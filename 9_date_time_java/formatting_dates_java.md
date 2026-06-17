# Formatting Dates in Java

## Why date formatting matters
- Dates are used in many applications, such as calendars, logs, and user interfaces.
- Formatting dates makes them readable and meaningful for people.
- Different regions and applications require different date formats.
- Java provides date formatting tools so dates can be displayed and stored correctly.

## Java date/time APIs
- Older classes: `java.util.Date` and `java.util.Calendar`.
- Modern Java date/time handling: `java.time` package.
- `java.time` is more flexible and easier to use for formatting and parsing.

## Core date/time classes
- `LocalDate`: date only (year, month, day).
- `LocalTime`: time only (hour, minute, second).
- `LocalDateTime`: date and time without timezone.
- `ZonedDateTime`: date and time with timezone.

## Formatting with `DateTimeFormatter`
- `DateTimeFormatter` converts date/time objects into strings.
- You define a pattern to control the output format.
- Common patterns include day-month-year, year-month-day, and full weekday/month names.

Example:
```java
import java.time.LocalDate;
import java.time.format.DateTimeFormatter;

public class FormatDateExample {
    public static void main(String[] args) {
        LocalDate today = LocalDate.now();
        DateTimeFormatter formatter = DateTimeFormatter.ofPattern("dd MMMM yyyy");
        String formattedDate = today.format(formatter);
        System.out.println("Formatted Date: " + formattedDate);
    }
}
```

## Common date format patterns
- `dd/MM/yyyy` = 15/05/1990
- `yyyy-MM-dd` = 1990-05-15
- `MMMM d, yyyy` = May 15, 1990
- `EEEE, MMMM d, yyyy` = Tuesday, May 15, 1990

## Use cases for formatted dates
- User interfaces should show friendly, easy-to-read dates.
- Databases often require specific date formats for storage.
- Logs benefit from consistent timestamps for tracing events.
- Different regions use different formats, so formatting helps localize output.

## Example: user input and formatted output
```java
import java.time.LocalDate;
import java.time.format.DateTimeFormatter;
import java.util.Scanner;

public class BirthdayFormatter {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter your name: ");
        String name = scanner.nextLine();

        System.out.print("Enter your birthdate (yyyy-MM-dd): ");
        String inputDate = scanner.nextLine();

        LocalDate birthdate = LocalDate.parse(inputDate);
        DateTimeFormatter formatter = DateTimeFormatter.ofPattern("EEEE, MMMM d, yyyy");
        String formattedBirthdate = birthdate.format(formatter);

        System.out.println("Hello " + name + ", your birthdate is " + formattedBirthdate + ".");
        scanner.close();
    }
}
```

## Choosing the right class
- Use `LocalDate` when you only need a date.
- Use `LocalTime` when you only need a time.
- Use `LocalDateTime` when you need both date and time.
- Use `ZonedDateTime` when timezone information is required.

## Summary
- Date formatting converts a date object into a string using a pattern.
- The `java.time` package and `DateTimeFormatter` are the modern Java tools for formatting dates.
- Format dates for display, storage, or logging to make them useful and consistent.
- Choose the correct date/time class depending on whether you need date-only, time-only, date-time, or timezone support.
