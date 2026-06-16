# Encapsulation in Java

This note explains encapsulation and how Java uses access modifiers to protect data.

## What is Encapsulation?

- Encapsulation bundles data (attributes) and methods (functions) into a single class.
- It hides internal details and exposes only what is necessary.
- It ensures data is accessed and modified only through controlled methods.

## Why Encapsulation Matters

- Provides control over how data is used.
- Makes code easier to update and maintain.
- Improves security by protecting sensitive data.
- Helps prevent unauthorized access and incorrect usage.

## Encapsulation in Action

Imagine a coffee machine:

- You add water and coffee grounds.
- You press a button and wait for coffee.
- You do not need to know how the machine works internally.

In Java, the machine is like a class, and you interact only with the public interface.

## Access Modifiers and Encapsulation

Access modifiers determine visibility of class members.

- `private`
  - Accessible only inside the same class.
  - Used to hide data from other classes.
- `public`
  - Accessible from any class, anywhere in the program.
  - Used for methods that should be available globally.
- `protected`
  - Accessible within the same package and by subclasses.
  - Useful for controlled access in inheritance.
- Default (no modifier)
  - Accessible only within the same package.

## Java Encapsulation Example

A common encapsulation pattern:

- Class stores private data fields.
- Constructor initializes those fields.
- Getter methods provide read access.
- Setter methods provide controlled write access.
- Setters can validate input before changing data.

Example behavior:

- `Person` class has private `name` and `age`.
- `getName()` and `getAge()` return values safely.
- `setName()` and `setAge()` update values with validation.
- `setAge()` can reject negative ages to enforce rules.

```java
public class Person {
    private String name;
    private int age;

    public Person(String name, int age) {
        this.name = name;
        setAge(age);
    }

    public String getName() {
        return name;
    }

    public int getAge() {
        return age;
    }

    public void setName(String name) {
        this.name = name;
    }

    public void setAge(int age) {
        if (age < 0) {
            throw new IllegalArgumentException("Age cannot be negative");
        }
        this.age = age;
    }
}

Person alice = new Person("Alice", 30);
System.out.println(alice.getName() + " is " + alice.getAge() + " years old.");
```

## Applications of Encapsulation

Encapsulation is useful in many contexts:

- Banking systems: protect account details and transactions.
- API development: expose clean methods while hiding implementation details.
- Stateful systems: allow objects to manage internal state safely.
- Large systems: separate complex logic into well-defined interfaces.

Example benefits:

- A car system hides engine management behind simple methods like `start()`.
- A game can keep player and inventory details hidden while allowing interaction.

## Summary

- Encapsulation bundles attributes and methods into a class.
- It restricts direct access to data.
- It improves security, flexibility, and maintainability.
- Java uses `private`, `public`, `protected`, and default access modifiers to enforce encapsulation.
