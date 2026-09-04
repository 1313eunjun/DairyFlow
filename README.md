# DairyFlow

A JavaFX desktop application for managing cheese inventory, aging, suppliers, wholesale orders, and shelf operations.

## Problem

Small dairy facilities need to coordinate cheese intake, aging, storage, and wholesale sales while keeping inventory records consistent. Managing these workflows manually makes it difficult to know where each cheese wheel is stored, how long it has aged, whether it has spoiled, and which supplier or wholesale company is involved.

DairyFlow brings these operations into one desktop application with structured workflows and persistent local data.

## Key Features

- Register, update, view, and remove farmers and wholesale companies
- Purchase cheese wheels from farmers and track inventory changes
- Assign and remove cheese wheels from storage shelves
- Track shelf location, cheese age, aging treatments, and spoilage status
- Update and inspect individual cheese-wheel records
- Sell cheese wheels to wholesale companies
- Record operational activity and preserve application data between sessions
- Navigate workflows through a custom JavaFX interface

## Demo

![DairyFlow application demo](demo.png)

## Architecture

Application code is organized under `src/main/java/ca/mcgill/ecse/cheecsemanager/`:

```text
application/    Application startup and JavaFX initialization
controller/     Business logic, workflows, and transfer objects
fxml/           JavaFX UI controllers, views, and reusable components
model/          Domain model and business entities
persistence/    Data storage and loading
```

The UI layer delegates operations to controllers, controllers coordinate the domain model, and the persistence layer stores and restores application state.

## Tech Stack

- Java 17
- JavaFX 21
- Gradle
- XStream
- ControlsFX
- JUnit 5
- Cucumber

## Build and Run

### Prerequisites

- JDK 17

The Gradle wrapper is included, so a separate Gradle installation is not required.

### Build

```bash
./gradlew clean build
```

### Run

```bash
./gradlew run
```

### Test

```bash
./gradlew test
```

On Windows, replace `./gradlew` with `gradlew.bat`.

## Testing

DairyFlow combines JUnit 5 with Cucumber behavior-driven tests.

- Feature specifications are stored in `src/test/resources/`
- Step definitions and supporting tests are stored in `src/test/java/`
- Scenarios cover shelf management, farmer and wholesale-company workflows, cheese purchasing and sales, inventory assignment, cheese-wheel updates, aging treatments, and robot movement
- Gradle runs the test suites through the JUnit Platform

## Project Highlights

- Layered desktop architecture separating UI, workflows, domain objects, and persistence
- End-to-end inventory workflows spanning suppliers, shelves, cheese wheels, and wholesale companies
- File-based persistence for restoring application state
- Behavior-driven acceptance tests for core business requirements
- Reusable JavaFX controls, animations, and styled interface components
- Gradle wrapper for reproducible builds and tests

## Roadmap

- Add continuous integration for automated builds and tests
- Expand validation and error reporting across data-entry workflows
- Add exportable inventory and transaction reports
- Package the application as a platform-specific desktop installer
