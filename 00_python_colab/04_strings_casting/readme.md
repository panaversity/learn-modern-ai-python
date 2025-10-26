# 📚 Python Strings 

Welcome!  
This document covers everything you need to know about **Python Strings**, explained in **easy language** with **simple examples and comments**.

---

## 🔹 What is a String?

- A **string** is a sequence of characters like letters, numbers, or symbols.
- In Python, strings are **immutable** (you can't change them after creation).

---

## 🔹 Creating Strings

You can create strings using **single**, **double**, or **triple quotes**:

```python
# Using single quotes
single_quote = 'Hello, World!'

# Using double quotes
double_quote = "Hello, World!"

# Using triple quotes for multi-line strings
multi_line = '''Hello,
World!'''

# Using raw strings (special characters are treated as normal text)
raw_string = r'Hello\nWorld!'
```

---

## 🔹 Escape Sequences

**Escape sequences** are special codes inside strings starting with a backslash (`\`):

```python
print("Hello,\tWorld!")   # \t adds a tab space
print("Hello,\nWorld!")   # \n moves to a new line
print("Hello, \"World!\"")  # \" prints double quotes inside the string
print("Hello,\\World!")   # \\ prints a single backslash
```

---

## 🔹 Unicode Characters

Python supports **Unicode**, meaning it can handle characters from many languages:

```python
print("\u0041")  # Prints 'A'
print("\u0042")  # Prints 'B'
```

---

## 🔹 String Operations

You can **join**, **slice**, **find length**, and **change case** of strings:

```python
# String Concatenation (joining strings)
greeting = "Hello" + ", " + "World!"  # Result: "Hello, World!"

# Indexing (getting one character)
first_char = "Python"[0]  # 'P'
second_char = "Python"[1]  # 'y'

# Slicing (getting part of string)
text = "Python Programming"
first_word = text[0:6]  # 'Python'
last_word = text[7:]    # 'Programming'

# Length of string
length = len("Hello World")  # 11

# Changing case
upper_case = "hello".upper()  # 'HELLO'
lower_case = "HELLO".lower()  # 'hello'
```

---

## 🔹 String Methods

### ➡️ split()

Breaks a string into parts:

```python
# Split by comma
text = "apple,banana,orange"
fruits = text.split(",")  # ['apple', 'banana', 'orange']

# Split by spaces
sentence = "Hello World Python"
words = sentence.split()  # ['Hello', 'World', 'Python']
```

---

### ➡️ join()

Joins a list of strings into one string:

```python
fruits = ['apple', 'banana', 'orange']
text = ", ".join(fruits)  # "apple, banana, orange"
```

---

### ➡️ replace()

Replaces part of a string with something else:

```python
text = "Hello, World!"
new_text = text.replace("Hello", "Hi")  # "Hi, World!"
```

---

### ➡️ find() and index()

Finds the **position** of a substring:

```python
text = "Hello, World!"

# find() returns the index or -1 if not found
position = text.find("World")  # 7
not_found = text.find("Python")  # -1

# index() returns the index but gives an error if not found
position = text.index("World")  # 7
# text.index("Python") → Raises ValueError
```

---

### ➡️ count()

Counts how many times something appears:

```python
text = "hello hello world"
count = text.count("hello")  # 2
```

---

## 🔹 String Formatting (Inserting values into strings)

### ➡️ Using % Operator

```python
name = "John"
age = 30
message = "My name is %s and I am %d years old." % (name, age)
# "My name is John and I am 30 years old."
```

---

### ➡️ Using str.format() Method

```python
name = "John"
age = 30
message = "My name is {} and I am {} years old.".format(name, age)
# "My name is John and I am 30 years old."

# Using indexes
message = "I am {1} years old and my name is {0}.".format(name, age)
# "I am 30 years old and my name is John."
```

---

### ➡️ Using f-Strings (Best Way)

```python
name = "John"
age = 30
message = f"My name is {name} and I am {age} years old."
# "My name is John and I am 30 years old."
```

---

## 🔹 String Memory Management

Python tries to **save memory** by reusing strings.

### ➡️ String Literal Pool

```python
# Same small strings are stored only once
a = "hello"
b = "hello"
print(a is b)  # True
```

---

### ➡️ String Interning

```python
import sys

# Interning manually
a = sys.intern("hello world!")
b = sys.intern("hello world!")
print(a is b)  # True
```

---

### ➡️ Strings Not Always Interned

```python
# Long strings may not be interned automatically
a = "this is a very long string"
b = "this is a very long string"
print(a is b)  # Might be False

# Dynamically created strings
a = "hello"
b = "world"
c = a + b
d = "helloworld"
print(c is d)  # False
```

---

## 🔹 String Repetition

You can **repeat** strings using `*`:

```python
# Repeat a character 20 times
separator = "-" * 20  # "--------------------"

# Repeat patterns
pattern = "*" * 5  # "*****"

# Example: Create a simple triangle
for i in range(1, 6):
    print("*" * i)
# Output:
# *
# **
# ***
# ****
# *****
```

---

## 🔹 String Comparisons

Python compares strings by the **dictionary order** (alphabetical):

```python
print("apple" < "banana")  # True
print("apple" == "Apple")  # False (case matters)
print("abc" < "abd")       # True
```

---

## 🔹 Type Casting with Strings

Convert between **strings**, **integers**, **floats**, and **lists**:

```python
# String to Integer
num_str = "123"
num_int = int(num_str)  # 123

# Integer to String
num = 456
num_str = str(num)  # "456"

# String to Float
pi_str = "3.14"
pi_float = float(pi_str)  # 3.14

# String to List
list_of_chars = list("Python")  # ['P', 'y', 't', 'h', 'o', 'n']

# List to String
joined_string = ''.join(['P', 'y', 't', 'h', 'o', 'n'])  # "Python"
```

---

# ✅ Conclusion

- **Strings** are a very important data type in Python.
- You can **create**, **modify**, **analyze**, and **format** strings easily.
- **Understanding string memory** and **optimization** can help you write better Python programs.
