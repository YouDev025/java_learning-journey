# Understanding Polymorphism in Java

## What is Polymorphism?

- Polymorphism allows objects to share the same interface while exhibiting different behavior based on their specific implementation.
- It is essential for flexibility and reusability in object-oriented programming.
- A single reference type can refer to objects of multiple types, and the behavior changes depending on the actual object.

## Polymorphism Use Cases

- Code reuse with generic methods and classes.
- Decoupling implementation from interface.
- Dynamic behavior in frameworks and libraries.
- Easier maintenance when extending functionality.

## Types of Polymorphism

### Compile Time Polymorphism (Method Overloading)

- Also called static polymorphism.
- Occurs when multiple methods in the same class share the same name but differ in parameter types or counts.
- The compiler decides which method to call based on the argument list.

```java
class MathOperations {
    int add(int a, int b) {
        return a + b;
    }

    int add(int a, int b, int c) {
        return a + b + c;
    }

    double add(double a, double b) {
        return a + b;
    }
}

public class Main {
    public static void main(String[] args) {
        MathOperations ops = new MathOperations();
        System.out.println(ops.add(2, 3));
        System.out.println(ops.add(1, 2, 3));
        System.out.println(ops.add(2.5, 3.5));
    }
}
```

### Runtime Polymorphism (Method Overriding)

- Also called dynamic polymorphism.
- Happens when a subclass provides its own implementation of a method defined in the superclass.
- The actual method invoked is resolved at runtime based on the object's actual type.

```java
class Animal {
    void sound() {
        System.out.println("Animal makes a sound.");
    }
}

class Dog extends Animal {
    @Override
    void sound() {
        System.out.println("Dog barks.");
    }
}

class Cat extends Animal {
    @Override
    void sound() {
        System.out.println("Cat meows.");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal myAnimal = new Dog();
        myAnimal.sound();

        myAnimal = new Cat();
        myAnimal.sound();
    }
}
```

## Virtual Methods

- In Java, all non-static methods are virtual by default.
- Virtual methods can be overridden in subclasses.
- This allows dynamic method resolution at runtime, so the actual object type determines which method is executed.

## Why Polymorphism Matters

- It lets generic code work with different object types.
- It supports loose coupling by separating interface from implementation.
- It allows behavior to change at runtime without modifying client code.
- It is commonly used in framework design, plugin systems, and data-driven applications.

## Summary

- Polymorphism enables objects to behave differently while sharing a common interface.
- Compile time polymorphism is implemented through method overloading.
- Runtime polymorphism is achieved through method overriding.
- Polymorphism improves code reuse, decoupling, maintenance, and flexibility.
