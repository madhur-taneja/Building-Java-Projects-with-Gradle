# Building Java Projects with Gradle

A simple "Hello World" Java app in Spring Boot and then built it using Gradle

Open and view the Project using the `.zip` file provided or at my [Github Repository](https://github.com/madhur-taneja/Building-Java-Projects-with-Gradle)

## Table of Contents
- [Getting Started](#getting-started)
	- [Tools Required](#tools-required)
	- [Installation](#installation)
- [Development](#development)
    - [1. Building the base app](#1-building-the-base-app)
	- [2. Adding the wrapper](#2-adding-the-wrapper)
	- [3. Building the web app](#3-building-the-web-app)
- [Running the App](#running-the-app)
- [Resources](#resources)

## Getting Started

This project has been created from scratch. The spring initializer wasn't used

The project has 3 branches: `master`, `wrapper` and `webapp`

* `master` contains the `hello-world` app
* `wrapper` is built from master additionally containing the gradle-wrapper
* `webapp` is built from master additionally containing a webapp

### Tools Required

You would require the following tools to develop and run the project:

* Java 8
* SpringBoot
* Gradle
* A text editor or an IDE (like IntelliJ)

### Installation

* Install Gradle in your system. It’s highly recommended to use an installer:
  * [SDKMAN](https://sdkman.io/)
  * [Homebrew](https://brew.sh/)
  
  As a last resort, if neither of these tools suit your needs, you can download the binaries from [Gradle Org](https://www.gradle.org/downloads)

## Development

##### 1. Building the base app  
  ###### 1.1 Create the Directory Structure
   ```
    └── src
        └── main
            └── java
                └── hello
   ```
  ###### 1.2 Create a Gradle build file

##### 2. Adding the wrapper
  ###### 2.1 The Gradle Wrapper is the preferred way of starting a Gradle build. It consists of a batch script for Windows and a shell script for OS X and Linux. These scripts allow you to run a Gradle build without requiring that Gradle be installed on your system. This used to be something added to your build file, but it’s been folded into Gradle, so there is no longer any need. Instead, you simply use the following command

  ``` $ gradle wrapper --gradle-version 5.2.1 ```

  ###### 2.2 After this task completes, you will notice a few new files. The two scripts are in the root of the folder, while the wrapper jar and properties files have been added to a new gradle/wrapper folder

  ```
    └── <project folder>
        └── gradlew
        └── gradlew.bat
        └── gradle
            └── wrapper
                └── gradle-wrapper.jar
                └── gradle-wrapper.properties
  ```

  The Gradle Wrapper is now available for building your project. Add it to your version control system, and everyone that clones your project can build it just the same. It can be used in the exact same way as an installed version of Gradle. Run the wrapper script to perform the build task, just like you did previously:
  
  ```./gradlew build```

##### 3. Building the web app
  ###### 3.1 Now you can create a web controller for a simple web application
      
  ```src/main/java/hello/HelloController.java```
  
  ###### 3.2 Create an Application class
  
  ###### 3.3 Run the application
  
  ```./gradlew build && java -jar build/libs/gs-spring-boot-0.1.0.jar```

  ###### 3.4 Check out the service
      
  Run in another CLI: ```$ curl localhost:8080``` <br>
  Output: Greetings from Spring Boot!

  ###### 3.5 Add Unit Tests (Under Progress)  
    Creating two files:  
      3.5.1 `src/test/java/hello/HelloControllerTest.java`  
      3.5.2 `src/test/java/hello/HelloControllerIT.java`
    
## Running the App

There are multiple commands that are useful when working with gradle

* Open terminal in the root directory of the project
  * To check the available tasks, use the following command:
  ```
    gradle tasks
  ```
  * To check the tests and linting, use the following command:
  ```
    gradle checks
  ``` 
  * To delete the contents of the build directory, use the following command:
  ```
    gradle clean
  ```
  * To build the project, use the following command:
  ```
    gradle build
  ```
  * And finally to run the project, use the following command:
  ```
    gradle run
  ``` 
	
## Resources

* [Bulding an Application with Spring Boot](https://spring.io/guides/gs/spring-boot/)
* [Building Java Projects with Gradle](https://spring.io/guides/gs/gradle/)
