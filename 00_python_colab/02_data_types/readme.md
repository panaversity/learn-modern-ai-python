## Overview

This repository contains a comprehensive summary of Python's fundamental data types, explained in a beginner-friendly manner. The guide uses simple analogies and practical examples to make complex concepts accessible to new programmers.

## Table of Contents

- [Numeric Types](#numeric-types)
  - [Integer (int)](#integer-int)
  - [Floating-Point (float)](#floating-point-float)
  - [Complex (complex)](#complex-complex)
- [Boolean (bool)](#boolean-bool)
- [Sequence Types](#sequence-types)
  - [String (str)](#string-str)
  - [List (list)](#list-list)
  - [Tuple (tuple)](#tuple-tuple)
  - [Range (range)](#range-range)
- [Set Types](#set-types)
  - [Set (set)](#set-set)
  - [Frozen Set (frozenset)](#frozen-set-frozenset)
- [Mapping Type](#mapping-type)
  - [Dictionary (dict)](#dictionary-dict)
- [Binary Types](#binary-types)
  - [Bytes (bytes)](#bytes-bytes)
  - [Bytearray (bytearray)](#bytearray-bytearray)
  - [Memoryview (memoryview)](#memoryview-memoryview)
- [None Type](#none-type)
- [Additional Topics](#additional-topics)
  - [Integer Literals and Memory Sharing](#integer-literals-and-memory-sharing)
  - [Type Casting](#type-casting)
  - [Truthy and Falsy Values](#truthy-and-falsy-values)
  - [isinstance() Function](#isinstance-function)

## Numeric Types

### Integer (int)

Whole numbers without any decimal part, like `1`, `2`, `3`, `-1`, `-2`, etc.

```python
num_int = 42
print(type(num_int), "num_int =", num_int)  # <class 'int'> num_int = 42
```

### Floating-Point (float)

Numbers with decimal points, useful for measurements and precise values.

```python
num_float = 3.14
print(type(num_float), "num_float =", num_float)  # <class 'float'> num_float = 3.14
```

### Complex (complex)

Numbers with both real and imaginary components, used in advanced math and engineering.

```python
num_complex = 2 + 3j
print(type(num_complex), "num_complex =", num_complex)  # <class 'complex'> num_complex = (2+3j)

# Accessing individual parts
z = 3 + 4j
print("Real Part:", z.real)        # 3.0
print("Imaginary Part:", z.imag)   # 4.0
```

## Boolean (bool)

Simple True/False values, named after mathematician George Boole.

```python
is_python_fun = True
print(type(is_python_fun), "is_python_fun =", is_python_fun)  # <class 'bool'> is_python_fun = True

# Useful for decision making
if is_python_fun:
    print("Let's learn more Python!")
```

## Sequence Types

### String (str)

A sequence of characters (text), created using quotes.

```python
text_double = "Hello, Python!"  # Using double quotes
text_single = 'Hello, Python!'  # Using single quotes
text_multi = '''This is a multi-line
string using triple quotes'''    # Triple quotes for multi-line strings

print(type(text_double), "text_double =", text_double)  # <class 'str'> text_double = Hello, Python!
```

### List (list)

An ordered, mutable collection that can store different types of data.

```python
my_list = [1, 2, 3, "Python", 3.14, 3+2j]
print(type(my_list), "my_list =", my_list)  # <class 'list'> my_list = [1, 2, 3, 'Python', 3.14, (3+2j)]

# Lists can be modified
my_list[0] = 100
print("Modified list:", my_list)  # Modified list: [100, 2, 3, 'Python', 3.14, (3+2j)]
```

### Tuple (tuple)

An ordered, immutable collection similar to lists but cannot be changed after creation.

```python
my_tuple = (1, 2, 3, "AI", 2.71, False)
print(type(my_tuple), "my_tuple =", my_tuple)  # <class 'tuple'> my_tuple = (1, 2, 3, 'AI', 2.71, False)

# Trying to modify a tuple will cause an error:
# my_tuple[0] = 100  # TypeError: 'tuple' object does not support item assignment
```

### Range (range)

Represents a sequence of numbers, often used in loops.

```python
num_range = range(1, 10, 2)  # range(start, stop, step)
print(type(num_range), "num_range step =", num_range.step)  # <class 'range'> num_range step = 2

# To see all values in the range
print("Values in num_range:")
for i in num_range:
    print(i)  # Prints: 1, 3, 5, 7, 9
```

## Set Types

### Set (set)

A mutable collection of unique items with no duplicates.

```python
my_set = {1, 2, 33, 4, 4, 5}  # Notice the duplicate 4
print(type(my_set), "my_set =", my_set)  # <class 'set'> my_set = {1, 2, 33, 4, 5}

# Adding to a set
my_set.add(100)
print("Set after adding 100:", my_set)  # Set after adding 100: {1, 2, 33, 4, 5, 100}
```

### Frozen Set (frozenset)

An immutable version of a set that cannot be changed after creation.

```python
frozen_set = frozenset([11, 2, 3, 4, 4, 5])
print(type(frozen_set), "frozen_set =", frozen_set)  # <class 'frozenset'> frozen_set = frozenset({11, 2, 3, 4, 5})

# Trying to modify a frozen set will cause an error:
# frozen_set.add(100)  # AttributeError: 'frozenset' object has no attribute 'add'
```

## Mapping Type

### Dictionary (dict)

Stores key-value pairs, similar to a real dictionary with words and definitions.

```python
my_dict = {"name": "Alice", "age": 25, "language": "Python"}
print(type(my_dict), "my_dict =", my_dict)  # <class 'dict'> my_dict = {'name': 'Alice', 'age': 25, 'language': 'Python'}

# Access values using their keys
print("Name:", my_dict["name"])  # Name: Alice
print("Age:", my_dict["age"])    # Age: 25

# Dictionaries are mutable
my_dict["age"] = 26
print("Updated dictionary:", my_dict)  # Updated dictionary: {'name': 'Alice', 'age': 26, 'language': 'Python'}

# Adding new key-value pairs
my_dict["hobby"] = "Coding"
print("Dictionary with new key:", my_dict)  # Dictionary with new key: {'name': 'Alice', 'age': 26, 'language': 'Python', 'hobby': 'Coding'}
```

## Binary Types

### Bytes (bytes)

Immutable sequence of bytes, useful for handling binary data.

```python
byte_data = b"Hello"  # The 'b' prefix indicates bytes data
print(type(byte_data), "byte_data =", byte_data)  # <class 'bytes'> byte_data = b'Hello'

# Each character in bytes corresponds to its ASCII value
print("First byte:", byte_data[0])  # First byte: 72 (ASCII value for 'H')

# Example for reading/writing binary data:
# with open("image.jpg", "rb") as image_file:
#     image_data = image_file.read()
# 
# with open("copy.jpg", "wb") as target_file:
#     target_file.write(image_data)
```

### Bytearray (bytearray)

Mutable sequence of bytes that can be modified after creation.

```python
byte_array = bytearray([65, 66, 67, 69])  # ASCII values: A=65, B=66, C=67, E=69
print(type(byte_array), "byte_array =", byte_array)  # <class 'bytearray'> byte_array = bytearray(b'ABCE')

# Inspecting bytes
print("First byte value:", byte_array[0])  # First byte value: 65
print("First byte as character:", chr(byte_array[0]))  # First byte as character: A

# Converting to a string
print("Decoded string:", byte_array.decode('utf-8'))  # Decoded string: ABCE

# Modifying bytearrays
ba = bytearray(b"hello")
print("Before change:", ba)  # Before change: bytearray(b'hello')
ba[0] = 72  # Change 'h' (ASCII 104) to 'H' (ASCII 72)
print("After change:", ba)  # After change: bytearray(b'Hello')
```

### Memoryview (memoryview)

An efficient way to work with binary data without making copies.

```python
mem_view = memoryview(b"Operation Badar")
print(type(mem_view), "mem_view =", mem_view)  # <class 'memoryview'> mem_view = <memory at 0x...>

# Extracting parts of the data
print("First 5 bytes as bytes:", bytes(mem_view[0:5]))  # First 5 bytes as bytes: b'Opera'
```

## None Type

Represents the absence of a value or a null value.

```python
x = None
y = None
z = x

print("Type of None:", type(x))  # Type of None: <class 'NoneType'>
print("x == y:", x == y)  # x == y: True (same value)
print("x is y:", x is y)  # x is y: True (same object - None is a singleton)

# Functions with no return statement return None by default
def function_that_returns_nothing():
    print("This function did something but doesn't return a value")

result = function_that_returns_nothing()
print("Result:", result)  # Result: None

# None is treated as False in conditions
if None:
    print("This won't print")
else:
    print("None is treated as False in conditions")  # This will print
```

## Additional Topics

### Integer Literals and Memory Sharing

Python optimizes memory by reusing objects for small integers.

```python
# Integers between -5 and 256 share the same object
small_num1 = 42
small_num2 = 42
print("small_num1 is small_num2:", small_num1 is small_num2)  # True - same object

# Larger integers are separate objects
large_num1 = 1000
large_num2 = 1000
print("large_num1 is large_num2:", large_num1 is large_num2)  # False - different objects
print("large_num1 == large_num2:", large_num1 == large_num2)  # True - same value
```

### Type Casting

Converting data from one type to another.

```python
# Implicit type casting (automatic)
i = 10          # Integer
j = 20.6        # Float
f = i + j       # i is automatically converted to float
print("i + j =", f, "Type:", type(f))  # i + j = 30.6 Type: <class 'float'>

# Explicit type casting (manual)
f1 = 66.89
i1 = int(f1)  # Converts float to int (truncates decimal part)
print(f"{f1} as an integer:", i1)  # 66.89 as an integer: 66

# String to float
s = "25.8"
f2 = float(s)
print(f"The string '{s}' as a float:", f2)  # The string '25.8' as a float: 25.8

# String with decimal to integer (two-step process)
i2 = int(float("25.8"))
print(f"The string '25.8' as an integer:", i2)  # The string '25.8' as an integer: 25

# Converting to boolean
print("42 as a boolean:", bool(42))             # True (non-zero is True)
print("0 as a boolean:", bool(0))               # False (zero is False)
print("'Hello' as a boolean:", bool("Hello"))   # True (non-empty string is True)
print("'' as a boolean:", bool(""))             # False (empty string is False)
```

### Truthy and Falsy Values

Some values are treated as True or False in conditions.

```python
# Truthy values (treated as True):
truthy_examples = [42, -1, "hello", [1, 2], {"a": 1}]

print("Truthy values (these are treated as True):")
for value in truthy_examples:
    print(f"  {value} is {bool(value)}")

# Falsy values (treated as False):
falsy_examples = [0, None, "", [], {}, set()]

print("\nFalsy values (these are treated as False):")
for value in falsy_examples:
    print(f"  {repr(value)} is {bool(value)}")

# Example in a condition:
name = ""  # Empty string - falsy
if name:
    print(f"Hello, {name}!")
else:
    print("Hello, anonymous user!")  # This will print
```

### isinstance() Function

Used to check if a value is of a certain type.

```python
age = 20
weight = 66.89

# Checking specific types
print("Is age an integer?", isinstance(age, int))           # True
print("Is weight an integer?", isinstance(weight, int))     # False
print("Is weight a float?", isinstance(weight, float))      # True

# Checking multiple types at once
print("Is age either an int or float?", isinstance(age, (int, float)))          # True
print("Is weight either an int or float?", isinstance(weight, (int, float)))    # True

# Practical application
def greet_person(name):
    # Validate input type
    if not isinstance(name, str):
        print("Error: name must be a string")
        return
    
    print(f"Hello, {name.title()}!")

greet_person("alice")  # Works fine: Hello, Alice!
greet_person(123)      # Shows error message
```

