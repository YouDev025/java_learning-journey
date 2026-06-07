# Strings in Java

This document expands on working with `String` in Java: creation, common operations, immutability, and practical examples.

## 1. What is a `String`?

A `String` is a sequence of characters (including spaces and punctuation). Think of a string like a bead necklace where each bead is a character and the whole necklace is the string.

Strings can be created as literals or by using the `new` keyword:

```java
String a = "Hello, World!";           // string literal
String b = new String("Hello, World!"); // explicit object (rarely needed)
```

## 2. Length and character access

Use `length()` to find the number of characters (including spaces) and `charAt(index)` to access a character by zero-based index:

```java
String s = "Java Programming";
int len = s.length();      // 16 (counts all chars)
char first = s.charAt(0);  // 'J'
```

## 3. Concatenation and joining

Combine strings with `+` or `concat()`:

```java
String s1 = "Hello";
String s2 = "World";
String combined = s1 + ", " + s2;           // "Hello, World"
String combined2 = s1.concat(", ").concat(s2);

// joining an array
String[] colors = {"Red","Green","Blue"};
String csv = String.join(", ", colors); // "Red, Green, Blue"
```

## 4. Comparing strings

Use `equals()` or `equalsIgnoreCase()` to compare content. Do not use `==` for value equality (it compares references):

```java
"Hello".equals("Hello");          // true
"Hello" == new String("Hello");   // usually false
```

## 5. Substring, split, and index operations

Extract parts and split strings:

```java
String t = "apple,banana,cherry";
String[] parts = t.split(","); // ["apple","banana","cherry"]
String sub = "Java Programming".substring(5, 16); // "Programming" (end exclusive)
int idx = t.indexOf("banana");
```

## 6. Immutability and consequences

`String` is immutable — operations that look like modifications actually create new `String` objects. This is safe but can be inefficient for many concatenations; use `StringBuilder` when building strings repeatedly.

```java
String s = "Hello";
s = s + " World"; // creates a new String

StringBuilder sb = new StringBuilder();
sb.append("Hello");
sb.append(" World");
String result = sb.toString();
```

## 7. Case, trimming, and replacing

Useful built-in methods:

```java
"Hello".toUpperCase();        // "HELLO"
"Hello".toLowerCase();        // "hello"
"  a  ".trim();               // "a"
"2020-2021".replace("-", "/"); // "2020/2021"
```

## 8. Formatting

Format using `String.format()` or `printf`:

```java
String out = String.format("Name: %s, Age: %d", "Alice", 30);
System.out.printf("%s is %d years old\n", "Alice", 30);
```

## 9. Best practices

- Use string literals for simple constants.
- Prefer `equals()` for content comparison and `equalsIgnoreCase()` when case-insensitive.
- Use `StringBuilder` for heavy concatenation (loops, large builders).
- Trim and validate input before processing user-provided strings.
- Be aware of Unicode and character encoding when manipulating text.

## 10. Summary

Strings are sequences of characters and are immutable in Java. Common operations include `length()`, `charAt()`, `substring()`, `split()`, `replace()`, and case/trim functions. Use `StringBuilder` for efficient, repeated concatenation.
