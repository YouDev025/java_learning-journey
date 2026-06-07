# Loops in Java

This document expands on loops in Java with practical details and examples: when to use each loop type, how to structure loops, and common loop control features.

## 1. What are loops and why use them?

Loops execute a block of code repeatedly based on a condition. They are fundamental for repeating tasks such as printing sequences, processing collections, or traversing arrays without writing repetitive code.

## 2. `for` loop

Use a `for` loop when the number of iterations is known or when iterating with an index.

```java
// print numbers from 1 to 5
for (int i = 1; i <= 5; i++) {
    System.out.println(i);
}
```

- Initialization: `int i = 1`
- Condition: `i <= 5`
- Update: `i++`

## 3. `while` loop

Use `while` when the number of iterations is not known in advance; the loop runs while the condition is true.

```java
int i = 1;
while (i <= 5) {
    System.out.println(i);
    i++;
}
```

## 4. `do-while` loop

`do-while` executes the body at least once and then checks the condition.

```java
int i = 1;
do {
    System.out.println(i);
    i++;
} while (i <= 5);
```

Even if `i` started greater than `5`, the `do` block runs once before the condition is checked.

## 5. Enhanced `for` (for-each)

Use the enhanced `for` when iterating collections or arrays when you don't need an index.

```java
int[] numbers = {1,2,3,4,5};
for (int value : numbers) {
    System.out.println(value);
}
```

## 6. Nested loops

Nested loops are useful for multidimensional data (e.g., matrices). Be mindful of time complexity.

```java
// multiplication table 1..10
for (int i = 1; i <= 10; i++) {
    for (int j = 1; j <= 10; j++) {
        System.out.print((i * j) + "\t");
    }
    System.out.println();
}
```

## 7. `break` and `continue`

- `break` exits the nearest loop immediately.
- `continue` skips the rest of the current iteration and proceeds to the next.

Examples:

```java
// break example: find first number > 5
int[] nums = {2, 4, 7, 1};
for (int n : nums) {
    if (n > 5) {
        System.out.println("Found: " + n);
        break; // exit loop
    }
}

// continue example: print 1..10 but skip 5
for (int i = 1; i <= 10; i++) {
    if (i == 5) continue;
    System.out.println(i);
}
```

## 8. Best practices

- Keep loop bodies focused and small.
- Prefer enhanced `for` for simple iteration over collections/arrays.
- Use `while` or `do-while` when the end condition depends on external or dynamic state.
- Avoid modifying the collection you're iterating unless using an iterator.
- Use `break`/`continue` sparingly to keep logic easy to follow.
- Be mindful of performance when nesting loops (watch for O(n^2) or worse).

## 9. Summary

Java supports several loop constructs (`for`, enhanced `for`, `while`, `do-while`) to handle repetition. Choose the construct that best fits your iteration pattern, keep code readable, and test edge cases (empty collections, off-by-one errors).
