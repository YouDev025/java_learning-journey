# Checked and Runtime Exceptions Compared

## Checked Exceptions

### What are Checked Exceptions?
Checked exceptions are exceptions that are verified by the Java compiler at compile time. The compiler ensures that your code handles these exceptions before it can be successfully compiled. If you do not handle a checked exception, compilation will fail with an error.

### Characteristics
- Must be caught with a `try-catch` block or declared using `throws` in the method signature.
- Represent recoverable conditions such as file not found or network issues.
- Occur due to external factors outside programmer control.

### Example
```java
import java.util.Scanner;
import java.io.File;
import java.io.FileNotFoundException;

public class CheckedExceptionExample {
    public static void main(String[] args) {
        try {
            File file = new File("nonexistentfile.txt");
            Scanner scanner = new Scanner(file);
        } catch (FileNotFoundException e) {
            System.out.println("Error: File not found.");
        }
    }
}
```

### Common Checked Exceptions
- `IOException` — file operations and network communications
- `FileNotFoundException` — when a file cannot be found
- `ClassNotFoundException` — when attempting to dynamically load a class at runtime

### When to Use
- File operations (reading from or writing to files)
- Database connections
- Network communications

## Runtime Exceptions

### What are Runtime Exceptions?
Runtime exceptions are not checked by the compiler at compile time. They occur during program execution and can often be avoided by writing correct code. The Java compiler does not require you to handle or declare runtime exceptions.

### Characteristics
- Do not need to be explicitly caught or declared.
- Usually indicate programming errors such as logic errors or improper API usage.
- Can be prevented by fixing the code.

### Example
```java
public class RuntimeExceptionExample {
    public static void main(String[] args) {
        try {
            int result = 10 / 0;
        } catch (ArithmeticException e) {
            System.out.println("Error: Cannot divide by zero.");
        }
    }
}
```

### Common Runtime Exceptions
- `NullPointerException` — when trying to access a null object reference
- `ArithmeticException` — invalid arithmetic operations like divide by zero
- `ArrayIndexOutOfBoundsException` — accessing array indices outside valid range

### When to Use
- Arithmetic errors (divide by zero, overflow)
- Null pointer access errors
- Array index out-of-bounds errors

## Comparison

| Aspect | Checked Exceptions | Runtime Exceptions |
|--------|-------------------|-------------------|
| **Compile Time Check** | Checked by compiler; must be handled | Not checked by compiler |
| **Handling Requirement** | Mandatory (`try-catch` or `throws`) | Optional |
| **Represents** | Recoverable conditions from external events | Programming errors |
| **Examples** | `IOException`, `FileNotFoundException`, `ClassNotFoundException` | `NullPointerException`, `ArithmeticException`, `ArrayIndexOutOfBoundsException` |
| **Prevention** | Handle at compile time | Fix logic in code |

## Benefits of Checked Exceptions

### Compile Time Safety
Checked exceptions require developers to handle potential error scenarios at compile time, reducing the chances of unhandled exceptions during execution, leading to more stable applications.

### Recoverable Errors
Checked exceptions typically represent conditions that a program can anticipate and recover from, such as file not found or invalid user input, encouraging graceful error handling.

### Clear API Contracts
By declaring checked exceptions in method signatures, APIs communicate what issues may arise and what needs to be handled, leading to better code practices.

### Promotes Defensive Programming
Using checked exceptions encourages developers to think proactively about error handling, resulting in more robust and resilient software.

## Benefits of Runtime Exceptions

### Simplicity
Runtime exceptions do not require explicit handling, simplifying the code. Developers can focus on main logic without mandatory error handling for every potential issue.

### Indication of Programming Errors
Runtime exceptions usually indicate bugs or logical errors in the code (null pointer access, array index out of bounds), allowing developers to catch and fix issues during development.

### Performance
Since runtime exceptions do not require checked handling, they can lead to cleaner and more efficient code, especially in performance-critical sections.

### Control Flow
Runtime exceptions can signal problems that should not occur if program logic is correct, allowing developers to implement custom logic for handling unexpected conditions without cluttering code with error-handling structures.

## When to Use Which?

**Use Checked Exceptions when:**
- Handling external events outside programmer control (missing files, network failures)
- You want to ensure error recovery mechanisms are in place at compile time
- Creating libraries or APIs with clear error contracts

**Use Runtime Exceptions when:**
- Indicating programming bugs or logic errors
- The error could have been prevented by correct code
- You want simpler code without mandatory error handling

## Summary
- Checked exceptions are verified at compile time and must be handled.
- Runtime exceptions are not checked and indicate programming errors.
- Checked exceptions help with compile-time safety and recoverable error handling.
- Runtime exceptions provide simplicity and indicate bugs that should be fixed in code.
- Both play important roles in a well-designed exception-handling strategy.
