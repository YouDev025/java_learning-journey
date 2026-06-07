# Packages and Imports in Java

This note summarizes packages and imports: what they are, how to create them, how to import classes, important built-in packages, and best practices.

## What is a package?

A package in Java is a namespace that groups related classes and interfaces, similar to labeled cabinets in an organized record office. Packages:

- Organize code into a folder-like structure for easier navigation.
- Prevent name collisions by providing namespaces (two classes with the same simple name can coexist in different packages).
- Control access: classes and members can be package-private (default) or public, affecting visibility within the package.

## Creating a package

Declare a package at the top of a Java source file using the `package` keyword. Conventionally use a reverse-domain name to ensure uniqueness (for example, `com.example`):

```java
// file: src/shapes/Circle.java
package shapes;

public class Circle {
    private double radius;

    public Circle(double radius) {
        this.radius = radius;
    }

    public double area() {
        return Math.PI * radius * radius;
    }
}
```

Notes:
- The directory structure should match the package name (e.g., `shapes/Circle.java`).
- Use meaningful, short package names and follow the reverse-domain convention for public libraries.

## Importing classes and packages

Use the `import` statement to bring classes (or all classes from a package) into scope, so you don't have to use fully-qualified names:

```java
// file: src/app/Main.java
package app;

import shapes.Circle; // import a single class

public class Main {
    public static void main(String[] args) {
        Circle c = new Circle(2.5);
        System.out.println("Area: " + c.area());
    }
}
```

Wildcard import:

```java
import shapes.*; // imports all public classes from shapes package
```

Fully-qualified name (no import):

```java
shapes.Circle c = new shapes.Circle(2.5);
```

When compiling and running from the command line, ensure the classpath includes the root of your package directories. Example (from project root):

```powershell
javac src/shapes/Circle.java src/app/Main.java
java -cp src app.Main
```

## Built-in Java packages (common ones)

- `java.lang` — automatically imported. Core classes: `String`, `Math`, `System`, `Object`, `Thread`.
- `java.util` — collections and utilities: `ArrayList`, `HashMap`, `Collections`, `Optional`, `Scanner`.
- `java.io` — input/output and streams: `File`, `InputStream`, `OutputStream`, `BufferedReader`, `FileReader`.
- `java.net` — networking: `Socket`, `ServerSocket`, `URL`, `HttpURLConnection`.
- `java.sql` — JDBC and database access: `Connection`, `DriverManager`, `PreparedStatement`, `ResultSet`.
- `java.time` — modern date/time API: `LocalDate`, `LocalTime`, `LocalDateTime`, `Duration`, `ZoneId`.

## Imports best practices

- Prefer importing only the classes you need rather than using `*` wildcard imports in large projects.
- Keep imports organized (many IDEs can auto-sort and remove unused imports).
- Avoid listing unused imports — they add clutter and may confuse readers.
- Use package-private visibility intentionally to encapsulate implementation details within a package.

## Example: shapes package + usage

Structure:

- src/
  - shapes/
    - Circle.java
  - app/
    - Main.java

Circle (in `shapes`):

```java
package shapes;

public class Circle {
    private double radius;

    public Circle(double radius) { this.radius = radius; }
    public double area() { return Math.PI * radius * radius; }
}
```

Main (in `app`):

```java
package app;

import shapes.Circle;

public class Main {
    public static void main(String[] args) {
        Circle c = new Circle(3.0);
        System.out.println("Area: " + c.area());
    }
}
```
