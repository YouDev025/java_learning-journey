# Java Environment and Ecosystem

- Java is a versatile programming language used in web apps, mobile apps, enterprise software, cloud-native, and microservices-based development.
- It runs on any system with Java support, as the Java Virtual Machine (JVM) converts Java bytecode into machine code.
- The Java Development Kit (JDK) includes Java Runtime Environment (JRE) and development tools for building, compiling, and running Java applications.
- The JRE provides the JVM and core libraries for executing Java applications but lacks development tools like compilers.
- Java follows object-oriented programming, organizing code into objects for better management.
- It enforces strong typing, ensuring strict type checks during compilation.
- It supports multithreading, allowing multiple processes to run simultaneously.
- Automatic memory management handles memory allocation and garbage collection.
- Integrated Development Environments (IDEs) provide comprehensive tools for software development.
- Frameworks facilitate code reuse and accelerate development.
- Build tools automate compiling code, managing dependencies, and packaging applications.
- Application servers provide environments for deploying and managing Java applications.
- Testing frameworks ensure application functionality through robust testing tools.
- The Java ecosystem supports desktop and mobile applications, as well as development frameworks using key technologies.
- Java includes built-in security features to protect against security risks.
- Its comprehensive standard library provides built-in tools for common tasks.
- The features of Java include object-oriented programming, platform independence, strong typing, automatic memory management, multithreading, a comprehensive standard library, built-in security features, and versatility across domains.

## 1. What is Java?

Java is a high-level, object-oriented programming language and platform designed for portability, performance, and safety. It compiles source code to bytecode that runs on the Java Virtual Machine (JVM), enabling "Write Once, Run Anywhere" portability across operating systems.

### Key characteristics

- Object-oriented
- Platform independence (JVM)
- Strong standard library
- Automatic memory management (garbage collection)
- Concurrency primitives and APIs

## 2. Java Editions

- **Java SE (Standard Edition)** — Core language, standard libraries, desktop and console applications.
- **Jakarta EE (formerly Java EE)** — Specifications and APIs for enterprise applications: servlets, JPA, JAX-RS, CDI, etc.
- **Java ME** — For constrained and embedded devices (IoT, legacy mobile devices).

## 3. Platform components

- **JDK (Java Development Kit)** — Tools for development: `javac`, `javadoc`, `jar`, and the standard libraries.
- **JRE (Java Runtime Environment)** — Runtime components needed to execute Java applications (JVM + standard libs).
- **JVM (Java Virtual Machine)** — Executes Java bytecode; provides memory management, class loading, and runtime optimizations.

Example: compile and run

```bash
javac Main.java
java Main
```

## 4. Build & dependency tools

- **Maven** — XML-driven, strong dependency management and convention-over-configuration; central in many enterprises.
- **Gradle** — Flexible, faster builds, Groovy or Kotlin DSL; widely used for modern projects and Android.

Typical Maven layout:

```
project/
├── src/
└── pom.xml
```

Dependency example (Maven):

```xml
<dependency>
  <groupId>org.springframework</groupId>
  <artifactId>spring-core</artifactId>
  <version>6.0.0</version>
</dependency>
```

## 5. Common development tools

- `javac` — Java compiler
- `java` — JVM launcher
- `javadoc` — API documentation generator
- `jar` — Package/inspect JAR files

## 6. IDEs

- **IntelliJ IDEA** — Rich refactoring, smart completion, and ecosystem integrations.
- **Eclipse** — Extensible with many plugins; strong legacy tooling.
- **NetBeans** — Official Apache IDE; good for quick starts and GUI builders.

## 7. Popular frameworks & libraries

- **Spring Framework / Spring Boot** — Dependency injection, web, data access, and microservice foundations. Spring Boot accelerates app setup with auto-configuration and embedded servers.
- **Hibernate / JPA** — Object‑relational mapping (ORM) for database persistence.
- **Micronaut, Quarkus** — Modern frameworks optimized for cloud and native images.

Spring Boot starter example:

```java
@SpringBootApplication
public class Application {
  public static void main(String[] args) {
    SpringApplication.run(Application.class, args);
  }
}
```

## 8. Web & network technologies

- **Servlets & JSP** — Lower-level web APIs (servlet container).
- **REST APIs** — Commonly implemented with Spring MVC / Spring WebFlux or JAX-RS implementations.
- **WebSockets, gRPC** — For real-time and RPC-style communication.

## 9. Packaging & deployment

- **JAR** — Java ARchive (library or executable with `Main-Class`).
- **WAR** — Web Application Archive for servlet containers (less common with Spring Boot's embedded servers).
- **EAR** — Enterprise Archive for Jakarta EE applications.
- **Native images** — Tools like GraalVM native-image can compile applications ahead-of-time for faster startup and lower memory.

## 10. Java ecosystem definitions

- **JDK** — Java Development Kit: all the tools and libraries needed to write and build Java applications.
- **JRE** — Java Runtime Environment: runtime components required to execute Java programs.
- **JVM** — Java Virtual Machine: the runtime engine that loads classes, verifies bytecode, and executes code on the host platform.
- **Bytecode** — Platform-independent instructions generated by the Java compiler (`javac`).
- **Classpath** — The list of paths and JARs that the JVM uses to locate classes at runtime.
- **Module path** — The modern Java module resolution mechanism introduced in Java 9 for modular applications.
- **LTS** — Long-term support release, maintained for a longer period and often recommended for production.
- **OpenJDK** — The open-source reference implementation of Java.

## 11. Release model and versioning

- Oracle and the OpenJDK community publish new Java releases every six months.
- Long-term support (LTS) releases arrive roughly every three years and are the best choice for stable production use.
- Common LTS versions include Java 8, Java 11, Java 17, and Java 21.
- Java feature releases introduce new language features, library updates, and performance improvements.

## 12. Choosing tools and workflows

- Use a current JDK version supported by your frameworks. For most new projects, Java 17 or newer is recommended.
- Choose Maven for convention, ease of use, dependency management, and large corporate projects.
- Choose Gradle when you need fast builds, custom scripts, or Kotlin-based build logic.
- Use a modern editor or IDE with Java support, such as IntelliJ IDEA, Eclipse, NetBeans, or Visual Studio Code.

## 13. Learning resources

- Maven Central / MVNRepository: https://mvnrepository.com
- Official Java docs: https://docs.oracle.com/en/java/
- Spring Guides: https://spring.io/guides
- OpenJDK: https://openjdk.org
- Jakarta EE: https://jakarta.ee
