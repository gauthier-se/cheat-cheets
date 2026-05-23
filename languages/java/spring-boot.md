# Spring Boot

## CLI & Maven Integration

Most of the interaction with Spring Boot from the CLI happens via the Maven plugin (`spring-boot-maven-plugin`).

| Command | Description |
| :--- | :--- |
| `mvn spring-boot:run` | Start the Spring Boot application |
| `mvn clean package` | Build an executable "fat" JAR containing all dependencies |
| `java -jar target/app.jar` | Run the built Spring Boot application |

## Spring Boot Profiles

Profiles are used to segregate parts of your application configuration (e.g., `dev`, `prod`).

```bash
# Run with a specific profile via Maven
mvn spring-boot:run -Dspring-boot.run.profiles=dev

# Run with a specific profile via compiled JAR
java -jar target/app.jar --spring.profiles.active=prod
```

## Useful JVM Arguments

When running your app in production, you can pass standard Java arguments before the `-jar` flag.

```bash
# Set memory limits and active profile
java -Xms512m -Xmx1024m -jar target/app.jar --spring.profiles.active=prod

# Pass custom application properties on the fly (e.g., overriding server port)
java -jar target/app.jar --server.port=8081 --spring.datasource.url=jdbc:mysql://localhost/test
```

## Spring Initializr (via CLI)

You can bootstrap a new Spring Boot project directly from the terminal using `curl` and the Spring Initializr API.

```bash
# Generate a ZIP with Web, JPA, and PostgreSQL dependencies
curl https://start.spring.io/starter.zip \
  -d dependencies=web,data-jpa,postgresql \
  -d language=java \
  -d type=maven-project \
  -o my-project.zip
```
