# Python Collections: Lists, Tuples, and Dictionaries 📚

Welcome! This guide provides a simple, clear explanation of three important Python collections: **Lists**, **Tuples**, and **Dictionaries**.  
Perfect for beginners who want easy definitions, examples, and real-life comparisons!

---

## 📜 1. Lists in Python

**Easy Definition:**  
A **list** is like a **shopping bag** — you can put things in, remove them, change them, and they stay in the order you added them.

### Characteristics:
- **Ordered:** Items stay in the order you add them.
- **Mutable:** You can change, add, or remove items.
- **Indexed:** Each item has a position (starting at 0).
- **Dynamic Size:** Lists can grow or shrink.
- **Heterogeneous:** Can contain different data types.
- **Supports Duplicates:** Same item can appear multiple times.

### 🌟 Creating a List:
```python
# Example: A shopping list
fruits: list = ["apple", "banana", "cherry"]

# Example: A list of lucky numbers
numbers: list = [10, 20, 30, 40]
```

### 🌟 Accessing List Elements:
```python
print(fruits[0])    # Output: apple
print(fruits[-1])   # Output: cherry
```

### 🌟 Modifying Lists:
```python
fruits[0] = "watermelon"
print(fruits)  # ['watermelon', 'banana', 'cherry']
```

### 🌟 List Slicing:
```python
print(fruits[0:2])  # ['watermelon', 'banana']
```

---

## 📜 2. Common List Methods

### 🌟 Appending and Extending:
```python
fruits.append("orange")
fruits.extend(["grapes", "pineapple"])
```

### 🌟 Removing Elements:
```python
fruits.remove("banana")
fruits.pop()
fruits.pop(0)
```

### 🌟 Sorting a List:
```python
numbers.sort()
numbers.sort(reverse=True)
fruits.sort(key=len)              # By length
fruits.sort(key=lambda x: x[-1])  # By last character
```

---

## 📜 3. Iterating Over Lists
```python
for fruit in fruits:
    print(fruit)
```

### 🌟 List Comprehension:
```python
squares = [x**2 for x in [1, 2, 3, 4, 5]]
print(squares)  # [1, 4, 9, 16, 25]
```

---

## 📜 4. Tuples in Python

**Easy Definition:**  
A **tuple** is like a **sealed box** — you can look inside, but you can’t change anything.

### Characteristics:
- **Ordered**
- **Immutable**
- **Hashable** (usable as dictionary keys)

### 🌟 Creating a Tuple:
```python
tuple1: tuple = ("apple", "banana", "cherry")
tuple2: tuple = (10, 20, 30)
```

### 🌟 Accessing Tuples:
```python
print(tuple1[0])  # apple
```

### 🌟 Attempting to Modify Tuple (Not Allowed):
```python
# tuple1[0] = "watermelon"  
# ❌ Error: 'tuple' object does not support item assignment
```

---

## 📜 5. Dictionaries in Python

**Easy Definition:**  
A **dictionary** is like a **real dictionary** — you search using a word (key) and get its meaning (value).

### Characteristics:
- **Ordered**
- **Mutable**
- **Unindexed** (access with keys, not numbers)
- **No Duplicate Keys**

### 🌟 Creating a Dictionary:
```python
person: dict = {
    "name": "Alice",
    "age": 25,
    "city": "New York"
}
```

### 🌟 Accessing Values:
```python
print(person["name"])      # Alice
print(person.get("city"))  # New York
```

### 🌟 Modifying a Dictionary:
```python
person["age"] = 26
person["email"] = "alice@example.com"
```

### 🌟 Deleting Items:
```python
del person["city"]
email = person.pop("email")
```

---

## 📜 6. Dictionary Methods

```python
print(person.keys())
print(person.values())
print(person.items())

person.clear()

person.update({"name": "Bob", "age": 30})
```

---

## 📜 7. Iterating Over a Dictionary

```python
# Loop through keys
for key in person:
    print(key)

# Loop through values
for value in person.values():
    print(value)

# Loop through key-value pairs
for key, value in person.items():
    print(f"{key}: {value}")
```

---

## 📜 8. Practical Examples

### 🌟 Phonebook Example:
```python
phonebook = {
    "Alice": "1234",
    "Bob": "5678",
    "Charlie": "91011"
}
print(phonebook["Bob"])
```

### 🌟 Counting Word Frequencies:
```python
text = "apple banana apple orange banana apple"
words = text.split()
word_count = {}

for word in words:
    if word in word_count:
        word_count[word] += 1
    else:
        word_count[word] = 1

print(word_count)
```

---

## 📜 9. Common Pitfalls

- ❌ **Accessing a non-existing key**  
  → Raises KeyError.  
  ➡ **Use `.get()`** instead if unsure.

- ❌ **Keys must be immutable**  
  → Only strings, numbers, and tuples can be dictionary keys.

---

## 📜 10. Dictionary Comprehensions

### 🌟 Easy Way to Create a Dictionary:
```python
numbers = [1, 2, 3, 4, 5]
doubled = {num: num*2 for num in numbers}
print(doubled)  # {1: 2, 2: 4, 3: 6, 4: 8, 5: 10}
```

---

# 🎯 Quick Summary with Real-Life Examples:

| Python Collection | Real-Life Example |
|-------------------|-------------------|
| List 🛒           | Shopping List      |
| Tuple 📦          | Sealed Box         |
| Dictionary 📖     | Real Dictionary    |

