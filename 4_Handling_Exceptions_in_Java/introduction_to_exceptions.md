# Introduction to Exceptions

## What are Exceptions?
Java exceptions are events that disrupt the normal flow of a program. They occur during program execution and can cause a program to behave unexpectedly or crash. Examples include dividing by zero, accessing an invalid array index, or trying to open a file that does not exist.

## Why Exceptions Matter
Java provides exception handling so programs can respond to errors gracefully instead of terminating abruptly. By catching exceptions, an application can display helpful messages, recover from errors, or clean up resources.

## Errors vs Exceptions
- **Errors** are serious conditions that usually cannot be recovered from.
- They are often related to the environment where the application runs and are typically outside the programmer's control.
- Examples: JVM exhausting memory, memory leaks, stack overflow, library incompatibilities, infinite recursion.

- **Exceptions** are conditions that a reasonable application might catch and handle.
- They represent recoverable situations, such as invalid input or unavailable resources.

## Types of Exceptions
### Checked Exceptions
Checked exceptions are verified by the compiler at compile time. You must either:
- handle them with a `try-catch` block, or
- declare them in the method signature using `throws`.

Common checked exceptions:
- `IOException` — input/output failures, such as reading a missing file
- `SQLException` — database access errors
- `ClassNotFoundException` — when a class cannot be loaded by name

### Unchecked Exceptions
Unchecked exceptions are not checked by the compiler at compile time. They usually indicate programming mistakes and can often be prevented with correct code.

Common unchecked exceptions:
- `NullPointerException` — using a null reference
- `ArrayIndexOutOfBoundsException` — accessing an invalid array index
- `ArithmeticException` — invalid arithmetic operations like divide by zero
- `IllegalArgumentException` — a method receives an inappropriate argument

## Common Exception Causes
Exceptions can occur from:
- invalid user input
- device malfunction
- lost network connectivity
- out-of-bounds access
- null reference use
- type mismatches
- unavailable files
- database errors
- arithmetic mistakes

## Handling Exceptions in Java
Java uses `try`, `catch`, and `finally` blocks:
- `try` contains code that may throw an exception.
- `catch` handles the exception if it occurs.
- `finally` runs regardless of whether an exception was thrown and is often used to clean up resources.

Example:
```java
public class DivisionExample {
    public static void main(String[] args) {
        int numerator = 10;
        int denominator = 0;

        try {
            int result = numerator / denominator;
            System.out.println("Result: " + result);
        } catch (ArithmeticException e) {
            System.out.println("Error: Cannot divide by zero.");
        } finally {
            System.out.println("Cleanup code runs regardless of an exception.");
        }
    }
}
```

## Custom Exceptions
You can create your own exception types by extending `Exception` for checked exceptions or `RuntimeException` for unchecked exceptions. This helps define specific application-level error conditions.

Example:
```java
class MyCustomException extends Exception {
    public MyCustomException(String message) {
        super(message);
    }
}

public class CustomExceptionExample {
    public static void main(String[] args) {
        try {
            throw new MyCustomException("This is a custom exception message.");
        } catch (MyCustomException e) {
            System.out.println("Caught custom exception: " + e.getMessage());
        }
    }
}
```

## Summary
- An exception is an event that disrupts program flow.
- Exceptions allow Java programs to handle errors gracefully instead of crashing.
- Errors are serious and usually not handled by applications.
- Checked exceptions are checked at compile time and must be handled or declared.
- Unchecked exceptions are not checked by the compiler and usually signal programming errors.
- Java's exception handling mechanism uses `try`, `catch`, and `finally`.
- Custom exceptions let you define application-specific error conditions.
