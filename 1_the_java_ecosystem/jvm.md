# Java Virtual Machine (JVM)

## What is the JVM?

The Java Virtual Machine (JVM) is the specification and implementation that executes Java bytecode. The JVM provides a platform-independent execution environment: Java source -> compiled bytecode (.class) -> JVM executes bytecode on any platform with a conforming JVM.

Common JVM implementations include HotSpot (OpenJDK), Eclipse OpenJ9, and GraalVM (including a JVM and AOT compilation options).

## Core responsibilities

- Class loading and linking
- Bytecode verification
- Memory management: heap, stack, method area, and native memory
- Garbage collection (GC)
- Execution engine: interpreter + Just-In-Time (JIT) compiler
- Thread and synchronization support

## JVM architecture (high level)

- Class Loader Subsystem: loads .class files and resolves dependencies.
- Runtime Data Areas:
  - Heap: objects and arrays
  - Java stacks: frames for method invocations
  - Method area / metaspace: class metadata and static fields
  - Native method stacks and PC registers
- Execution Engine: interpreter, JIT compiler, and garbage collector

## How Java runs (simple flow)

1. Write Java source: `Main.java`
2. Compile: `javac Main.java` -> `Main.class` (bytecode)
3. Run: `java Main` -> JVM loads `Main.class`, verifies, links, and executes

## Performance features

- HotSpot JIT compiles frequently executed bytecode into native code for speed
- Tiered compilation balances startup time and peak performance
- GC algorithms (G1, ZGC, Shenandoah) trade throughput, pause times, and footprint

## Native-image and alternatives

- GraalVM can produce an ahead-of-time (AOT) native image which does not require a JVM at runtime but is not a drop-in replacement for all workloads.

## Practical notes

- The JVM is responsible for portability: compile once, run anywhere with a compatible JVM.
- When debugging runtime issues, check JVM flags (e.g., `-Xmx`, `-XX:+UseG1GC`) and logs.

Further reading: see the JDK and JRE pages for how JVM is packaged and distributed.