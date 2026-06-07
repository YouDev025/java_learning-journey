# Java Development Kit (JDK)

## What is the JDK?

The Java Development Kit (JDK) is the full software development kit for Java. It includes the Java compiler (`javac`), the runtime, standard libraries, and tools for building, packaging, and diagnosing applications.

Common distributions: OpenJDK builds, Oracle JDK, Amazon Corretto, Eclipse Temurin.

## Key components

- `javac` — Java source compiler (produces bytecode `.class` files)
- `java` — Java launcher to run applications (invokes a JVM)
- `jlink` — create custom runtime images containing only required modules
- `javadoc` — generate API documentation from source
- `jar` — package and inspect JAR files
- `jshell` — interactive REPL for Java
- Tools for diagnostics: `jmap`, `jstack`, `jcmd`, `jlink`, `jdeps`

## How developers use the JDK

- Compile: `javac src/Main.java`
- Run compiled classes: `java -cp . Main`
- Create a JAR: `jar --create --file app.jar -C out/ .`
- Make a runtime image: `jlink --module-path jmods --add-modules my.module --output my-image`

## Environment variables and PATH

- Set `JAVA_HOME` to the JDK installation directory.
- Add `%JAVA_HOME%\bin` to `PATH` on Windows so `javac` and `java` are available.

## JDK versioning and modules

Since Java 9, the JDK is modularized (Project Jigsaw). Applications can be built with explicit module info or use the classpath. The JDK provides both modular runtime images and tools to analyze module dependencies.

## When to install the JDK

- If you write or build Java code, install the JDK.
- Continuous integration/build servers need the JDK to compile projects.

Practical tip: use distribution variant (Adoptium/Eclipse Temurin, Amazon Corretto) that matches your support and security needs.