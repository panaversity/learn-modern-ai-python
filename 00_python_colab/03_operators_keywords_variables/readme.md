# Python Operators and Variables

A comprehensive guide to understanding Python operators and variables with clear definitions and well-commented code examples.

## Table of Contents

- [Overview](#overview)
- [Operators and Operands](#operators-and-operands)
  - [Unary Operators](#unary-operators-work-with-just-one-value)
  - [Binary Operators](#binary-operators-work-with-two-values)
- [Types of Operators in Python](#types-of-operators-in-python)
  - [1. Arithmetic Operators](#1-arithmetic-operators-for-math-calculations)
  - [2. Comparison Operators](#2-comparison-operators-for-comparing-values)
  - [3. Logical Operators](#3-logical-operators-for-combining-conditions)
  - [4. Assignment Operators](#4-assignment-operators-for-storing-values-in-variables)
  - [5. Identity Operators](#5-identity-operators-for-checking-if-objects-are-the-same-in-memory)
  - [6. Membership Operators](#6-membership-operators-for-checking-if-a-value-is-in-a-collection)
- [Python Keywords](#python-keywords)
- [Python Variables](#python-variables)
  - [Rules for Variable Names](#rules-for-variable-names)
  - [Naming Conventions](#naming-conventions)
  - [Multiple Variable Assignment](#multiple-variable-assignment)
  - [Deleting Variables](#deleting-variables)
- [License](#license)
- [Contributing](#contributing)

## Overview

This repository provides a beginner-friendly guide to Python operators and variables. Each concept is explained in simple terms with practical code examples to help solidify your understanding.

## Operators and Operands

**Operator**: A symbol that tells Python to perform a specific action or calculation (like `+`, `-`, `*`).  
**Operand**: The values or variables that the operator works on.

```python
# Example: In the expression 3 + 4
# + is the operator (it tells Python to add)
# 3 and 4 are the operands (the values being added)

result = 3 + 4  # The operator (+) works on the operands (3 and 4)
```

### Unary Operators (work with just one value)

Unary operators need only one value to work with.

```python
# Negative operator: Changes a positive number to negative or vice versa
x = 5
y = -x  # The - operator flips the sign of x, so y becomes -5
print(y)  # Output: -5

# Logical NOT: Flips True to False or False to True
a = True
b = not a  # The 'not' operator reverses the boolean value
print(b)  # Output: False

# Bitwise NOT: Flips each binary digit (0→1, 1→0)
x = 5  # In binary: 0101
y = ~x  # ~ flips all bits, resulting in -6 in decimal
print(y)  # Output: -6
```

### Binary Operators (work with two values)

Binary operators need two values to work with. These are covered in detail in the following sections.

## Types of Operators in Python

### 1. Arithmetic Operators (for math calculations)

```python
a = 10
b = 3

# Addition: Adds two numbers
print(a + b)   # Output: 13

# Subtraction: Subtracts second number from first
print(a - b)   # Output: 7

# Multiplication: Multiplies two numbers
print(a * b)   # Output: 30

# Division: Divides first number by second (always gives a float)
print(a / b)   # Output: 3.3333...

# Floor Division: Divides and rounds down to nearest whole number
print(a // b)  # Output: 3

# Modulus: Returns the remainder after division
print(a % b)   # Output: 1

# Exponentiation: Raises first number to power of second
print(a ** b)  # Output: 1000 (10³ = 10×10×10)
```

### 2. Comparison Operators (for comparing values)

```python
x = 10
y = 5

# Equal to: Checks if two values are the same
print(x == y)  # Output: False

# Not equal to: Checks if two values are different
print(x != y)  # Output: True

# Greater than: Checks if first value is larger than second
print(x > y)   # Output: True

# Less than: Checks if first value is smaller than second
print(x < y)   # Output: False

# Greater than or equal to: Checks if first value is at least as large as second
print(x >= y)  # Output: True

# Less than or equal to: Checks if first value is at most as large as second
print(x <= y)  # Output: False
```

### 3. Logical Operators (for combining conditions)

```python
x = True
y = False

# AND: Returns True only if both conditions are True
print(x and y)  # Output: False (since y is False)

# OR: Returns True if at least one condition is True
print(x or y)   # Output: True (since x is True)

# NOT: Reverses the result, True becomes False and vice versa
print(not x)    # Output: False (opposite of True)
```

### 4. Assignment Operators (for storing values in variables)

```python
# Simple assignment: Stores a value in a variable
x = 5           
print(x)        # Output: 5

# Add and assign: Adds right value to the variable, then updates variable
x += 3          # Same as writing x = x + 3
print(x)        # Output: 8

# Subtract and assign: Subtracts right value from variable, then updates variable
x -= 3          # Same as writing x = x - 3
print(x)        # Output: 5

# Multiply and assign: Multiplies variable by right value, then updates variable
x *= 3          # Same as writing x = x * 3
print(x)        # Output: 15

# Divide and assign: Divides variable by right value, then updates variable
x /= 3          # Same as writing x = x / 3
print(x)        # Output: 5.0 (notice it's now a float)

# Floor divide and assign: Divides and rounds down, then updates variable
x //= 3         # Same as writing x = x // 3
print(x)        # Output: 1.0
```

### 5. Identity Operators (for checking if objects are the same in memory)

```python
# Create two lists with the same values
a = [1, 2, 3]
b = [1, 2, 3]
# Make c point to the same list as a
c = a

# 'is' checks if two variables point to exactly the same object in memory
print(a is c)      # Output: True (they point to the same list)
print(a is b)      # Output: False (different lists with same values)

# '==' checks if two variables have the same values
print(a == b)      # Output: True (the lists contain the same values)

# 'is not' checks if two variables point to different objects
print(a is not b)  # Output: True (they are different objects)

# We can see the memory locations using id()
print(id(a))       # Prints memory address, e.g., 134193929171776
print(id(b))       # Different address, e.g., 134193940649408
print(id(c))       # Same as a's address, confirming they are the same object
```

### 6. Membership Operators (for checking if a value is in a collection)

```python
# Create a list of numbers
my_list = [1, 2, 3, 4, 5]

# 'in' checks if a value exists in a collection
print(3 in my_list)       # Output: True (3 is in the list)

# 'not in' checks if a value doesn't exist in a collection
print(10 not in my_list)  # Output: True (10 is not in the list)

# These operators also work with strings
my_string = "Operation Badar"
print('O' in my_string)          # Output: True (the letter O is in the string)
print('Hello' not in my_string)  # Output: True (the word Hello is not in the string)
```

## Python Keywords

**Keywords**: Special reserved words in Python that have predefined meanings. You cannot use them as variable names.

```python
import keyword
print(keyword.kwlist)  # Prints all Python keywords
# Example keywords: 'if', 'else', 'for', 'while', 'def', 'class', 'True', 'False', etc.
```

## Python Variables

**Variables**: Names that store data values. Think of them as labeled boxes where you can put information.

### Rules for Variable Names

1. Can contain letters, digits, and underscores
2. Cannot start with a digit
3. Are case-sensitive (`name` and `Name` are different variables)
4. Cannot be Python keywords

```python
# Good variable names
name = "Alice"         # Stores a string
_age = 25              # Starts with underscore (valid)
salary2024 = 50000     # Contains numbers (but doesn't start with one)
my_variable = "Python" # Uses underscores for readability

# Bad variable names (these would cause errors)
# 2name = "Bob"          # Cannot start with a number
# my-variable = "Error"  # Cannot use hyphens
# class = "CS101"        # Cannot use Python keywords as variable names
```

### Naming Conventions

```python
# snake_case for variables and functions
total_cost = 100
def calculate_tax():
    pass

# CamelCase or PascalCase for classes
class BankAccount:
    pass

# UPPER_CASE for constants (values that don't change)
MAX_SPEED = 120
PI = 3.14159

# _single_underscore for "private" variables (hint to other programmers)
_password = "secret123"

# __double_underscore for special Python name mangling
__secret_key = "very_secret"

# __dunder__ for special Python methods
def __init__(self):
    pass
```

### Multiple Variable Assignment

```python
# You can assign multiple values at once (very handy!)
x, y, z = 1, 2.5, "Python"
# This creates three variables:
# x gets 1 (an integer)
# y gets 2.5 (a float)
# z gets "Python" (a string)
print(x, y, z)  # Output: 1 2.5 Python
```

### Deleting Variables

```python
# Create a variable
x = 10
print(x)  # Output: 10

# Delete the variable from memory
del x     # The variable x no longer exists

# If we try to use x now, we'll get an error
# print(x)  # Would raise: NameError: name 'x' is not defined
```

