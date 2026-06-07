# Java Runtime Environment (JRE)

## What is the JRE?

The Java Runtime Environment (JRE) is a distribution that contains a JVM implementation plus the set of core libraries needed to run Java applications. It does not include developer tools like `javac`.

Historically, the JRE was distributed separately from the JDK for end users; with modularization and distribution changes since Java 9, the separate JRE download is less emphasized and many runtimes are delivered as part of the JDK or as custom images created by `jlink`.

## What the JRE provides

- A JVM implementation (HotSpot, OpenJ9, etc.)
- Core Java class libraries (the runtime API)
- Runtime configuration files and startup scripts

## When to use a JRE

- For machines that only need to run Java applications (end-user desktops, servers where only runtime is needed).
- Use a minimal runtime image (via `jlink`) when you want a smaller footprint for containers or embedded systems.

## Practical notes

- Many vendors now recommend shipping a tailored runtime image built with `jlink` instead of depending on a system JRE.
- The JRE does not contain tools for compiling sources. For development, always use a JDK.

Check runtime version with `java -version`.