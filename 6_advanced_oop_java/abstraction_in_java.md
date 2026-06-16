# Applying Abstraction in Java

## What is Abstraction?

- Abstraction hides unnecessary implementation details and exposes only the essential features.
- It simplifies complex systems and helps developers focus on what matters.
- Java achieves abstraction using interfaces and abstract classes.

## Why Abstraction Matters

- Simplifies system interaction by hiding the internal workings.
- Makes code easier to understand, use, and maintain.
- Promotes code reusability and flexibility.
- Supports polymorphism by allowing objects to be treated as instances of their parent type.

## Interfaces in Java

- An interface is a reference type that defines a contract for classes.
- Interfaces can contain abstract methods, default methods, static methods, and nested types.
- They cannot have instance fields or constructors.
- Methods in interfaces are abstract by default and must be implemented by implementing classes.
- Interfaces support multiple inheritance, so a class can implement more than one interface.
- All interface methods are implicitly public.

### Example: Animal Interface

```java
interface Animal {
    void sound();
}

class Dog implements Animal {
    @Override
    public void sound() {
        System.out.println("Dog barks.");
    }
}

class Cat implements Animal {
    @Override
    public void sound() {
        System.out.println("Cat meows.");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal dog = new Dog();
        Animal cat = new Cat();
        dog.sound();
        cat.sound();
    }
}
```

## Abstract Classes in Java

- An abstract class cannot be instantiated directly.
- It can contain both abstract methods and concrete methods.
- Abstract methods must be implemented by subclasses.
- Abstract classes are useful for sharing common behavior and enforcing required methods.
- A class can extend only one abstract class.

### Example: Shape Abstract Class

```java
abstract class Shape {
    abstract void draw();

    void display() {
        System.out.println("Displaying shape details.");
    }
}

class Circle extends Shape {
    @Override
    void draw() {
        System.out.println("Drawing a circle.");
    }
}

public class Main {
    public static void main(String[] args) {
        Shape shape = new Circle();
        shape.display();
        shape.draw();
    }
}
```

## Interfaces vs Abstract Classes

- Interfaces define a contract with method signatures and can support multiple inheritance.
- Abstract classes can contain fields, concrete methods, and abstract methods.
- A class can implement multiple interfaces but can extend only one abstract class.
- Interfaces are best for defining capabilities without implementation details.
- Abstract classes are best when related classes need shared behavior and some common implementation.

## Abstraction Benefits

- Simplifies complex systems by hiding implementation details.
- Promotes code reuse through shared behavior in abstract classes.
- Enables different classes to use the same method signatures through interfaces.
- Enhances flexibility and maintainability by isolating implementation changes.
- Supports polymorphism and adaptable design.

## Summary

- Abstraction lets developers focus on essential functionality instead of implementation details.
- Java uses interfaces and abstract classes to implement abstraction.
- Interfaces define contracts and support multiple inheritance.
- Abstract classes provide shared code and required methods for subclasses.
- Abstraction improves reusability, flexibility, and maintainability.
