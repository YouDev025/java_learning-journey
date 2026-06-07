# Java Functions & Methods
> *A concise, practical reference for implementing methods in Java*

---

## Table of Contents
1. [Core Concepts](#core-concepts)
2. [Method Anatomy](#method-anatomy)
3. [Types of Methods](#types-of-methods)
4. [Parameters & Return Types](#parameters--return-types)
5. [Method Overloading & Overriding](#method-overloading--overriding)
6. [Recursion](#recursion)
7. [Scope & Identifiers](#scope--identifiers)
8. [Javadoc](#javadoc)
9. [Best Practices](#best-practices)
10. [Quick Reference](#quick-reference)

---

## Core Concepts

| Term | Definition |
|------|-----------|
| **Function** | A named block of code that takes inputs, performs a task, and may return a value. |
| **Method** | A function bound to a class; can access instance fields and participate in OOP. |

> In Java, **all functions are methods** — they must live inside a class.

---

## Method Anatomy

```java
//  modifier  return-type  name    parameters
    public    static int   add  (int a, int b) {
        return a + b;   // body
    }
```

| Part | Purpose |
|------|---------|
| **Modifier** | Access/scope control (`public`, `private`, `static`, …) |
| **Return type** | Type of value returned; `void` if nothing is returned |
| **Name** | Verb-based, describes the action (e.g. `calculateArea`) |
| **Parameters** | Typed inputs; empty `()` if none required |
| **Body** | Logic block; use `return` to send a value back |

---

## Types of Methods

### Static Method
Belongs to the **class**; called without an instance.

```java
public class MathUtils {
    public static int add(int a, int b) {
        return a + b;
    }
}

// Call directly on the class
int sum = MathUtils.add(5, 3);  // 8
```

### Instance Method
Belongs to an **object**; requires instantiation.

```java
public class Calculator {
    public double multiply(double x, double y) {
        return x * y;
    }
}

// Call on an instance
Calculator calc = new Calculator();
double product = calc.multiply(2.5, 4.0);  // 10.0
```

### Void Method
Performs an action but **returns no value**.

```java
public void greet(String name, int age) {
    System.out.println("Hello " + name + ", you are " + age + " years old.");
}

greet("Alice", 30);
// → Hello Alice, you are 30 years old.
```

---

## Parameters & Return Types

```java
// Multiple parameters — rectangle area
public double area(double width, double height) {
    return width * height;
}
area(4.5, 3.0);  // → 13.5

// No parameters, no return value
public void printMessage() {
    System.out.println("Hello World");
}

// Primitive vs. reference parameters
public void increment(int n) { n++; }          // n is a copy — caller unchanged
public void clear(List<Integer> list) { list.clear(); } // list is a reference — caller affected
```

> **Tip:** Avoid mutating input objects unless that is the explicit intent.

---

## Method Overloading & Overriding

### Overloading — same name, different signatures (same class)

```java
public class Display {
    public void show(int n)    { System.out.println(n); }
    public void show(String s) { System.out.println(s); }
    public void show(double d) { System.out.println(d); }
}

Display d = new Display();
d.show(42);       // → 42
d.show("hello");  // → hello
d.show(3.14);     // → 3.14
```

The **compiler** picks the correct method based on the argument types at compile time.

### Overriding — redefine inherited behaviour (subclass)

```java
class Animal {
    public void speak() {
        System.out.println("...");
    }
}

class Dog extends Animal {
    @Override
    public void speak() {
        System.out.println("Woof!");
    }
}

Animal a = new Dog();
a.speak();  // → Woof!   (runtime polymorphism)
```

> Always use `@Override` — it lets the compiler catch signature mismatches early.

---

## Recursion

A method that **calls itself**. Every recursive method needs:
1. A **base case** that stops the recursion.
2. A **recursive case** that moves toward the base case.

```java
public int factorial(int n) {
    if (n <= 1) return 1;          // base case
    return n * factorial(n - 1);   // recursive case
}

factorial(5);  // → 120
```

```
factorial(5)
  └─ 5 * factorial(4)
         └─ 4 * factorial(3)
                └─ 3 * factorial(2)
                       └─ 2 * factorial(1)
                              └─ 1  ✓ base case
```

> ⚠️ Without a base case, you get a `StackOverflowError`.

---

## Scope & Identifiers

| Scope | Where declared | Accessible from |
|-------|---------------|-----------------|
| **Local** | Inside a method or block | Only within that block |
| **Instance** | In the class (no `static`) | All instance methods of that object |
| **Static (class)** | In the class with `static` | All methods of the class; shared across instances |

```java
public class Counter {
    private static int classCount = 0;  // static scope
    private int id;                     // instance scope

    public Counter() {
        classCount++;
        int temp = classCount;  // local scope — gone after constructor exits
        this.id = temp;
    }
}
```

---

## Javadoc

Document **every public method** with a Javadoc comment directly above it.

```java
/**
 * Calculates the square of an integer value.
 *
 * @param x  the value to square
 * @return   x multiplied by itself
 */
public static int square(int x) {
    return x * x;
}
```

| Tag | Purpose |
|-----|---------|
| `@param name desc` | Documents an input parameter |
| `@return desc` | Documents the return value |
| `@throws ExType desc` | Documents a checked or notable exception |
| `@see ClassName#method` | Cross-references related methods |

---

## Best Practices

- ✅ **Single Responsibility** — one method does one thing.
- ✅ **Descriptive names** — `calculateMonthlyInterest()` beats `calc()`.
- ✅ **Short & focused** — extract helpers when a method grows beyond ~20 lines.
- ✅ **Immutable parameters** — avoid mutating inputs unless explicitly designed to do so.
- ✅ **Use `@Override`** — always annotate overriding methods.
- ✅ **Javadoc all public API** — especially parameters and return values.
- ❌ **Avoid side effects** in methods that return values.
- ❌ **Don't overload** beyond 2–3 variants; consider a builder or options object instead.

---

## Quick Reference

```java
// Static utility method
public static int add(int a, int b) { return a + b; }

// Instance method
public double multiply(double x, double y) { return x * y; }

// Void method
public void greet(String name, int age) {
    System.out.println("Hello " + name + ", you are " + age);
}

// Overloaded methods
public void show(int n)    { System.out.println(n); }
public void show(String s) { System.out.println(s); }

// Overriding
@Override
public void speak() { System.out.println("Woof!"); }

// Recursive method
public int factorial(int n) {
    if (n <= 1) return 1;
    return n * factorial(n - 1);
}
```

---

*Reference based on standard Java SE. For deeper reading, see the [official Java tutorials](https://docs.oracle.com/javase/tutorial/java/javaOO/methods.html).*