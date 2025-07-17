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

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.
