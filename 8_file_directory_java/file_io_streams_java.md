# File I/O Streams in Java

## Why file handling matters
- File handling lets developers read from and write to files on a computer.
- Java uses classes from the `java.io` package for file input and output.
- File handling provides persistence, so data remains after the program ends.
- Without persistence, application data would be discarded when the program closes.
- File handling also enables sharing data between programs and users, and helps manage configuration files across environments.

## Using the `File` class
- The `File` class represents a file or directory path.
- It provides methods to create, delete, and check properties like existence.
- The `File` class does not perform file content operations itself.
- Example:
```java
import java.io.File;

public class FileExample {
    public static void main(String[] args) {
        File myFile = new File("example.txt");
        if (myFile.exists()) {
            System.out.println("file exists");
        } else {
            System.out.println("file does not exist");
        }
    }
}
```
- `new File("example.txt")` creates an object representing the path.
- `exists()` checks whether the file exists on disk.

## Writing data to files
- Use `FileWriter` and `BufferedWriter` to write text to files.
- `FileWriter` creates the file if it does not exist and overwrites it if it does.
- `BufferedWriter` wraps `FileWriter` to improve write efficiency.
- Use a try-catch block to handle `IOException` during writing.

Example:
```java
import java.io.BufferedWriter;
import java.io.FileWriter;
import java.io.IOException;

public class WriteToFile {
    public static void main(String[] args) {
        try {
            FileWriter writer = new FileWriter("output.txt");
            BufferedWriter bufferedWriter = new BufferedWriter(writer);
            bufferedWriter.write("Hello, World!");
            bufferedWriter.newLine();
            bufferedWriter.close();
        } catch (IOException e) {
            System.out.println("An error occurred: " + e.getMessage());
        }
    }
}
```
- Always close the writer to save data and release resources.
- Handle exceptions in the `catch` block and print error messages if needed.

## Reading data from files
- Use `FileReader` and `BufferedReader` to read text data line by line.
- `FileReader` reads characters from a file.
- `BufferedReader` wraps `FileReader` for efficient reading.
- Read lines in a loop until `readLine()` returns `null`.
- Close the reader when finished.

Example:
```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class ReadFromFile {
    public static void main(String[] args) {
        try {
            FileReader reader = new FileReader("output.txt");
            BufferedReader bufferedReader = new BufferedReader(reader);
            String line;
            while ((line = bufferedReader.readLine()) != null) {
                System.out.println(line);
            }
            bufferedReader.close();
        } catch (IOException e) {
            System.out.println("An error occurred: " + e.getMessage());
        }
    }
}
```
- Use a try-catch block to handle file reading errors.
- Print relevant messages if an exception occurs.

## Summary
- Java file I/O uses the `java.io` package to work with files and directories.
- `File` represents file paths and checks file properties, while reader/writer classes perform actual I/O.
- Writing uses `FileWriter` and `BufferedWriter`; reading uses `FileReader` and `BufferedReader`.
- Proper resource management and exception handling are essential for robust file handling.
