# Spring Boot and Vaadin course source code

This repository contains the source code for the [Building Modern Web Applications With Spring Boot and Vaadin](https://vaadin.com/docs/latest/flow/tutorials/in-depth-course).

*Live demo:* https://crm.demo.vaadin.com

Prerequisites:
* Java 8 or higher
* node.js and
* npm. Vaadin Gradle plugin will install those for you
  automatically (handy for CI), or you can install it to your OS:
    * Windows: [node.js Download site](https://nodejs.org/en/download/) - use the .msi 64-bit installer
    * Linux: `sudo apt install npm`
* Git
* (Optionally): Intellij Community

## Branches
- The main branch contains the source code for the latest Vaadin release

## Text tutorial
You can find a text version of the tutorial in the [Vaadin Documentation](https://vaadin.com/docs/latest/flow/tutorials/in-depth-course).

## Running With Spring Boot via Gradle In Development Mode

Run the following command in this repo:

```bash
./gradlew clean bootRun
```

Now you can open the [http://localhost:8080](http://localhost:8080) with your browser.

## Running With Spring Boot from your IDE In Development Mode

Run the following command in this repo, to create necessary Vaadin config files:

```bash
./gradlew clean vaadinPrepareFrontend
```

The `build/vaadin-generated/` folder will now contain proper configuration files.

Open the `DemoApplication` class, and Run/Debug its main method from your IDE.

Now you can open the [http://localhost:8080](http://localhost:8080) with your browser.

## Building In Production Mode

Run the following command in this repo:

```bash
./gradlew clean build -Pvaadin.productionMode
```

That will build this app in production mode as a runnable jar archive; please find the jar file in `build/libs/base-starter-spring-gradle*.jar`.
You can run the JAR file with:

```bash
cd build/libs/
java -jar base-starter-spring-gradle*.jar
```

Now you can open the [http://localhost:8080](http://localhost:8080) with your browser.

### Building In Production On CI

Usually the CI images will not have node.js+npm available. However, Vaadin Gradle Plugin will download it for you automatically, there is no need for you to do anything.
To build your app for production in CI, just run:

```bash
./gradlew clean build -Pvaadin.productionMode
```
