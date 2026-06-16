# Object-Oriented Programming (OOP)

Object-oriented programming is a way of organizing software around objects and classes.
The main ideas are:

- **Object:** A specific thing with its own data and behavior.
- **Class:** A blueprint or template used to create objects.
- **Properties:** The attributes or characteristics of an object.
- **Methods:** The actions an object can perform.
- **Inheritance:** A way for a class to derive from another class and reuse its properties and methods.
- **Encapsulation:** Hiding internal details while exposing only what is necessary.
- **Polymorphism:** Allowing different objects to be used through the same interface.

## Classes and Objects

Imagine a red sports car:

- The car’s color, speed, and model are its properties.
- Driving and honking are actions it can perform.
- In programming, the red sports car is an **object**.
- A **class** is the blueprint that defines what all cars should have.

A class describes shared properties and methods, while objects are concrete instances with specific values.

```java
class Car {
    String color;
    int speed;
    String model;

    void drive() {
        System.out.println("Driving the " + color + " " + model);
    }

    void honk() {
        System.out.println("Honk!");
    }
}

Car myCar = new Car();
myCar.color = "red";
myCar.speed = 220;
myCar.model = "sports car";
myCar.drive();
myCar.honk();
```

## Properties

Properties are the attributes of an object.
For a car, examples include:

- `color` (red, blue, black)
- `speed` (fast, medium, slow)
- `model` (sedan, SUV, sports car)

Each object stores its own values for those properties.

## Methods

Methods are actions performed by an object.
For a car, methods may include:

- `drive()`
- `honk()`
- `park()`

Methods define how the object behaves.

## Inheritance

Inheritance creates new classes from existing ones.
It is like a family tree:

- A base `Car` class can have subclasses such as `ElectricCar` and `SportsCar`.
- Subclasses inherit properties and methods from the parent class.
- They can also add their own unique features.

Examples:

- `ElectricCar` may add a `batteryLife` property.
- `SportsCar` may add a `boost()` method.

## Encapsulation

Encapsulation bundles an object’s data and the methods that operate on it into a single unit.
It hides internal details and exposes only what is necessary.

Example:

- A television can be controlled with a remote, but you do not need to know how the screen works internally.
- The TV’s inner workings remain hidden while the outside interface stays simple.

## Polymorphism

Polymorphism allows different objects to be treated as instances of a common parent type.
A single method name can work with different object types.

Example:

- A `helicopter` and a `rocket` both have a `fly()` method.
- The helicopter’s `fly()` uses rotor blades.
- The rocket’s `fly()` uses engines.

Even though the method name is the same, each object performs a different action.

```java
interface Flyer {
    void fly();
}

class Helicopter implements Flyer {
    public void fly() {
        System.out.println("Lift off with rotor blades");
    }
}

class Rocket implements Flyer {
    public void fly() {
        System.out.println("Launch with engines");
    }
}

void launch(Flyer flyer) {
    flyer.fly();
}
```

## Example: Online Bookstore

Use an online bookstore to understand OOP concepts.

- `Book` class: blueprint with properties such as `title`, `author`, and `price`.
- A specific book like *The Great Gatsby* is an object instance of `Book`.
- `Customer` class: properties include `name`, `email`, and `address`.

Methods define behavior:

- `Book.displayInfo()` shows book details.
- `Book.applyDiscount()` lowers the price.
- `Customer.createAccount()` lets a new customer sign up.
- `Customer.processOrder()` handles book purchases.

Inheritance and specialization:

- `Ebook` can inherit from `Book` and add `fileFormat`.

Encapsulation protects sensitive data:

- Private properties such as passwords are hidden and accessed through controlled methods.

Polymorphism supports shared interfaces:

- Different payment methods like `CreditPayment` and `PayPal` can implement the same interface.
- Customers can choose a payment method while the code treats them uniformly.

```java
interface PaymentMethod {
    void pay(double amount);
}

class CreditPayment implements PaymentMethod {
    public void pay(double amount) {
        System.out.println("Paying " + amount + " with credit card");
    }
}

class PayPal implements PaymentMethod {
    public void pay(double amount) {
        System.out.println("Paying " + amount + " with PayPal");
    }
}
```

## Summary

- Objects are specific instances with unique properties and behaviors.
- Classes are blueprints that define shared properties and methods.
- Properties store attributes.
- Methods define actions.
- Inheritance lets new classes derive from existing ones.
- Encapsulation hides internal details.
- Polymorphism lets different objects share the same interface while behaving differently.
