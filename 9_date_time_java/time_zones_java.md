# Time Zones in Java

## Why time zones matter
- Time zones ensure users in different parts of the world see the correct local time.
- They are essential for scheduling meetings, logging events, and maintaining consistent timestamps.
- Without time zone handling, global applications can produce confusing or incorrect times.
- A time zone is defined by its offset from Coordinated Universal Time (UTC), for example `UTC-5`.

## Key Java time zone classes
- `ZoneId`: represents a time zone identifier like `America/New_York` or `Europe/London`.
- `ZonedDateTime`: combines date, time, and a time zone to represent a specific moment in a region.
- `ZoneOffset`: defines a fixed offset from UTC, useful for precise calculations.
- `OffsetDateTime`: stores a date-time with an offset from UTC, without a full time zone rule set.

## Using `ZoneId`
- Use `ZoneId.of("America/New_York")` to create a specific zone identifier.
- `ZoneId` lets you work with region-based time zone rules.

## Using `ZonedDateTime`
- `ZonedDateTime` represents a date and time in a specific time zone.
- Use `ZonedDateTime.now(zoneId)` to get the current date/time in that zone.
- It is ideal for applications that need the actual local time in different regions.

Example:
```java
import java.time.ZoneId;
import java.time.ZonedDateTime;

public class ZonedDateTimeExample {
    public static void main(String[] args) {
        ZoneId newYorkZone = ZoneId.of("America/New_York");
        ZonedDateTime zdt = ZonedDateTime.now(newYorkZone);
        System.out.println("New York time: " + zdt);
    }
}
```

## Using `ZoneOffset`
- `ZoneOffset` defines a fixed offset from UTC, such as `UTC-05:00`.
- It is useful in systems that require exact offset-based calculations.
- Unlike `ZoneId`, it does not contain daylight saving rules.

## Using `OffsetDateTime`
- `OffsetDateTime` stores date-time information with an offset.
- It is useful when the exact timezone region is not needed, only the offset from UTC.
- This can be useful for database storage or interchange formats.

## Converting meeting times across time zones
- Use a base time in UTC and convert it to each participant’s local zone.
- `withZoneSameInstant()` keeps the absolute instant the same while displaying the equivalent local time.
- This is important for scheduling global events without changing the actual moment in time.

Example:
```java
import java.time.ZonedDateTime;
import java.time.ZoneId;
import java.time.format.DateTimeFormatter;

public class TimeZoneConversionExample {
    public static void main(String[] args) {
        ZonedDateTime meetingUtc = ZonedDateTime.parse("2025-10-01T14:00:00Z");
        String[] zones = {"America/New_York", "Europe/London", "Asia/Kolkata", "Australia/Sydney"};
        DateTimeFormatter formatter = DateTimeFormatter.ofPattern("yyyy-MM-dd HH:mm z");

        System.out.println("Meeting time in UTC: " + meetingUtc.format(formatter));

        for (String zoneIdString : zones) {
            ZoneId zone = ZoneId.of(zoneIdString);
            ZonedDateTime localTime = meetingUtc.withZoneSameInstant(zone);
            System.out.println(zoneIdString + ": " + localTime.format(formatter));
        }
    }
}
```

## Summary
- Time zones are critical for global applications and accurate scheduling.
- Java provides `ZoneId`, `ZonedDateTime`, `ZoneOffset`, and `OffsetDateTime` to handle time zones.
- `ZoneId` is for regional identifiers, `ZonedDateTime` combines date and zone, `ZoneOffset` is a fixed UTC offset, and `OffsetDateTime` adds offset-aware date-time storage.
- Use consistent timestamp formatting to avoid confusion and maintain data accuracy across regions.
