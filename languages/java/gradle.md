# Gradle

## Basic Commands

Always use the Gradle Wrapper (`./gradlew`) if available in the project, instead of a globally installed `gradle` command.

| Command | Description |
| :--- | :--- |
| `./gradlew build` | Build the project (compiles code, runs tests, creates JAR/WAR) |
| `./gradlew clean` | Delete the `build/` directory |
| `./gradlew test` | Run tests |
| `./gradlew assemble` | Compile and package the code without running tests |
| `./gradlew tasks` | List all available runnable tasks in the project |
| `./gradlew dependencies` | Show the dependency tree for the project |

## Useful Options

| Command | Description |
| :--- | :--- |
| `./gradlew build -x test` | Build the project but skip running tests |
| `./gradlew build --refresh-dependencies` | Force Gradle to re-download cached dependencies |
| `./gradlew build --scan` | Generate a detailed build scan (performance and dependency report) |
| `./gradlew build --info` / `--debug` | Increase verbosity for troubleshooting |

## Running Applications

For applications using the `application` plugin or Spring Boot:

| Command | Description |
| :--- | :--- |
| `./gradlew run` | Run the application (if `application` plugin is applied) |
| `./gradlew bootRun` | Run a Spring Boot application |

## Daemon and Performance

Gradle runs a background Daemon to speed up subsequent builds.

| Command | Description |
| :--- | :--- |
| `./gradlew --status` | Check the status of running Gradle daemons |
| `./gradlew --stop` | Stop all running Gradle daemons (useful if the build hangs) |
| `./gradlew build --no-daemon` | Run a build without the Daemon (useful for CI/CD) |
