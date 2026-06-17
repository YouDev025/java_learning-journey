# Java Date and Time Classes

## Why date and time management is required
- Managing dates and times is common in software development.
- Use cases include calendar applications, logging events, and displaying current date/time.
- Date/time handling is essential for scheduling, auditing, and time-based application behavior.
- Java uses the `java.time` package for modern date and time handling.

## Core Java date/time classes
- `LocalDate`: represents a date in year-month-day format.
- `LocalTime`: represents a time of day in hours, minutes, seconds, and nanoseconds.
- `LocalDateTime`: combines both date and time without timezone information.
- `ZonedDateTime`: includes date, time, and timezone information.

## LocalDate
- `LocalDate` represents only the date.
- It has no time or timezone component.
- Ideal for birthdays, holidays, or any date-only values.

Example:
```java
import java.time.LocalDate;

public class LocalDateExample {
    public static void main(String[] args) {
        LocalDate today = LocalDate.now();
        System.out.println("Today's Date: " + today);
    }
}
```

## LocalTime
- `LocalTime` represents the time of day.
- It does not include date or timezone information.
- Useful for alarms, timers, and daily time-only values.

Example:
```java
import java.time.LocalTime;

public class LocalTimeExample {
    public static void main(String[] args) {
        LocalTime now = LocalTime.now();
        System.out.println("Current Time: " + now);
    }
}
```

## LocalDateTime
- `LocalDateTime` combines date and time.
- It does not have timezone information.
- Useful for local meeting schedules or timestamped events in one timezone.

Example:
```java
import java.time.LocalDateTime;

public class LocalDateTimeExample {
    public static void main(String[] args) {
        LocalDateTime currentDateTime = LocalDateTime.now();
        System.out.println("Current Date and Time: " + currentDateTime);
    }
}
```

## ZonedDateTime
- `ZonedDateTime` includes date, time, and timezone.
- It is useful for global schedules, airline flights, and cross-timezone events.
- It provides timezone-aware date/time values.

Example:
```java
import java.time.ZonedDateTime;

public class ZonedDateTimeExample {
    public static void main(String[] args) {
        ZonedDateTime zonedNow = ZonedDateTime.now();
        System.out.println("Current Date, Time, and Zone: " + zonedNow);
    }
}
```

## Summary
- Java date and time handling is provided by the `java.time` package.
- Use `now()` on date/time classes to retrieve the current system value.
- `LocalDate` is for dates only, `LocalTime` is for time only.
- `LocalDateTime` is for local date and time without timezone.
- `ZonedDateTime` is for date and time with timezone awareness.
- Use descriptive output with `System.out.println` to display class values clearly.
