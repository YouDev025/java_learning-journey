# Data Types in Java

## 1. What are data types?

Data types are containers designed to hold specific kinds of information. Each data type specifies what kind of data a variable can store and defines properties like size and range. Data types determine what operations Java programs can perform on stored data.

## 2. Categories of Java data types

Java data types are broadly grouped into:

- Primitive data types
- Reference data types

### 2.1 Primitive data types

Primitive data types store actual values directly. They have a fixed size, a default immutable value, and cannot be null.

Common primitive types:

- `byte` — 8-bit integer, range `-128` to `127`. Useful to save memory in large arrays.
  - Example: `byte age = 25;`
- `short` — 16-bit integer, range `-32,768` to `32,767`. Good for small integer values like temperature.
  - Example: `short temperature = -5;`
- `int` — 32-bit integer, the most commonly used integer type for whole numbers.
  - Example: `int population = 1_000_000;`
- `long` — 64-bit integer for very large whole numbers, such as distances or large counters.
  - Example: `long distanceToMoon = 384_400_000L;`
- `float` — 32-bit floating-point number for decimal values when high precision is not required.
  - Example: `float price = 19.99F;`
- `double` — 64-bit floating-point number for more precise decimal values.
  - Example: `double pi = 3.141592653589793;`
- `char` — single 16-bit Unicode character.
  - Example: `char initial = 'a';`
- `boolean` — true/false value, often used for conditions and state checks.
  - Example: `boolean loggedIn = true;`

### 2.2 Reference data types

Reference data types store references to objects or collections instead of storing the actual data directly. They are used for more complex structures like text, lists, and custom objects.

Common reference types:

- `String` — sequence of characters used for text data.
  - Example: `String greeting = "Hello, World!";`
- Arrays — ordered collections of values of the same type.
  - Example: `int[] scores = {90, 85, 78, 92};`
  - Values are accessed by index, starting at zero.
- Classes — blueprints for creating objects that combine data and behavior.
  - Example: a `Book` class with attributes like `title` and `author`.
- Objects — instances of classes containing data and methods.
- Interfaces — contracts that define method signatures without implementations.
  - They let multiple classes implement the same behaviors and make code easier to update.
- Enums — named constants that define a fixed set of values.
  - Useful for representing options like days of the week or colors.

## 3. Why primitive and reference types matter

- Primitive types are efficient and store simple values directly.
- Reference types let you work with complex data structures, custom types, and standard library classes.
- Choosing the right type helps keep code clear, efficient, and easier to maintain.

## 4. Best practices for selecting data types

- Use `int` for whole numbers in most cases.
- Use `double` for decimal values when precision matters.
- Use `String` for text and character sequences.
- Use `boolean` for yes/no or true/false conditions.
- Be careful with decimal calculations, as `float` and `double` behave differently and may lead to rounding differences.

## 5. Summary

- Data types are containers that store specific kinds of information.
- Each data type defines a variable's allowed values, size, and range.
- Primitive types include `byte`, `short`, `int`, `long`, `float`, `double`, `char`, and `boolean`.
- Reference types use memory addresses to locate actual data and support complex structures.
- Reference types include `String`, arrays, classes, interfaces, and enums.
- Understanding data types helps developers write correct and maintainable Java programs.
