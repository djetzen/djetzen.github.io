---
layout: post
title:  "Playing around with ionic"
date:   2019-09-18
categories: programming
---
## Ionic
In the last weeks I have been playing around with the [Ionic](https://ionicframework.com/)-Framework. In the beginning my motivation was to create an app to track my activities with my new bike. The requirements were that the records could be entered on my mobile device and it should be very easy to use. The first idea was to create a webpage and host it on my raspberry pi. After some considerations, I then decided to rather create an app. As I did the native android development a few years back during my bachelors thesis I decided to test out the frameworks that promise a single codebase for multiple platforms. Another reason for choosing Ionic was that I was not very familiar with Typescript and Angular and the whole technology stack associated with it. My motivation was to get a first glimpse at these technologies and learn them.

## Overview
The setup was quite easy as there are very good examples and tutorials on the Ionic page. I decided to start with the sidemenu app and customise it. The application has three pages. On the first page you can enter the distance you rode by bike and the money you saved (e.g. in my case the parking fees at the station). On the second page there is a list of all the elements where you can see them and also delete each entry. On the top there are some "statistics" like the total sum of km rode, the sum of the money saved and the sum of co2 you saved by riding the bike. On the third page you can set the litres of fuel your car takes per 100km. This value is used for calculating the co2 saved.

## Technical stuff
In the background there is an sqlite database where the entries are saved. I decided to use sqlite as it was quite easy to setup and I am familiar with relational databases. There are also two services which deliver the data. The dataservice does some calculations or reads from the internal storage, the database service connects to the database and performs the operations there. The tests are written with the angular libraries, jasmine and the test runner is karma, which was configured by default.

## Last words
The start was very easy and I managed to set up and run the app after a short time. The design and the layout of the tests are for sure improvable, but as a small project and to explore ionic, angular and typescript for the first time it is fine. And the most important point: the app is working and is used nearly every day by me and is giving me some nice informations.

the sources can be found [here](https://github.com/djetzen/bike-savings)