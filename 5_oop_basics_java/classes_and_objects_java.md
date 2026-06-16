# Using Classes and Objects in Java

This note explains classes, objects, access modifiers, and non-access modifiers in Java.

## Classes and Objects

- A **class** is a blueprint or template for creating objects.
- A **car** class can define attributes such as `wheels`, `steeringSystem`, `engine`, `seats`, `color`, `model`, and `year`.
- A **subclass** inherits from a superclass using the `extends` keyword.
- Objects created from a class share the same structure but can have unique values.

Example:

- `Car` is a class blueprint.
- `Car myCar` declares a reference variable.
- `new Car()` creates a new object instance.
- Initializing attributes assigns values like `color`, `model`, and `year`.
- `myCar.displayInfo()` calls a method to print the car’s details.

```java
class Car {
    String color;
    String model;
    int year;

    void displayInfo() {
        System.out.println(model + " (" + year + ") - " + color);
    }
}

Car myCar = new Car();
myCar.color = "blue";
myCar.model = "hatchback";
myCar.year = 2023;
myCar.displayInfo();
```

## Inheritance

- A subclass inherits properties and methods from a superclass.
- The subclass can add new behavior or override existing behavior.
- Example: `Dog` can inherit from `Animal` and add `bark()` method.

```java
class Animal {
    void eat() {
        System.out.println("Animal eats");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Woof!");
    }
}
```

## Access Modifiers

Access modifiers determine the visibility of classes, methods, and variables.

- `public`
  - Accessible from any class in any package.
  - Example: `public String model;` lets other classes access and modify the model.
- `private`
  - Accessible only within the same class.
  - Example: `private String color;` hides the color from other classes.
- `protected`
  - Accessible within the same package and by subclasses in other packages.
  - Example: `protected int year;` allows package access and subclass access.
- Default (no modifier)
  - Accessible only within the same package.
  - Example: `String model;` is package-private.

## Non-Access Modifiers

Non-access modifiers add behavioral details without changing visibility.

- `static`
  - Belongs to the class rather than individual instances.
  - Shared by all objects of the class.
  - Example: a static counter for the total number of `Car` objects created.
- `final`
  - A variable cannot be changed once assigned.
  - A method cannot be overridden.
  - A class cannot be subclassed.
  - Example: declaring a class `final` prevents it from being extended.
- `abstract`
  - An abstract class cannot be instantiated and must be extended.
  - An abstract method has no implementation and must be implemented by subclasses.
  - Example: `Shape` is an abstract class with an abstract method `draw()`.
  - `Circle` can extend `Shape` and implement `draw()`.

```java
abstract class Shape {
    abstract void draw();
}

class Circle extends Shape {
    void draw() {
        System.out.println("Drawing Circle");
    }
}

final class Vehicle {
    // This class cannot be subclassed
}

class Counter {
    static int totalCars;
}
```

## Summary

- A class defines properties and behaviors for objects.
- Objects are instances of classes with specific attribute values.
- Access modifiers control visibility: `public`, `private`, `protected`, and default.
- Non-access modifiers influence behavior: `static`, `final`, and `abstract`.
