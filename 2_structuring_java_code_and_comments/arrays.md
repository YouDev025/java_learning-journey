# Arrays in Java

This document covers arrays in Java, including how to declare, create, modify, and iterate through arrays.

## 1. What is an array?

An array is a collection of elements, all of the same type, stored in contiguous memory locations. Arrays let you store multiple values in a single variable, making it easier to manage collections of data. Each element is accessed using an index, which represents the element's position in the array.

Java arrays can hold primitive data types like `int`, `char`, or `boolean`, or reference types such as objects.

## 2. Declaring and creating arrays

To declare an array, use the type followed by `[]` and the array name:

```java
int[] numbers;
```

After declaring an array, initialize it to allocate memory using `new`:

```java
numbers = new int[5];
```

You can also declare and initialize an array in one line:

```java
int[] numbers = new int[5];
```

Or create and assign values directly:

```java
int[] numbers = {1, 2, 3, 4, 5};
```

## 3. Accessing array elements

Access individual elements using their index inside square brackets. Array indices start at `0`.

Example:

```java
int[] numbers = {1, 2, 3, 4, 5};
System.out.println(numbers[0]); // 1
System.out.println(numbers[4]); // 5
```

## 4. Modifying array values

Change an element by assigning a new value at its index:

```java
int[] numbers = {1, 2, 3, 4, 5};
numbers[2] = 10; // third element now becomes 10
```

Use `numbers.length` to determine how many elements are in the array.

## 5. Iterating through arrays

A common operation is iterating through the array to read or modify elements.

### 5.1 Standard `for` loop

```java
for (int i = 0; i < numbers.length; i++) {
    System.out.println(numbers[i]);
}
```

The loop stops when `i` reaches `numbers.length`, and `i++` moves to the next element.

### 5.2 Enhanced `for` loop

```java
for (int value : numbers) {
    System.out.println(value);
}
```

This `for-each` syntax provides a simpler way to access each element.

## 6. Multidimensional arrays

Java supports multidimensional arrays, such as two-dimensional arrays, which are arrays of arrays.

Example:

```java
int[][] matrix = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};
```

This creates a 3x3 grid of numbers. Each inner set of braces represents one row.

## 7. Accessing elements in a 2D array

Use two indices to access a value in a two-dimensional array:

```java
int value = matrix[0][1]; // accesses the value in row 0, column 1
```

## 8. Iterating through a 2D array

Use nested loops to walk through each row and column:

```java
for (int i = 0; i < matrix.length; i++) {
    for (int j = 0; j < matrix[i].length; j++) {
        System.out.print(matrix[i][j] + " ");
    }
    System.out.println();
}
```

The outer loop handles rows and the inner loop handles columns.

## 9. Summary

- Arrays store multiple values of the same type in a single variable.
- Declare arrays with `type[] name` and initialize them with `new type[size]`.
- Access and modify array elements using zero-based indices.
- Use `length` to get the array size.
- Iterate arrays with `for` loops or enhanced `for-each` loops.
- Multi-dimensional arrays require nested loops to traverse.
