# Conditional Statements

This document expands on conditional statements in Java: how they make decisions, when to use them, and practical examples for `if`, `if-else`, `else if`, `switch`, and nested conditionals.

## 1. What are conditional statements?

Conditional statements let a program decide which code to run based on boolean expressions (true/false). Think of them as questions the program asks at runtime; the answer determines the next action.

## 2. `if` statement

Use `if` to execute code only when a condition is true.

Example:

```java
int number = 10;
if (number > 5) {
    System.out.println("The number is greater than 5");
}
```

## 3. `if-else` and `else if`

`if-else` provides an alternative block when the `if` condition is false. `else if` lets you test additional conditions in sequence.

Example:

```java
int number = 3;
if (number > 5) {
    System.out.println("The number is greater than 5");
} else {
    System.out.println("The number is not greater than 5");
}
```

Chained example with `else if`:

```java
int number = 5;
if (number > 5) {
    System.out.println("The number is greater than 5");
} else if (number == 5) {
    System.out.println("The number equals 5");
} else {
    System.out.println("The number is less than 5");
}
```

## 4. `switch` statement

Use `switch` to compare a single variable against multiple discrete values. It often reads clearer than many `if-else` branches for the same variable. Always include a `default` case as a fallback.

Example:

```java
int day = 3;
switch (day) {
    case 1:
        System.out.println("Monday");
        break;
    case 2:
        System.out.println("Tuesday");
        break;
    case 3:
        System.out.println("Wednesday");
        break;
    default:
        System.out.println("Weekend or unknown day");
}
```

## 5. Nested conditionals

You can nest conditional statements to express more complex decision trees. Keep nesting shallow to preserve readability.

Example:

```java
int age = 20;
if (age >= 18) {
    System.out.println("You are an adult.");
    if (age >= 65) {
        System.out.println("You are a senior citizen.");
    }
} else {
    System.out.println("You are a minor.");
}
```

## 6. When to use `switch` vs `if`

- Use `switch` when checking one variable against many constant values (enums, integers, strings).
- Use `if`/`else if` when conditions are ranges, complex expressions, or involve different variables.

## 7. Best practices

- Keep conditions simple and readable.
- Prefer early returns to reduce nesting and improve clarity.
- Extract complex condition logic into well-named methods.
- Use `switch` with `enum` types for clarity and maintainability.
- Always include a `default` in `switch` as a safe fallback.

## 8. Summary

Conditional statements control program flow by evaluating boolean expressions. Use `if`, `else if`, `else`, and `switch` appropriately, prefer readable and maintainable structures, and avoid deep nesting when possible.
