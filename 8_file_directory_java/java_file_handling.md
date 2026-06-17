# Java File Handling

## What is file handling?
- File handling enables reading from and writing to files on a computer.
- In Java, file handling is done using classes from the `java.io` package.
- It provides persistent storage so data is not lost when the program ends.
- Common uses include storing data between program runs, sharing data between programs/users, and reading configuration settings.

## Key concepts
- The `File` class represents a file or directory path.
- `File` can create, delete, and inspect files or directories, but it does not itself read or write file contents.
- A Java program starts execution in the `main` method of a class.

## Example: checking if a file exists
```java
import java.io.File;

public class FileExample {
    public static void main(String[] args) {
        File file = new File("example.txt");
        if (file.exists()) {
            System.out.println("File Exists");
        } else {
            System.out.println("FileDoesNotExist");
        }
    }
}
```
- `new File("example.txt")` creates a `File` object representing the path.
- The `File` object does not create the actual file by itself.
- `exists()` checks whether the file exists.

## Writing to a file
- Writing saves data from the program to storage so it persists after the application closes.
- Java uses classes like `FileWriter` and `BufferedWriter` for writing text files.
- `FileWriter` writes characters to a file and will create the file if it does not exist.
- Wrapping `FileWriter` with `BufferedWriter` makes writing more efficient, especially for larger data.

Example:
```java
import java.io.BufferedWriter;
import java.io.FileWriter;
import java.io.IOException;

public class WriteFileExample {
    public static void main(String[] args) {
        try {
            FileWriter fw = new FileWriter("output.txt");
            BufferedWriter bw = new BufferedWriter(fw);
            bw.write("Hello, Java file handling!");
            bw.newLine();
            bw.close();
        } catch (IOException e) {
            System.out.println("An error occurred: " + e.getMessage());
        }
    }
}
```
- Use a `try` block to catch `IOException` during writing.
- Close the writer to save the data and release system resources.

## Reading from a file
- Reading retrieves data stored in a file so the program can process it.
- Java file reading classes include `FileReader` and `BufferedReader`.
- `BufferedReader` improves efficiency and allows reading lines of text easily.

Example:
```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class ReadFileExample {
    public static void main(String[] args) {
        try {
            FileReader fr = new FileReader("input.txt");
            BufferedReader br = new BufferedReader(fr);
            String line;
            while ((line = br.readLine()) != null) {
                System.out.println(line);
            }
            br.close();
        } catch (IOException e) {
            System.out.println("An error occurred: " + e.getMessage());
        }
    }
}
```
- Use `readLine()` in a loop to read file content line by line.
- Close the reader when finished.

## Comparing file handling classes
- `File`: represents a file or directory path and can create/delete files or directories.
- `FileReader`: reads character streams from files; suitable for simple text input.
- `BufferedReader`: wraps `FileReader` to read text efficiently, especially for larger files.
- `FileWriter`: writes character streams to files; good for simple text output.
- `BufferedWriter`: wraps `FileWriter` and improves writing performance for larger data.

## Summary
- File handling is essential for persistent data storage beyond program runtime.
- The `java.io` package provides the main classes for file handling in Java.
- Use `File` for file path management, `FileWriter`/`BufferedWriter` for writing, and `FileReader`/`BufferedReader` for reading.
- Always handle exceptions and close streams or writers to release resources.
