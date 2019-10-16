# Building Java Projects with Gradle

* I created a simple "Hello World" Java app in Spring Boot and then built it using Gradle.
* This project has been created from scratch. The spring initializer wasn't used.
* The project has 3 branches: `Master`, `Wrapper` and `Webapp`.

## Getting Started

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
  ###### 2.1 The Gradle Wrapper is the preferred way of starting a Gradle build. It consists of a batch script for Windows and a shell script for OS X and Linux. These scripts allow you to run a Gradle build without requiring that Gradle be installed on your system. This used to be something added to your build file, but it’s been folded into Gradle, so there is no longer any need. Instead, you simply use the following command.

  ``` $ gradle wrapper --gradle-version 5.2.1 ```

  ###### 2.2 After this task completes, you will notice a few new files. The two scripts are in the root of the folder, while the wrapper jar and properties files have been added to a new gradle/wrapper folder.

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
  ###### 3.1 Now you can create a web controller for a simple web application.
      
  ```src/main/java/hello/HelloController.java```
  
  ###### 3.2 Create an Application class
  
  ###### 3.3 Run the application
  
  ```./gradlew build && java -jar build/libs/gs-spring-boot-0.1.0.jar```

  ###### 3.4 Check out the service.
      
  Run in another CLI: ```$ curl localhost:8080```
  Output: Greetings from Spring Boot!

  ###### 3.5 Add Unit Tests (Under Progress)  
    Creating two files:  
      3.5.1 `src/test/java/hello/HelloControllerTest.java`  
      3.5.2 `src/test/java/hello/HelloControllerIT.java`
      
## Tools Required

* Spring Boot
* Gradle
* IDE (Intellij)
* Java 8

## Resources

* [Bulding an Application with Spring Boot](https://spring.io/guides/gs/spring-boot/)
* [Building Java Projects with Gradle](https://spring.io/guides/gs/gradle/)
