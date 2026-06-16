# Using Inner Classes in Java

## What are Inner Classes?

- An inner class is a class defined within another class.
- Inner classes can access members, variables, and methods of the outer class directly.
- They help organize code and keep related classes together.

## Why Use Inner Classes?

- Group classes that are only used in one place.
- Improve readability and maintainability.
- Encapsulate implementation details within the outer class.
- Access outer class members without passing them explicitly.

## Example: Simple Inner Class

```java
class OuterClass {
    int outerVariable = 10;

    class InnerClass {
        void display() {
            System.out.println("Outer variable value: " + outerVariable);
        }
    }
}

public class Main {
    public static void main(String[] args) {
        OuterClass outer = new OuterClass();
        OuterClass.InnerClass inner = outer.new InnerClass();
        inner.display();
    }
}
```

## Types of Inner Classes

### 1. Non-static Inner Class

- Also known as a member inner class.
- Can access both static and non-static members of the outer class.
- Requires an instance of the outer class to instantiate.

### 2. Static Nested Class

- Declared with the `static` keyword.
- Cannot access non-static members of the outer class directly.
- Can be instantiated without creating an outer class instance.

```java
class OuterClass {
    static int staticVariable = 20;

    static class StaticNestedClass {
        void show() {
            System.out.println("Static variable value: " + staticVariable);
        }
    }
}

public class Main {
    public static void main(String[] args) {
        OuterClass.StaticNestedClass nested = new OuterClass.StaticNestedClass();
        nested.show();
    }
}
```

### 3. Method-local Inner Class

- Defined inside a method.
- Accessible only within that method.
- Useful for small helper classes that are only needed within a single method.

```java
class OuterClass {
    void myMethod() {
        class MethodLocalInner {
            void display() {
                System.out.println("Inside Method Local Inner Class");
            }
        }

        MethodLocalInner localInner = new MethodLocalInner();
        localInner.display();
    }
}

public class Main {
    public static void main(String[] args) {
        OuterClass outer = new OuterClass();
        outer.myMethod();
    }
}
```

### 4. Anonymous Inner Class

- Does not have a name.
- Used when a class is needed only once.
- Commonly used to implement interfaces or extend classes on the fly.

```java
interface Greeting {
    void greet();
}

public class Main {
    public static void main(String[] args) {
        Greeting greeting = new Greeting() {
            @Override
            public void greet() {
                System.out.println("Hello from Anonymous Inner Class!");
            }
        };

        greeting.greet();
    }
}
```

## Practical Example: Library and Book

```java
class Library {
    String libraryName;

    Library(String libraryName) {
        this.libraryName = libraryName;
    }

    class Book {
        String title;
        String author;

        Book(String title, String author) {
            this.title = title;
            this.author = author;
        }

        void displayBookInfo() {
            System.out.println("Library: " + libraryName);
            System.out.println("Book Title: " + title);
            System.out.println("Author: " + author);
        }
    }
}

public class Main {
    public static void main(String[] args) {
        Library library = new Library("City Library");
        Library.Book book = library.new Book("1984", "George Orwell");
        book.displayBookInfo();
    }
}
```

## When to Use Inner Classes

- Encapsulate implementation details of the outer class.
- Group logically related classes together.
- Access outer class members directly when needed.
- Handle events in GUI applications using anonymous inner classes.
- Implement data structure nodes, such as trees and linked lists.

## Summary

- Inner classes are defined within outer classes and can access outer members.
- Java supports non-static inner classes, static nested classes, method-local inner classes, and anonymous inner classes.
- Inner classes help organize code, hide implementation details, and support tight coupling with the outer class.
- They are useful in GUI event handling, data structures, and other contexts where a helper class is local to its owner.
