# Maven (mvn)

## Build Lifecycle Commands

| Command | Description |
| :--- | :--- |
| `mvn clean` | Delete the `target/` directory (cleans previous builds) |
| `mvn compile` | Compile the source code of the project |
| `mvn test` | Compile and run unit tests |
| `mvn package` | Package the compiled code into a distributable format (e.g., JAR/WAR) |
| `mvn verify` | Run checks on integration test results to ensure quality criteria are met |
| `mvn install` | Install the package into the local repository (`~/.m2/repository`) |
| `mvn deploy` | Copy the final package to a remote repository |

## Useful Options

| Command | Description |
| :--- | :--- |
| `mvn clean package -DskipTests` | Build and package the project while skipping tests |
| `mvn dependency:tree` | Display a tree of all project dependencies (great for finding conflicts) |
| `mvn dependency:purge-local-repository` | Clear the local repository of cached dependencies (fixes weird build issues) |
| `mvn spring-boot:run` | Start a Spring Boot application |

## Examples

```bash
# 1. Clean build skipping tests
mvn clean install -DskipTests

# 2. Create a new Maven project from an archetype (template)
mvn archetype:generate -DgroupId=com.mycompany.app -DartifactId=my-app -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
```
