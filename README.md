# 🧀DairyFlow - Dairy Supply Chain Management System 

A JavaFX desktop application that manages the flow of local cheese production from farmers to client companies. It provides an interactive UI to track cheese wheels, shelves, orders, and supply-chain operations.

## ✨ Key Features

- Manage farmers, companies, and cheese wheels (create/update/view)
- Shelf assignment & tracking (location, age, spoiled status)
- Ordering workflow from companies + inventory updates
- Reporting/dashboards for operational insights

## Tech Stack

- Java 21
- JavaFx
- Gradle
- JUnit 5
- Cucumber

## Demo

![Demo](demo.png)

## 🚀 Build & Run

### Prerequisites
- Java 21 (recommended)
- Gradle is optional (project includes the Gradle wrapper: './gradlew')

### Build
~~~bash
./gradlew build
~~~

### Run
~~~bash
./gradlew run
~~~

### Running Tests
~~~bash
./gradlew test
~~~

### Formatting
~~~bash
clang-format --style=Google -i src/**/*.java
- install clang-format (brew install clang-format)
~~~
