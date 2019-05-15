---
layout: post
title:  "Writing a simple flask app and deploying it with docker"
date:   2019-05-15
categories: jekyll update
---
# Overview
During the last days I worked with Flask (http://flask.pocoo.org/) and created an application. In this post I wanted to share how to implement a simple Hello-World application with a REST-Endpoint and how we can deploy it using Docker. The sources can be found here: https://github.com/djetzen/hello_flask

The files needed for this task are `requirements.txt`, the `Dockerfile` and the `hello.py`.

## Requirements.txt
In the requirements.txt we list all the dependencies we want to use. In our case this is only `flask`. The syntax for this is, `plugin==version`. So here we are using the (as of now) latest version of flask, which is 1.0.2. We are using this file for configuring and installing the plugins to our python version inside the Docker container with pip.

## hello.py
The `hello.py` is quite simple. We import in the first line Flask and create in line 3 an app. Endpoints are registered using the `@app.route` annotation. Inside the brackets the path is mentioned as well as the type of it. If nothing given, it is a GET-Endpoint. Otherwise we add to the brackets something like `methods=['POST']`. Inside our route function we simply return the string saying `Hello Flask`. At the end of the file we create a main method, which starts the Flask app.

## Dockerfile
The Dockerfile inherits the Python 3.7.3 alpine image (latest version at the time of this post). In the next lines we copy the `requirements.txt` and the `hello.py` file to the root direction of this folder. Currently the python version inside the Docker container does not have the necessary Flask plugin installed. Therefore we make a `RUN` command and install every plugin in the specific version as given in the `requirements.txt`. As our Flask application is running on the Port 5000, we expose this port and call our application using the `CMD["python", "hello.py"]`.

## Building and running
For building the Docker image we navigate to the folder of the source files and  simply call: `docker build -t hello_flask .`.
After this was successful we simply call `docker container run -p 5000:5000 hello_flask`. Optionally you can add the `-d` parameter to start the container in detached mode.
As soon as the container is running, we go to `http://localhost:5000/hello` and we can see the answer "Hello Flask!".