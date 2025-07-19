# Maven Java Demo

This is a sample Java project using Maven to demonstrate project setup, build process, and basic logging implementation using SLF4J. The project serves as a template for quickly testing ideas with proper project structure and logging configured.

## Prerequisites

- Java 24 or later
- Maven 3.9+ (optional if using Maven Wrapper)

## Features

- Basic Maven project structure
- JUnit 5 for testing
- SLF4J logging framework
- Maven Wrapper included (allows running Maven without installation)

## Building the Project

### Using Maven (if installed)

```bash
mvn clean install
```

### Using Maven Wrapper (no Maven installation required)

```bash
./mvnw clean install      # For Linux/macOS
.\mvnw.cmd clean install  # For Windows
```

## Running the Application

### Using Maven

```bash
mvn exec:java -Dexec.mainClass="com.glinboy.demo.App"
```

### Using Java directly (after building)

```bash
java -jar target/demo-1.0-SNAPSHOT.jar
```

## Project Structure

```
├── src/
│   ├── main/
│   │   └── java/
│   │       └── com/
│   │           └── glinboy/
│   │               └── demo/
│   │                   └── App.java
│   └── test/
│       └── java/
│           └── com/
│               └── glinboy/
│                   └── demo/
│                       └── AppTest.java
├── pom.xml              # Project configuration
├── mvnw                 # Maven Wrapper script for Unix
├── mvnw.cmd            # Maven Wrapper script for Windows
└── README.md           # This file
```

## Adding Dependencies

The project uses Maven for dependency management. To add new dependencies, modify the `pom.xml` file. For example:

```xml
<dependency>
    <groupId>org.slf4j</groupId>
    <artifactId>slf4j-api</artifactId>
    <version>${slf4j.version}</version>
</dependency>
```

## Testing

Run tests using Maven:

```bash
mvn test
```

Or using Maven Wrapper:

```bash
./mvnw test             # For Linux/macOS
.\mvnw.cmd test        # For Windows
```

## Logging Configuration

The application uses Logback for logging with the following features:
- Console logging is always enabled
- File logging is optional and can be enabled via system property
- Log files are stored in the `logs` directory
- Rolling file policy with daily rotation
- Keeps last 10 days of logs
- Total log files size is capped at 1GB

### Enabling File Logging

By default, logs are only written to the console. To enable file logging, add the `-Dlog.file.enabled=true` system property when running the application:

```bash
# Using Java directly
java -Dlog.file.enabled=true -jar target/demo-1.0.0.jar

# Using Maven
mvn exec:java -Dexec.mainClass="com.glinboy.demo.App" -Dlog.file.enabled=true
```

When file logging is enabled:
- Current logs are written to: `logs/application.log`
- Archived logs are stored in: `logs/archived/application.yyyy-MM-dd.log`

To disable file logging, simply omit the system property or set it to false:
```bash
java -Dlog.file.enabled=false -jar target/demo-1.0.0.jar
```

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.
