# Parsing Dates in Java

## What is date parsing?
- Parsing converts a string into a structured date or time object.
- It helps Java understand raw text like "21/02/2030" as a date.
- The `DateTimeFormatter` class defines how the date string is interpreted.
- Parsing is useful for user input, configuration data, and processing text.

## Parsing a simple date string
- Import `LocalDate` and `DateTimeFormatter` from `java.time`.
- Create a formatter with the pattern matching the input string.
- Use `LocalDate.parse()` to convert the string into a `LocalDate`.

Example:
```java
import java.time.LocalDate;
import java.time.format.DateTimeFormatter;

public class ParseDateExample {
    public static void main(String[] args) {
        String dateString = "2030-02-21";
        DateTimeFormatter formatter = DateTimeFormatter.ofPattern("yyyy-MM-dd");
        LocalDate date = LocalDate.parse(dateString, formatter);
        System.out.println(date);
    }
}
```

## Parsing custom formats
- You can customize the pattern to match different formats.
- For example, parse `21/02/2030` using `dd/MM/yyyy`.

Example:
```java
import java.time.LocalDate;
import java.time.format.DateTimeFormatter;

public class CustomParseExample {
    public static void main(String[] args) {
        String dateString = "21/02/2030";
        DateTimeFormatter formatter = DateTimeFormatter.ofPattern("dd/MM/yyyy");
        LocalDate date = LocalDate.parse(dateString, formatter);
        System.out.println(date);
    }
}
```

## Parsing date and time
- Use `LocalDateTime` when the string contains both date and time.
- Define a formatter with both date and time patterns.

## Extracting dates from text
- You can parse dates from strings containing text by extracting the date substring first.
- Use string methods or regular expressions to isolate the date text.

Example:
```java
import java.time.LocalDate;
import java.time.format.DateTimeFormatter;

public class ExtractDateExample {
    public static void main(String[] args) {
        String sentence = "The scheduled date is 2030-02-21.";
        String dateSubstring = sentence.substring(sentence.indexOf("is") + 3, sentence.length() - 1);
        DateTimeFormatter formatter = DateTimeFormatter.ofPattern("yyyy-MM-dd");
        LocalDate date = LocalDate.parse(dateSubstring, formatter);
        System.out.println(date);
    }
}
```

## Parsing multiple dates from a string
- Split the text using delimiters like commas and conjunctions.
- Trim each part and parse valid date segments.
- Use error handling to manage invalid inputs.

Example:
```java
import java.time.LocalDate;
import java.time.format.DateTimeFormatter;

public class ParseMultipleDatesExample {
    public static void main(String[] args) {
        String text = "21/02/2030, 15/03/2031 and 10/04/2032";
        DateTimeFormatter formatter = DateTimeFormatter.ofPattern("dd/MM/yyyy");
        String[] parts = text.split(",| and ");
        for (String part : parts) {
            try {
                LocalDate date = LocalDate.parse(part.trim(), formatter);
                System.out.println(date);
            } catch (Exception e) {
                System.out.println("Invalid date: " + part.trim());
            }
        }
    }
}
```

## Parsing mixed-content strings with regex
- Identify date-like patterns using regex.
- Parse any words that match the expected date format.
- This is helpful when dates appear alongside other text.

## Summary
- Parsing converts raw text into Java date objects.
- `DateTimeFormatter` defines the expected date/time pattern.
- Use `LocalDate.parse()` and `LocalDateTime.parse()` for structured results.
- Extract dates from sentences or mixed content before parsing.
- Custom patterns and error handling improve robustness.
