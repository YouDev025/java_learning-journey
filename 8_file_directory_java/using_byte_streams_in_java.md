# Using Byte Streams in Java

## What are byte streams?
- Byte streams move raw bytes of data through the system, similar to a conveyor belt moving materials.
- They handle all types of data including text, images, audio, and video.
- Byte streams are used for reading and writing raw binary data.
- In Java, byte streams are part of the `java.io` package.

## Main byte stream classes
- `InputStream`: abstract superclass for byte input streams.
- `OutputStream`: abstract superclass for byte output streams.
- `FileInputStream`: reads bytes from a file.
- `FileOutputStream`: writes bytes to a file.
- `BufferedInputStream`: buffers input for better performance.
- `BufferedOutputStream`: buffers output for better performance.

## Reading with byte streams
- Use `FileInputStream` to read raw bytes from a file.
- The `read()` method returns one byte at a time.
- When the end of the file is reached, `read()` returns `-1`.
- Bytes can be cast to `char` for text output, but byte streams are not limited to text.
- Always close the stream to free resources, typically in a `finally` block or with try-with-resources.

Example:
```java
import java.io.FileInputStream;
import java.io.IOException;

public class ReadBytesExample {
    public static void main(String[] args) {
        try (FileInputStream fis = new FileInputStream("input.dat")) {
            int b;
            while ((b = fis.read()) != -1) {
                System.out.print((char) b);
            }
        } catch (IOException e) {
            System.out.println("An error occurred: " + e.getMessage());
        }
    }
}
```

## Writing with byte streams
- Use `FileOutputStream` to write raw bytes to a file.
- The `write()` method can write a single byte or a byte array.
- Close the output stream after writing to release resources.

Example:
```java
import java.io.FileOutputStream;
import java.io.IOException;

public class WriteBytesExample {
    public static void main(String[] args) {
        byte[] data = "Hello byte streams".getBytes();
        try (FileOutputStream fos = new FileOutputStream("output.dat")) {
            fos.write(data);
        } catch (IOException e) {
            System.out.println("An error occurred: " + e.getMessage());
        }
    }
}
```

## Copying files with byte streams
- Copying a file uses `FileInputStream` to read bytes and `FileOutputStream` to write bytes.
- Loop until `read()` returns `-1` to detect the end of the source file.
- Close both streams after the copy operation.

## When to use byte streams
- Use byte streams for binary files like images, audio, and video.
- Use them in network programming to transmit binary data over sockets.
- Use them in serialization when converting objects to a byte format.
- Use them when performance is important and raw bytes are needed.

## Byte streams vs. character streams
- Byte streams handle raw binary data.
- Character streams handle text and use character encoding.
- Byte stream base classes: `InputStream` and `OutputStream`.
- Character stream base classes: `Reader` and `Writer`.
- Common byte stream subclasses: `FileInputStream`, `FileOutputStream`.
- Common character stream subclasses: `FileReader`, `FileWriter`.
- Byte streams do not apply encoding; character streams do.
- Byte streams are best for binary formats, while character streams are best for text files.

## Summary
- Byte streams are essential for handling non-text data efficiently in Java.
- They provide classes and methods for reading and writing raw binary data.
- Use byte streams for multimedia applications, binary file processing, network data transfer, and serialization.
- Remember to manage resources by closing streams after use.
