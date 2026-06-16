# Introduction to Java Collections Framework

## What is a Collection?

### Definition
A **collection** is simply a group of objects. In formal terms, a collection is a container object that holds multiple references to other objects and provides methods to store, retrieve, manipulate, and communicate with aggregate data as a unified entity.

### Purpose in Java
In Java, collections:
- Store aggregate data
- Retrieve aggregate data
- Manipulate aggregate data
- Communicate aggregate data

## Java Collections Framework (JCF)

The **Java Collections Framework** is a powerful Java tool that allows developers to work with groups of objects.

**Key Features:**
- Provides a set of classes and interfaces to handle data collections
- Designed based on developers' specific needs
- Contains the root interface for all collection types
- Provides multiple collection types, each designed for specific use cases

---

## Types of Collections

### 1. List Collections

**Definition:** An ordered collection that allows duplicate elements and maintains order.

**Common Implementations:**
- ArrayList
- LinkedList

### 2. Set Collections

**Definition:** An unordered collection that does not allow duplicate elements.

**Common Implementations:**
- HashSet
- TreeSet

### 3. Map Collections

**Definition:** An unordered collection of key-value pairs where each key is unique.

**Common Implementations:**
- HashMap
- TreeMap

---

## ArrayList

### Overview
An ArrayList uses a **dynamic array** to store elements.

**Characteristics:**
- Allows fast, random access
- Slower when adding or removing elements from the middle

### Example Usage

```java
public class ListExample {
    public static void main(String[] args) {
        // Create an ArrayList to store strings
        List<String> fruits = new ArrayList<>();
        
        // Add fruits to the list
        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Cherry");
        
        // Print entire list
        System.out.println("Fruits: " + fruits);
        
        // Access and print the first fruit (index 0)
        String firstFruit = fruits.get(0);
        System.out.println("First fruit: " + firstFruit);
    }
}
```

**Explanation:**
1. `List<String> fruits = new ArrayList<>();` - Creates an ArrayList named fruits that can store strings
2. `fruits.add(...)` - Adds elements to the list
3. `fruits.get(0)` - Retrieves the element at index 0 (first element)
4. `System.out.println(...)` - Prints the list or specific element

---

## LinkedList

### Overview
A LinkedList uses a **doubly linked list** to store elements.

**Characteristics:**
- Efficiently adds and removes elements
- Operates slowly when accessing elements by index

### Example Usage

```java
public class LinkedListExample {
    public static void main(String[] args) {
        // Create a LinkedList to store strings
        LinkedList<String> animals = new LinkedList<>();
        
        // Add animals to the list
        animals.add("Dog");
        animals.add("Cat");
        animals.add("Elephant");
        
        // Print the entire list
        System.out.println("Animals: " + animals);
    }
}
```

**Explanation:**
1. `LinkedList<String> animals = new LinkedList<>();` - Creates a LinkedList named animals that can store strings
2. `animals.add(...)` - Adds elements to the list
3. `System.out.println(...)` - Prints the entire list

---

## Set Collections

### HashSet

**Characteristics:**
- Does not maintain any order
- Allows null values

### Example Usage

```java
public class HashSetExample {
    public static void main(String[] args) {
        // Create a HashSet to store unique strings
        HashSet<String> colors = new HashSet<>();
        
        // Add colors to the set
        colors.add("Red");
        colors.add("Green");
        colors.add("Blue");
        colors.add("Red");  // Duplicate - won't be added
        
        // Print the set of unique colors
        System.out.println("Colors: " + colors);
    }
}
```

**Explanation:**
- Attempting to add "Red" twice results in only one "Red" in the set (no duplicates)
- Prints all unique colors

### TreeSet

**Characteristics:**
- Maintains a sorted order of elements
- Does not allow null values

---

## Map Collections

### Overview
A Map collection **associates unique keys with values**. Each key is unique, but values can be duplicated.

### HashMap

**Characteristics:**
- Allows null values
- Data exists without a guaranteed order

### Example Usage

```java
public class HashMapExample {
    public static void main(String[] args) {
        // Create a HashMap with String keys and Integer values
        HashMap<String, Integer> ageMap = new HashMap<>();
        
        // Add name-age pairs to the map
        ageMap.put("Alice", 30);
        ageMap.put("Bob", 25);
        ageMap.put("Charlie", 35);
        
        // Print the entire map
        System.out.println("Age Map: " + ageMap);
        
        // Retrieve and print a specific value by key
        int aliceAge = ageMap.get("Alice");
        System.out.println("Alice's Age: " + aliceAge);
    }
}
```

**Explanation:**
1. `HashMap<String, Integer> ageMap = new HashMap<>();` - Creates a HashMap with String keys and Integer values
2. `ageMap.put(key, value)` - Adds key-value pairs to the map
3. `ageMap.get(key)` - Retrieves the value associated with a specific key

### TreeMap

**Characteristics:**
- Allows null values
- Maintains keys in sorted order

---

## Summary

### Key Takeaways

**Collections Framework Purpose:**
- Java collections store, retrieve, manipulate, and communicate aggregate data
- Powerful tool for developers to work with groups of objects

**Collection Types:**

| Type | Ordered? | Allows Duplicates? | Use Case |
|------|----------|-------------------|----------|
| List | Yes | Yes | Ordered data with duplicates |
| Set | No | No | Unique elements only |
| Map | No | Values can duplicate | Key-value associations |

**List Implementations:**
- **ArrayList**: Fast random access, slow for middle insertions/deletions
- **LinkedList**: Efficient insertions/deletions, slow random access

**Set Implementations:**
- **HashSet**: No order guaranteed, allows null values
- **TreeSet**: Maintains sorted order, no null values

**Map Implementations:**
- **HashMap**: No guaranteed order, allows null values
- **TreeMap**: Maintains key order (sorted), allows null values
