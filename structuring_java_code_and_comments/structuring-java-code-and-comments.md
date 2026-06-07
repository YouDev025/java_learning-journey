# Structuring Java Code and Comments

## 1. What are comments in Java?

Comments are notes inside the code that are not executed by the program. They are meant for developers to explain, clarify, or annotate parts of the code. Comments are a good practice because they help you and others understand the code better when revisiting it later.

## 2. Types of comments in Java

Java supports three comment types:

### 2.1 Single-line comments

Single-line comments start with `//`. Everything after `//` on that line is treated as a comment.

Example:

```java
// This is a single-line comment
int number = 10; // This variable stores the number 10
```

### 2.2 Multi-line comments

Multi-line comments start with `/*` and end with `*/`. They can span multiple lines.

Example:

```java
/*
 * This is a multi-line comment.
 * It can explain a block of code or provide detailed information.
 */
int sum = 0; /* this variable will hold the sum of numbers */
```

### 2.3 Documentation comments

Documentation comments start with `/**` and are used to generate documentation with tools like Javadoc. Each line typically begins with `*`.

Example:

```java
/**
 * This method calculates the square of a number.
 * @param number the number to be squared
 * @return the square of the input number
 */
public int square(int number) {
    return number * number;
}
```

## 3. Why comments matter

Comments are useful for several reasons:

- They enhance clarity by explaining complex logic.
- They help developers maintain code by providing context and reducing confusion.
- They support collaboration by helping team members understand each other's work.

## 4. Packages and project structure

Packages group related classes and interfaces together. They help avoid naming conflicts and make it easier to manage large projects.

### 4.1 Package declaration

The package declaration appears at the top of a Java source file.

Example:

```java
package com.example.myapp;

public class MyClass {
    // class code goes here
}
```

### 4.2 Folder structure

The folder structure should match the package declaration. For example:

```
src/
  com/
    example/
      myapp/
        MyClass.java
```

### 4.3 Public class file naming

Each public class should be in its own source file named exactly after the class with a `.java` extension. For example, `Book.java` contains `public class Book`.

## 5. Classes and objects

In Java, everything is organized into classes. A class is a blueprint for creating objects and can contain fields, constructors, and methods.

Example class:

```java
package com.example.library;

public class Book {
    String title;
    String author;

    public Book(String title, String author) {
        this.title = title;
        this.author = author;
    }
}
```

- `String title` and `String author` are instance variables or attributes.
- The constructor initializes a new `Book` object with title and author values.

## 6. Methods and naming conventions

Methods encapsulate functionality within a class. They should have descriptive names and follow conventions like `camelCase`, where the first word is lowercase and subsequent words start with an uppercase letter.

Example:

```java
public void displayBookDetails() {
    // method code
}
```

## 7. Entry point and execution flow

Every Java application needs an entry point, usually a `main` method within a public class. The JVM starts execution from the `main` method.

Example:

```java
package com.example.library;

public class App {
    public static void main(String[] args) {
        Library library = new Library();
        library.addBook(new Book("1984", "George Orwell"));
        library.displayBooks();
    }
}
```

This example demonstrates object creation and method calls in a structured way.

## 8. Imports and external classes

When using classes from other packages, import them at the top of the source file.

Example:

```java
package com.example.library;

import java.util.List;
import java.util.ArrayList;

public class Library {
    private List<Book> books = new ArrayList<>();
}
```

## 9. Best practices for beginners

- Use meaningful and descriptive names for classes, methods, and variables.
- Keep code organized with a logical package and file structure.
- Comment generously but wisely to explain why certain decisions were made.
- Avoid obvious comments that simply restate the code.
- Maintain consistent formatting, including indentation, spacing, and brace placement.
- Follow the flow of code execution, writing methods and classes in a logical order.

## 10. Summary

- Comments are notes in Java code that are not executed.
- Java supports single-line, multi-line, and documentation comments.
- Comments help with clarity, maintenance, and collaboration.
- Packages group related code and map to folder structure.
- Each public class should live in its own `.java` file.
- Java classes define objects and can contain fields, constructors, and methods.
- The `main` method is the entry point for Java applications.
- Imports bring classes from other packages into a source file.
- Beginners should use meaningful names, stay organized, comment wisely, and keep formatting consistent.
