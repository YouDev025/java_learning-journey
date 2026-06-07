# Operators in Java

This document covers Java operators, including assignment, unary, ternary, and advanced operator types.

## 1. What are operators?

Operators are special symbols that perform operations on variables and values. They tell the Java compiler to perform specific mathematical or logical manipulations. Operators can work with variables, constants, and expressions to produce a result.

## 2. Assignment operators

Assignment operators assign values to variables and can update those values using a math operation.

- `=` assigns a value to a variable.
- `+=` adds a value to the variable and updates it.
- `-=` subtracts a value from the variable and updates it.
- `*=` multiplies the variable by a value and updates it.
- `/=` divides the variable by a value and updates it.
- `%=` calculates the remainder and updates the variable.

Example:

```java
int a = 10;      // assign 10 to a

a += 5;          // a = a + 5, now a is 15
System.out.println("new value of a: " + a);

a *= 2;          // a = a * 2, now a is 30
System.out.println("after multiplication, new value of a: " + a);
```

Compound assignment operators combine an operation and assignment in a shorter form.

## 3. Unary operators

Unary operators work on a single operand. They are often used for increments, decrements, or negation.

- `+a` unary plus: keeps the value unchanged.
- `-a` unary minus: negates the value.
- `++a` or `a++` increment: adds 1 to the variable.
- `--a` or `a--` decrement: subtracts 1 from the variable.

Example:

```java
int a = 10;
System.out.println("unary plus: " + (+a));   // 10
System.out.println("unary minus: " + (-a));  // -10

a++;
System.out.println("after increment: " + a); // 11

a--;
System.out.println("after decrement: " + a); // 10
```

Unary operators can flip a number's sign or increase and decrease its value.

## 4. Ternary operator

The ternary operator is a shorthand form of `if-else`. It uses three operands:

```java
condition ? expression1 : expression2
```

If the condition is true, it evaluates `expression1`; otherwise, it evaluates `expression2`.

Example:

```java
int a = 10;
int b = 20;
int max = (a > b) ? a : b;
System.out.println("maximum value is " + max); // 20
```

## 5. Advanced operators overview

Advanced operators include bitwise and shift operators. They work at the binary level and are useful for low-level tasks, performance optimization, graphics programming, cryptography, and hardware-related code.

- Bitwise operators work with binary data.
- Shift operators move bits left or right.

These operators go beyond basic arithmetic, comparison, and logical operators.

## 6. Summary

- Advanced operators in Java include assignment, unary, ternary, bitwise, and shift operators.
- Assignment operators combine a value update with an assignment.
- Unary operators act on a single operand and can increment, decrement, or negate values.
- The ternary operator provides a concise conditional expression.
- Bitwise and shift operators are used for binary-level operations and specialized low-level programming tasks.
