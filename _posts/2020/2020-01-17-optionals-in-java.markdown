---
layout: post
title:  "Nullsafe programming in Java with Optionals"
date:   2020-01-18
categories: programming
---
# Introduction
A concept which was not very well known to me is the Optional class in Java. I read, that this concept was introduced in Java 8, but I never saw it in my daily work or used it until the last days. 
Last week a colleague showed me this concept and I would like to share it with you by showing a (very) small example.

## Domain
The domain is made up and contains three classes.
- `Person`: There is a Person, which has a `name` and an optional `location`. The location here should be optional.
- `Location`: The location has a `zipCode`, a `city`, but also a nested attribute `street` which is of type `Street`.
- `Street`: It has a `streetName` and a `houseNumber`.

You can retrieve the street by asking the person-object for the method `getStreet()`.
For the getters, setters and the builder we use project [lombok](https://projectlombok.org/). The documentation for this can be found [here](https://projectlombok.org/features/all)

## First test
We will write a first test, which tests, that the method `getStreet()` does what it is supposed to do:
```
@Test
void streetIsReturned() {
    Person p = new Person();
    p.setName("Dominik");
    p.setLocation(
        Location.builder()
        .street(Street.builder().streetName("Main Street").houseNumber(5).build())
        .zipCode("00000").city("Frankfurt").build());
    assertEquals("Main Street",p.getStreet());
}
``` 
You can see, that we create a Person, give it a name and using the builder pattern set a location with a street. Afterwards we make an assertion.

The implementation for the method is like this:
```
public String getStreet() {
    return location.getStreet().getStreetName();
}
```

## Second test
We will create a second test, where we set no location, as the location is optional.
```
@Test
    void locationIsOptional(){
        Person p = new Person();
        p.setName("Dominik");
        assertEquals(null, p.getStreet());
    }
```
Once we run this test, we will get a `NullPointerException` as we do not check for the location to be not null. 
We can do this quite easy with this implementation:
```
public String getStreet() {
    if (this.location != null) {
        return location.getStreet().getStreetName();
    }
    return null;
}
```
This will be totally fine and we see no problems here.

## Third test
We will now write a third test. The location is now given, but the street is not. Here is the test:
```
@Test
void streetIsOptional() {
    Person p = new Person();
    p.setName("Dominik");
    p.setLocation(Location.builder().zipCode("00000").city("Frankfurt").build());
    assertEquals(null, p.getStreet());
}
```
This will now throw a `NullPointerException` because we do not check, whether `location.getStreet()` is null. We could implement this with an additional null-check. But you see, that this can get quite messy, if we have a more complex structure, because there will be a lot of nested null checks. To avoid this, we can use [Optionals](https://docs.oracle.com/javase/8/docs/api/index.html?java/util/Optional.html) from Java.

An example implementation can then look like this:
```
public String getStreet() {
    return Optional.ofNullable(location)
            .map(location -> location.getStreet())
            .map(street -> street.getStreetName())
            .orElse(null);
}
```
`Optional.ofNullable()` takes as the argument an element which possibly can be null. If it is not null, it will call the `map`-method. If the expression inside the `map`-method is not null, it will call the next `map`-method and so on. If any of these lambdas are null, it will return the expression inside the `orElse`-method, otherwise the expression from the last `map`.

In my opinion this is way more readable than the many nullchecks you normally have. 

The sources can be found here on [Github](https://github.com/djetzen/java_examples/tree/master/optionals).

