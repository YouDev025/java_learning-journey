# Using Multiple `try-catch` in Java

## What is `try-catch` Exception Handling?
A `try-catch` block in Java handles exceptions that occur during program execution. It helps catch runtime errors and allows the application to respond appropriately instead of crashing.

### Basic Syntax
```java
try {
    // code that may throw an exception
} catch (ExceptionType e) {
    // handle exception
}
```

## Multiple `try-catch`
Multiple `try-catch` can mean using more than one `catch` block with a single `try`, or using multiple separate `try-catch` statements in a program.
This lets you handle different exception types separately when the same block of code may throw different errors.

### Example with multiple catch blocks
```java
try {
    int[] data = {1, 2, 3};
    int value = data[5];
    int result = 10 / 0;
} catch (ArrayIndexOutOfBoundsException e) {
    System.out.println("Array index is invalid: " + e.getMessage());
} catch (ArithmeticException e) {
    System.out.println("Arithmetic error: " + e.getMessage());
}
```
- `ArrayIndexOutOfBoundsException` occurs when an array index is invalid.
- `ArithmeticException` occurs when there is an illegal arithmetic operation, such as dividing by zero.

## Benefits of multiple `try-catch`
- Clearer error handling: each exception type is handled individually.
- Specific responses: different messages or recovery code can run for different errors.
- Better code organization: exception handling is more readable and maintainable.

## Common Use Cases
### User input validation
When converting user input to numbers, invalid input can throw `NumberFormatException`.
```java
try {
    int value = Integer.parseInt(userInput);
} catch (NumberFormatException e) {
    System.out.println("Invalid number format: " + userInput);
}
```

### File operations
Reading files can generate multiple exceptions like `FileNotFoundException` and `IOException`.
```java
try {
    FileReader reader = new FileReader("example.txt");
    BufferedReader buffered = new BufferedReader(reader);
    System.out.println(buffered.readLine());
    buffered.close();
} catch (FileNotFoundException e) {
    System.out.println("File not found: " + e.getMessage());
} catch (IOException e) {
    System.out.println("I/O error: " + e.getMessage());
}
```

## The `throws` Keyword
The `throws` keyword in a method declaration indicates that the method may throw one or more exceptions.
This tells callers that they need to handle those exceptions with `try-catch` or declare them again with `throws`.

### Syntax
```java
returnType methodName(parameters) throws ExceptionType1, ExceptionType2 {
    // method body
}
```

### Why use `throws`?
- Separation of concerns: methods can focus on logic without handling every exception.
- Clear contracts: callers know which errors may occur.
- Better design: exception handling is planned at higher levels of the application.

### Example with `throws`
```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class ThrowsExample {
    public static void main(String[] args) {
        try {
            readFile("example.txt");
        } catch (IOException e) {
            System.out.println("Error reading file: " + e.getMessage());
        }
    }

    public static void readFile(String filename) throws IOException {
        FileReader fileReader = new FileReader(filename);
        BufferedReader bufferedReader = new BufferedReader(fileReader);
        System.out.println(bufferedReader.readLine());
        bufferedReader.close();
    }
}
```
If the file does not exist, `FileReader` throws an `IOException`, which is handled by the caller.

## Summary
- Java uses exceptions to provide error-handling capabilities.
- Any code can throw an exception if a runtime error occurs.
- `try-catch` blocks handle those exceptions and keep programs running.
- Multiple `catch` blocks let you handle different exceptions separately.
- Using multiple `try-catch` blocks improves clarity, specificity, and organization.
- The `throws` keyword declares that a method may pass exceptions to its caller.
