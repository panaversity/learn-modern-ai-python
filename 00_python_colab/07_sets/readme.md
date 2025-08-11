# Python Sets

## 1. What is a Set?

A **Set** is a built-in Python data type that:
- ✅ Stores **unique elements** (no duplicates)
- ✅ Is **unordered** (no fixed position for items)
- ✅ Is **mutable** (can add/remove items)
- ✅ Only allows **immutable items** (numbers, strings, tuples)

**Example:**

```python
my_set = {1, 2, 3, "hello", (4, 5)}
# my_set = {[1, 2]}  ❌ Error! Lists are mutable.
```

---

## 2. How to Create a Set

- Use `{}` for non-empty sets.
- Use `set()` for empty sets (because `{}` creates a dictionary).

**Example:**

```python
set1 = {1, 2, 3}
set2 = set([4, 5, 6])  # Converts list to set
empty_set = set()      # ✅ Correct way
# wrong_empty = {}     ❌ Creates a dictionary!
```

---

## 3. Key Properties of Sets

### ✔ Unordered (No Indexing)

Items do not have a fixed position.  
Cannot access items using an index like `my_set[0]`.

```python
my_set = {10, 20, 30}
# print(my_set[0])  ❌ Error! No indexing.
```

---

### ✔ Unchangeable Items (But Set is Mutable)

You cannot modify an existing item directly,  
but you can **add** or **remove** items.

```python
my_set = {1, 2, 3}
my_set.add(4)       # ✅ Adds 4
my_set.remove(2)    # ✅ Removes 2
# my_set[0] = 99    ❌ Error! Cannot modify items directly.
```

---

### ✔ Only Unique Elements (No Duplicates)

```python
numbers = {1, 2, 2, 3}
print(numbers)  # Output: {1, 2, 3}  (duplicates removed)
```

---

### ✔ Only Immutable Items Allowed

Allowed: `int`, `float`, `str`, `tuple`  
Not Allowed: `list`, `dict`, `set`

```python
valid_set = {1, "hello", (4, 5)}
# invalid_set = {[1, 2]}  ❌ Error! Lists are mutable.
```

---

## 4. Set Methods

### 🔹 Adding & Removing Items

| Method      | Description                         | Example               |
|-------------|-------------------------------------|-----------------------|
| `add(x)`    | Adds one item                       | `my_set.add(5)`        |
| `remove(x)` | Removes item (error if missing)      | `my_set.remove(5)`     |
| `discard(x)`| Removes item (no error if missing)   | `my_set.discard(5)`    |
| `pop()`     | Removes a random item                | `my_set.pop()`         |
| `clear()`   | Removes all items                    | `my_set.clear()`       |

**Example:**

```python
nums = {1, 2, 3}
nums.add(4)       # {1, 2, 3, 4}
nums.discard(2)   # {1, 3, 4}
nums.remove(3)    # {1, 4}
nums.pop()        # Removes a random item
```

---

### 🔹 Set Operations (Math-like)

| Method                     | Description                      | Example               |
|-----------------------------|----------------------------------|------------------------|
| `union()` or `|`            | Combines two sets                | `set1.union(set2)`      |
| `intersection()` or `&`     | Common items in both sets        | `set1 & set2`           |
| `difference()` or `-`       | Items in set1 but not in set2     | `set1 - set2`           |
| `symmetric_difference()` or `^` | Items in either set, not both | `set1 ^ set2`           |

**Example:**

```python
A = {1, 2, 3}
B = {3, 4, 5}

print(A | B)   # {1, 2, 3, 4, 5} (union)
print(A & B)   # {3} (intersection)
print(A - B)   # {1, 2} (difference)
print(A ^ B)   # {1, 2, 4, 5} (symmetric difference)
```

---

### 🔹 Checking Relationships

| Method          | Description                           | Example             |
|------------------|---------------------------------------|---------------------|
| `issubset()`     | Checks if all items are in another set| `A.issubset(B)`      |
| `issuperset()`   | Checks if all items of another set are inside | `A.issuperset(B)` |
| `isdisjoint()`   | Checks if two sets have no common items| `A.isdisjoint(B)`   |

**Example:**

```python
X = {1, 2}
Y = {1, 2, 3}

print(X.issubset(Y))     # True (X is inside Y)
print(Y.issuperset(X))   # True (Y contains X)
print(X.isdisjoint({4})) # True (no common items)
```

---

## 5. FrozenSets (Immutable Sets)

A **frozenset** is like a set but **cannot be changed** after creation.  
Useful when you need an unchangeable set (e.g., as a dictionary key).

**Example:**

```python
frozen = frozenset([1, 2, 3])
# frozen.add(4)  ❌ Error! Frozensets are immutable.
```

---

## 6. Advanced Topics (Hashing & Memory)

### ✔ How Sets Work Internally (Hashing)

- Python uses **hashing** to store set items.
- Each item gets a unique **hash value** (like a fingerprint).
- Searching in sets is very **fast** (O(1) time complexity).

```python
print(hash("hello"))  # Output: Some unique number
```

---

### ✔ Garbage Collection in Sets

- Python **automatically** clears unused sets from memory.
- You can manually trigger garbage collection if needed:

```python
import gc
gc.collect()
```

---

## 7. When to Use Sets?

✅ Remove duplicates from a list.  
✅ Fast membership testing (`if x in my_set`).  
✅ Perform mathematical set operations (union, intersection, etc.).

**Example:**

```python
names = ["Alice", "Bob", "Alice", "Charlie"]
unique_names = set(names)  # Removes duplicates
print(unique_names)        # {'Alice', 'Bob', 'Charlie'}
```

---

## 8. Final Summary

✔ Sets store **unique**, **unordered** items.  
✔ Use `add()`, `remove()`, `discard()` to modify sets.  
✔ Use `union()`, `intersection()`, `difference()` for math operations.  
✔ **FrozenSets** are immutable sets.  
✔ Sets are great for **removing duplicates** and **fast lookups**!

---

# 📚 Happy Learning Python Sets!
