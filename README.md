# dropwizard-groovy-template
[![License](http://img.shields.io/badge/license-APACHE-blue.svg?style=flat)](http://choosealicense.com/licenses/apache-2.0/)
[![SemVer](http://img.shields.io/badge/semver-2.0.0-blue.svg?style=flat)](http://semver.org/spec/v2.0.0)
[![Download](https://api.bintray.com/packages/cratekube/maven/dropwizard-groovy-template-client/images/download.svg)](https://bintray.com/cratekube/maven/dropwizard-groovy-template-client/_latestVersion)
[![Build Status](https://travis-ci.com/cratekube/dropwizard-groovy-template.svg?branch=master)](https://travis-ci.com/cratekube/dropwizard-groovy-template)
[![Coverage Status](https://coveralls.io/repos/github/cratekube/dropwizard-groovy-template/badge.svg?branch=master)](https://coveralls.io/github/cratekube/dropwizard-groovy-template?branch=master)

A template repository for Dropwizard Groovy applications

## Configuration
Internal and external services are configured by extending the Dropwizard application configuration with additional
settings. An environment variable parser is used to allow configuration settings to be overridden at runtime. 
These configuration options can be seen in the [app config file](app.yml).

## Local development

### Gradle builds
This project uses [gradle](https://github.com/gradle/gradle) for building and testing.  We also use the gradle wrapper
to avoid downloading a local distribution.  The commands below are helpful for building and testing.
- `./gradlew build` compile and build the application
- `./gradlew check` run static code analysis and test the application
- `./gradlew shadowJar` builds a fat jar that can be used to run the Dropwizard application

After you have generated the fat jar you can run your application with java using:
```bash
java -jar build/libs/dropwizard-groovy-template-1.0.0-SNAPSHOT-all.jar
```

### Docker builds
We strive to have our builds repeatable across development environment so we also provide a Docker build to generate the
Dropwizard application.  The examples below should be executed from the root of the project.

Running the base docker build run:
```bash
docker run --target Build .
```

Generating the Dropwizard application docker image:
```bash
docker run --target Package -t my-app .
```

## Using the API client
This application generates a client for the Dropwizard application by using the swagger specification.  The maven asset
is available in JCenter, make sure you include the JCenter repository (https://jcenter.bintray.com/) when pulling this
client.  To use the client provide the following dependency in your project:

Gradle:
```groovy
implementation 'io.cratekube:dropwizard-groovy-template:1.0.0'
``` 

Maven:
```xml
<dependency>
  <groupId>io.cratekube</groupId>
  <artifactId>dropwizard-groovy-template</artifactId>
  <version>1.0.0</version>
</dependency>
```

## API Documentation
The API docs for this project are powered by the Swagger Specification. After starting up the application the available
APIs can be found at `http://localhost:<configured port>/swagger`

## Contributing
If you are interesting in contributing to this project please read the [contribution](CONTRIBUTING.md) and 
[pull request](PR_GUIDELINES.md) guidelines.  Thank you for your interest in CrateKube!

Test pull Request - aaholla
