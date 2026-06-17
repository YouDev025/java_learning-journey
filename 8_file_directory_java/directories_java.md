# Managing Directories in Java

## Why directories matter
- Directories organize files and folders so data remains easy to find and manage.
- Without good directory management, files can become scattered and hard to navigate.
- Directories help applications handle large amounts of data cleanly and reduce errors.
- They also support application configuration and file sharing across environments.

## Directory operations in Java
- Java provides directory handling APIs in both `java.io` and `java.nio.file`.
- `java.io.File` can create directories, list contents, and delete directories.
- `java.nio.file` offers newer APIs with better performance and richer error handling.

## Creating directories with `File`
- Use `new File(path)` to represent a directory path.
- `mkdir()` creates a single directory.
- `mkdirs()` creates the directory and any missing parent directories.
- Always check whether a directory already exists before creating it.

Example:
```java
import java.io.File;

public class CreateDirectoryExample {
    public static void main(String[] args) {
        File dir = new File("docs/reports");
        if (!dir.exists()) {
            if (dir.mkdirs()) {
                System.out.println("Directory created successfully.");
            } else {
                System.out.println("Failed to create directory.");
            }
        } else {
            System.out.println("Directory already exists.");
        }
    }
}
```

## Listing directory contents
- Use `list()` to retrieve file and directory names as a string array.
- Always check for `null` to avoid `NullPointerException` when the directory is empty or missing.

Example:
```java
import java.io.File;

public class ListDirectoryContents {
    public static void main(String[] args) {
        File dir = new File("docs");
        String[] items = dir.list();
        if (items != null) {
            for (String name : items) {
                System.out.println(name);
            }
        } else {
            System.out.println("Directory does not exist or is not accessible.");
        }
    }
}
```

## Deleting directories with `File`
- A directory must be empty before it can be deleted.
- Use `exists()` to verify the directory exists.
- Use `delete()` and check the returned boolean to confirm success.

Example:
```java
import java.io.File;

public class DeleteDirectoryExample {
    public static void main(String[] args) {
        File dir = new File("docs/reports");
        if (dir.exists()) {
            if (dir.delete()) {
                System.out.println("Directory deleted successfully.");
            } else {
                System.out.println("Failed to delete directory. It may not be empty.");
            }
        } else {
            System.out.println("Directory does not exist.");
        }
    }
}
```

## Using Java NIO for directories
- Java NIO (`java.nio.file`) provides modern directory and file handling.
- `Path` represents a file or directory path.
- `Files.createDirectories(path)` creates the directory and missing parent directories.
- NIO throws `IOException` for failures, enabling better error handling.

Example:
```java
import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;

public class NioCreateDirectoriesExample {
    public static void main(String[] args) {
        Path path = Paths.get("docs/reports");
        try {
            Files.createDirectories(path);
            System.out.println("Directory created successfully using NIO.");
        } catch (IOException e) {
            System.out.println("Failed to create directory: " + e.getMessage());
        }
    }
}
```

## Practical directory use case
- A document management system can create separate folders for reports, invoices, and letters.
- Users can list contents to see what files and subdirectories are available.
- Empty directories can be deleted when no longer needed.
- Proper directory handling keeps application data organized and easier to maintain.

## Summary
- Directories are containers for files and other directories.
- Java offers both `java.io.File` and `java.nio.file` for directory management.
- Use `mkdirs()` or `Files.createDirectories()` to ensure parent directories are created.
- Use `list()` to inspect directory contents and `delete()` to remove empty directories.
- Good directory management is essential for efficient file organization and error-free applications.
