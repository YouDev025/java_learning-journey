# Understanding Inheritance in Java

## Key Concepts

- Inheritance is when one class (child/subclass) derives properties and methods from another class (parent/superclass).
- It promotes code reuse by allowing classes to inherit existing behavior rather than rewriting it.
- A subclass can modify or extend superclass behavior using method overriding.
- Inheritance helps organize code into hierarchies, making it easier to understand and extend.

## Common Terms

- `superclass`: a class whose properties and methods are inherited by another class.
- `subclass`: a class that inherits from a superclass.
- `extends`: the keyword used in Java to declare that one class inherits from another.

## Java Inheritance Rules

- A subclass inherits all `public` and `protected` members from its superclass.
- A subclass does not inherit `private` members of the superclass.
- Inherited members can be reused directly in the subclass.

## Example: Animal and Dog

```java
class Animal {
    String name;

    void eat() {
        System.out.println(name + " is eating.");
    }

    void sound() {
        System.out.println("Animal makes a sound.");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Dog is barking.");
    }

    @Override
    void sound() {
        System.out.println("Dog barks.");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog myDog = new Dog();
        myDog.name = "Buddy";
        myDog.eat();
        myDog.bark();
        myDog.sound();
    }
}
```

## Types of Inheritance

- **Single Inheritance**: one subclass inherits from one superclass.
- **Multilevel Inheritance**: a subclass inherits from another subclass.
  - Example: `Animal` -> `Dog` -> `Puppy`
- **Hierarchical Inheritance**: multiple subclasses inherit from the same superclass.
  - Example: `Animal` -> `Dog`, `Cat`
- **Multiple Inheritance**: not directly supported in Java for classes due to ambiguity.
  - Java uses interfaces to achieve similar behavior.

## Method Overriding

- Overriding occurs when a subclass provides its own implementation of a method defined in the superclass.
- It allows child classes to customize inherited behavior.
- The runtime type determines which overridden method is called.

## Example: Runtime Polymorphism

```java
Animal myAnimal = new Dog();
myAnimal.sound(); // calls Dog's version of sound()
```

## Applications of Inheritance

- Code reuse: share common logic between related classes.
- Hierarchical classification: model relationships between general and specific entities.
- Flexible behavior: subclasses override methods for specialized actions.
- Game development: share common character properties and allow unique abilities.
- UI components: common component behavior with specific button, text box, or label actions.
- Data models: consistent shared fields across different entities with unique attributes.

## Summary

- Inheritance enables subclasses to inherit properties and methods from superclasses.
- Types of inheritance: single, multilevel, hierarchical, and multiple (via interfaces).
- Method overriding supports custom behavior in subclasses.
- Inheritance is especially useful for code reuse, organization, and extending functionality in real-world applications.
