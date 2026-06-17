# Working with Maps: HashMap and TreeMap

 
---

## What is a Map?

### Definition
A **map is a data structure that stores key-value pairs, where each key is unique and maps to a specific value.** In formal terms, a map is an associative array that associates unique keys with their corresponding values, allowing efficient retrieval of values based on their keys.

### Key Concepts

**Key Characteristics:**
- Each key must be unique
- Multiple keys cannot reference the same object
- Multiple values can reference the same object
- Values can be duplicated, but keys cannot

**Real-World Analogy:**
A map is like a digital address book with multiple nicknames pointing to the same phone number. Just as you can look up a contact by various names but get the same phone number, a map allows multiple keys to reference the same value.

### Basic Structure

```
Key → Value
"Alice" → 30
"Bob" → 25
"Charlie" → 30  (Same value as Alice)
```

---

## HashMap

### Overview

A **HashMap** is part of the Java Collections Framework that implements the map interface and stores entries in a **hash table**. It utilizes hashing to create an index, ensuring fast lookups.

### Characteristics

| Feature | Detail |
|---------|--------|
| **Storage Mechanism** | Hash table |
| **Time Complexity** | O(1) average case for access |
| **Key Ordering** | No guaranteed order |
| **Null Keys** | Allows one null key |
| **Null Values** | Allows multiple null values |
| **Duplicates** | Keys must be unique |
| **Thread-Safety** | Not synchronized (not thread-safe) |

### How HashMap Works

**Hashing Process:**
1. Key is passed to a hash function
2. Hash function generates a hash code
3. Hash code is converted to an index in the hash table
4. Value is stored at that index

**Retrieval:**
- Same hash function used to locate the value
- Direct access to the index = O(1) time complexity

### Basic Operations

```java
import java.util.HashMap;

// Create a HashMap with String keys and Integer values
HashMap<String, Integer> ageMap = new HashMap<>();

// Add entries using put method
ageMap.put("Alice", 30);
ageMap.put("Bob", 25);
ageMap.put("Charlie", 35);

// Retrieve value using get method
int aliceAge = ageMap.get("Alice");  // Returns 30

// Check if key exists using containsKey
if (ageMap.containsKey("Bob")) {
    System.out.println("Bob is in the map");
}

// Iterate through keys using keySet
for (String name : ageMap.keySet()) {
    System.out.println(name + " : " + ageMap.get(name));
}

// Remove entry using remove method
ageMap.remove("Charlie");

// Check size
System.out.println("Size: " + ageMap.size());
```

### Use Cases for HashMap

HashMaps are ideal for:
- **Quick Lookups** - Fast data retrieval by key
- **Counting Items** - Word frequency analysis or statistics
- **Dictionaries** - Implementing associative arrays
- **Caching** - Storing computed values for quick access
- **Index Building** - Creating indexes for fast searches
- **Large Datasets** - Handling data with performance requirements

### When to Use HashMap

✅ Use HashMap when:
- You need fast O(1) average access time
- The order of entries doesn't matter
- You need to handle large datasets efficiently
- You want to support null values and one null key
- You're implementing a cache or lookup table
- Performance is more important than ordering

### Example: Word Frequency Counter

```java
import java.util.HashMap;

public class WordFrequencyCounter {
    public static void main(String[] args) {
        // Create HashMap to count word frequencies
        HashMap<String, Integer> wordCount = new HashMap<>();
        
        String[] words = {"apple", "banana", "apple", "cherry", "banana", "apple"};
        
        // Count word frequencies
        for (String word : words) {
            if (wordCount.containsKey(word)) {
                // Key exists, increment count
                wordCount.put(word, wordCount.get(word) + 1);
            } else {
                // Key doesn't exist, add with count 1
                wordCount.put(word, 1);
            }
        }
        
        // Display word frequencies
        System.out.println("Word Frequencies:");
        for (String word : wordCount.keySet()) {
            System.out.println(word + ": " + wordCount.get(word));
        }
        // Output:
        // apple: 3
        // banana: 2
        // cherry: 1
    }
}
```

---

## TreeMap

### Overview

A **TreeMap** is another implementation of the Map interface that uses a **red-black tree structure** to ensure entries are stored in sorted order based on their keys.

### Characteristics

| Feature | Detail |
|---------|--------|
| **Storage Mechanism** | Red-black tree (balanced binary search tree) |
| **Time Complexity** | O(log n) for access operations |
| **Key Ordering** | Maintains sorted order |
| **Null Keys** | Does not allow null keys |
| **Null Values** | Allows multiple null values |
| **Duplicates** | Keys must be unique |
| **Thread-Safety** | Not synchronized (not thread-safe) |
| **Navigation** | Provides methods for sorted traversal |

### How TreeMap Works

**Tree Structure:**
1. Keys stored in a self-balancing red-black tree
2. Tree organized to maintain sorted order
3. Supports efficient range queries
4. Provides sorted iteration

**Access Time:**
- Logarithmic time O(log n) for insertions, deletions, and searches
- As dataset grows, access time grows logarithmically

### Basic Operations

```java
import java.util.TreeMap;

// Create a TreeMap with String keys and Integer values
TreeMap<String, Integer> scoreMap = new TreeMap<>();

// Add entries using put method
scoreMap.put("Alice", 95);
scoreMap.put("Bob", 87);
scoreMap.put("Charlie", 92);

// Retrieve value using get method
int aliceScore = scoreMap.get("Alice");  // Returns 95

// Check if key exists using containsKey
if (scoreMap.containsKey("Bob")) {
    System.out.println("Bob is in the map");
}

// Iterate through keys (automatically in sorted order)
for (String name : scoreMap.keySet()) {
    System.out.println(name + " : " + scoreMap.get(name));
}

// Get first (lowest) key
String firstKey = scoreMap.firstKey();

// Get last (highest) key
String lastKey = scoreMap.lastKey();

// Get range of keys
for (String name : scoreMap.subMap("Alice", "Charlie")) {
    System.out.println(name + " : " + scoreMap.get(name));
}

// Remove entry using remove method
scoreMap.remove("Charlie");
```

### Use Cases for TreeMap

TreeMaps are ideal for:
- **Sorted Lists** - Displaying information in order
- **Priority Queues** - Managing items by priority
- **Range Queries** - Finding all entries within a key range
- **Leaderboards** - Displaying scores in sorted order
- **Sorted Indexes** - Maintaining sorted collections
- **Min/Max Operations** - Finding smallest or largest key
- **Ordered Iteration** - Processing entries in key order

### When to Use TreeMap

✅ Use TreeMap when:
- You need entries sorted by key
- You perform range queries frequently
- You need to access smallest or largest key
- You iterate through entries in order
- You can accept O(log n) time complexity
- Ordering is important for your application
- You need navigable map operations

### Example: Leaderboard Implementation

```java
import java.util.TreeMap;
import java.util.Comparator;

public class Leaderboard {
    public static void main(String[] args) {
        // Create TreeMap with descending order (highest scores first)
        TreeMap<Integer, String> leaderboard = 
            new TreeMap<>(Comparator.reverseOrder());
        
        // Add player scores
        leaderboard.put(95, "Alice");
        leaderboard.put(87, "Bob");
        leaderboard.put(92, "Charlie");
        leaderboard.put(88, "David");
        leaderboard.put(98, "Eve");
        
        // Display leaderboard (automatically sorted by score)
        System.out.println("Leaderboard (Highest to Lowest):");
        int rank = 1;
        for (Integer score : leaderboard.keySet()) {
            System.out.println(rank + ". " + leaderboard.get(score) + 
                             " - Score: " + score);
            rank++;
        }
        // Output:
        // 1. Eve - Score: 98
        // 2. Alice - Score: 95
        // 3. Charlie - Score: 92
        // 4. David - Score: 88
        // 5. Bob - Score: 87
    }
}
```

---

## HashMap vs TreeMap: Detailed Comparison

### Storage and Structure

**HashMap:**
- Uses hash table for storage
- Entries scattered based on hash codes
- No inherent ordering

**TreeMap:**
- Uses red-black tree (balanced BST) structure
- Entries organized by key order
- Maintains sorted order automatically

### Performance Characteristics

| Operation | HashMap | TreeMap |
|-----------|---------|---------|
| **Get** | O(1) average | O(log n) |
| **Put** | O(1) average | O(log n) |
| **Remove** | O(1) average | O(log n) |
| **ContainsKey** | O(1) average | O(log n) |
| **Iteration** | O(n) | O(n) |
| **Space** | O(n) | O(n) |

### Null Handling

**HashMap:**
- Allows one null key
- Allows multiple null values
- Flexible with null data

**TreeMap:**
- Does not allow null keys (throws NullPointerException)
- Allows multiple null values
- More restrictive

### Ordering and Iteration

**HashMap:**
- No guaranteed order
- Iteration order unpredictable
- Depends on hash table state

**TreeMap:**
- Keys automatically sorted
- Iteration in key order
- Predictable and consistent

### Memory Usage

**HashMap:**
- Lower memory overhead per entry
- Only stores key and value

**TreeMap:**
- Higher memory overhead per entry
- Stores tree node references (left, right, parent, color)

### Comparability Requirements

**HashMap:**
- Keys need not be comparable
- Uses hash code only

**TreeMap:**
- Keys must be comparable (implement Comparable)
- Or provide custom Comparator
- Keys must be comparable to each other

---

## Decision Matrix: Choosing Between HashMap and TreeMap

### Choose HashMap When:

| Scenario | Reason | Example |
|----------|--------|---------|
| Speed critical | O(1) average access | User ID lookup |
| Unordered data | No sorting needed | Caching values |
| Large dataset | Better performance | Database indexing |
| Null support needed | Can store null key | Optional parameters |
| Simple key-value | No complex ordering | Simple dictionary |

### Choose TreeMap When:

| Scenario | Reason | Example |
|----------|--------|---------|
| Sorted order | Auto-sorting by key | Leaderboards |
| Range queries | SubMap operations | Range searches |
| Min/Max access | First/last key needed | Priority management |
| Natural ordering | Comparable elements | Alphabetical lists |
| Iteration order | Must be predictable | Report generation |

---

## HashMap and TreeMap Methods

### Common Methods

| Method | Purpose | HashMap | TreeMap |
|--------|---------|---------|---------|
| `put(K key, V value)` | Add entry | O(1) | O(log n) |
| `get(Object key)` | Retrieve value | O(1) | O(log n) |
| `remove(Object key)` | Remove entry | O(1) | O(log n) |
| `containsKey(Object key)` | Check key exists | O(1) | O(log n) |
| `keySet()` | Get all keys | O(n) | O(n) |
| `values()` | Get all values | O(n) | O(n) |
| `size()` | Get map size | O(1) | O(1) |
| `isEmpty()` | Check if empty | O(1) | O(1) |

### TreeMap-Specific Methods

| Method | Purpose |
|--------|---------|
| `firstKey()` | Get lowest key |
| `lastKey()` | Get highest key |
| `headMap(K toKey)` | Keys less than toKey |
| `tailMap(K fromKey)` | Keys greater than or equal to fromKey |
| `subMap(K from, K to)` | Keys from fromKey to toKey |
| `descendingMap()` | Reverse order map |

---

## Summary

### Key Takeaways

**Maps in General:**
- Store key-value pairs
- Each key must be unique
- Multiple values can be identical
- Allow efficient data organization

**HashMap:**
- Uses hash table for O(1) average access
- No guaranteed order of entries
- Allows one null key and multiple null values
- Ideal for fast lookups and caching
- Better performance for large datasets

**TreeMap:**
- Uses red-black tree for O(log n) access
- Maintains sorted order by key
- Does not allow null keys
- Ideal for sorted data and range queries
- Better for ordered operations

**When to Choose:**

| HashMap | TreeMap |
|---------|---------|
| Speed is priority | Order is priority |
| Unordered data | Sorted data required |
| Large dataset | Range queries needed |
| Simple lookup | Complex navigation |

**Common Uses:**

| HashMap | TreeMap |
|---------|---------|
| Word frequency | Leaderboards |
| User authentication | Sorted inventories |
| Caching | Priority queues |
| Dictionaries | Range searches |

### Quick Reference

```
HashMap:      Optimized for speed
              └─ Use for: Fast lookups, caching, dictionaries

TreeMap:      Optimized for order
              └─ Use for: Sorted data, leaderboards, range queries

Performance:
  HashMap:    O(1) average access
  TreeMap:    O(log n) access

Ordering:
  HashMap:    No guaranteed order
  TreeMap:    Always sorted by key

Null Support:
  HashMap:    One null key allowed
  TreeMap:    No null keys allowed
```
