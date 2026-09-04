# Repository Guidelines

This is a JavaFX desktop project built with Gradle and FXML.

## Project Structure & Module Organization

Sources live in `src/main/java/ca/mcgill/ecse/cheecsemanager`. The `application` package bootstraps JavaFX, `model` contains domain logic, `controller` coordinates workflows and transfer objects, `persistence` manages XStream saves, and `fxml` contains UI controllers and reusable components. Behavioral specifications reside in `src/test/resources`, while step definitions and supporting tests belong in `src/test/java`.

Styles live in `src/main/resources/ca/mcgill/ecse/cheecsemanager/style/`.
Icons live in `src/main/resources/ca/mcgill/ecse/cheecsemanager/view/icons/`.

Keep generated runtime outputs such as `app.data` and `build/` untouched so Gradle can regenerate them.

## Build, Test, and Development Commands

- `./gradlew clean build` — compile the application, run checks, and prepare build outputs.
- `./gradlew run` — start the JavaFX client.
- `./gradlew test` — run the JUnit 5 and Cucumber test suites.
- `./gradlew test -t` — watch for changes and rerun tests.

The Gradle wrapper is included, so a separate Gradle installation is not required.

## Coding Style & Naming Conventions

Use JDK 17. Indent with four spaces, use PascalCase for classes, camelCase for members, and SCREAMING_SNAKE_CASE for constants. Keep controller names aligned with their view or functional area. Prefer short comments only where logic is not obvious. Use the repository's configured Java style and Prettier for FXML formatting.

## Testing Guidelines

Follow the numbered `.feature` naming used in `src/test/resources` so scenarios remain ordered and readable. Add matching step definitions or unit tests near the feature's functional area, and assert through persistence APIs when state changes are involved. Every new workflow or UI change should include at least one Cucumber scenario and, when practical, a focused JUnit test. Run `./gradlew test` before opening a pull request.

## Commit & Pull Request Guidelines

Continue using `name/feature-context` branches such as `ewen/fxml-menu` or `ayush/persistence-fixes`. Write imperative, single-purpose commits such as `fix: guard empty shelf search` and avoid bundling unrelated changes. Pull requests should describe the problem, solution, test evidence, and any data-reset steps, then wait for reviewer sign-off and passing checks.

## Configuration & Data Tips

Point `JAVA_HOME` to a JDK 17 installation and confirm it with `java -version`. Treat `app.data` as disposable sample data, exclude secrets, and keep helper tooling such as `svg_converter.py` aligned with the resources used by the application.
