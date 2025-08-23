# 📦 Modules and 🍳 Functions in Python

---

## 📦 MODULES in Python

### What is a Module?
> A **module** is like a **toolbox** — it holds ready-made tools (functions, variables, classes) you can use anytime.

---

## 📂 Types of Modules

| Type | Description |
|:---|:---|
| 🚀 Built-in Modules | Already available inside Python (e.g., `math`, `random`) |
| ✍️ User-created Modules | You create your own modules |
| 🌍 External Modules | Downloaded from the internet (e.g., `requests`) |

---

### 1. 🚀 Built-in Module Example
```python
import math  # Import the math toolbox

print(math.sqrt(25))  # ➡️ 5.0
```
🧠 **Real-life example**: Like using your calculator’s √ button.

---

### 2. ✍️ User-created Module Example
Create a file `mymodule.py`:
```python
# mymodule.py
def add(a, b):
    return a + b
```
Use it in another file:
```python
import mymodule

print(mymodule.add(5, 3))  # ➡️ 8
```
🧠 **Real-life example**: Like writing your own recipe.

---

### 3. 🌍 External Module Example
Install first:
```bash
pip install requests
```
Then use:
```python
import requests

website = requests.get("https://www.example.com")
print(website.status_code)
```
🧠 **Real-life example**: Like downloading a new cooking recipe.

---

## 🔄 IMPORTING METHODS

| Syntax | Usage |
|:---|:---|
| `import module` | Full access |
| `from module import item` | Import specific |
| `from module import item as alias` | Rename imported item |
| `from module import *` | Import all (not recommended) |

Example:
```python
import math
print(math.sqrt(16))

from math import sqrt
print(sqrt(16))

from math import pi as circle_number
print(circle_number)

from math import *
print(sqrt(36))
```

---

# 🍳 FUNCTIONS in Python

## What is a Function?
> A **function** is like a **recipe card** — follow the steps to get a result.

---

## 📋 Simple Function Example
```python
def greet():
    """Says hello"""
    print("Hello World!")

greet()
```
🧠 **Real-life example**: Like greeting someone at the door.

---

## 🍔 Function With Inputs (Arguments)
```python
def make_sandwich(bread, filling="cheese"):
    print(f"Making {filling} sandwich with {bread} bread")

make_sandwich("whole wheat")
make_sandwich(filling="ham", bread="white")
```
🧠 **Real-life example**: Ordering your sandwich.

---

## 🎒 Special Argument Types

| Symbol | Meaning |
|:---|:---|
| `*args` | Multiple positional arguments |
| `**kwargs` | Multiple named arguments |

```python
def food_report(*fruits, **prices):
    print("Fruits:", fruits)
    print("Prices:", prices)

food_report("apple", "banana", apple=1.0, banana=0.5)
```
🧠 **Real-life example**: Bag full of fruits with labels.

---

## 🎯 Returning Values
```python
def calculate(num1, num2):
    return num1 + num2, num1 * num2

sum_result, product_result = calculate(3, 4)
print(sum_result)    # 7
print(product_result) # 12
```
🧠 **Real-life example**: Cooking and getting two dishes from one recipe.

---

## ⚡ Lambda Functions (One-Line Recipes)
```python
square = lambda x: x * x
print(square(5))  # ➡️ 25
```
🧠 **Real-life example**: Quick tea recipe.

---

## 📦 Generator Functions (Yield Values)
```python
def count_up_to(max):
    num = 1
    while num <= max:
        yield num
        num += 1

counter = count_up_to(3)

print(next(counter))  # 1
print(next(counter))  # 2
print(next(counter))  # 3
```
🧠 **Real-life example**: Delivering pizza slice by slice.

---

# 🌍 VARIABLE SCOPE

| Type | Meaning |
|:---|:---|
| Global Variable | Accessible everywhere |
| Local Variable | Accessible inside the function only |

```python
global_var = "I'm everywhere!"

def test_scope():
    local_var = "I'm only here!"
    print(global_var)

test_scope()
# print(local_var) ❌ Error: local_var only inside function
```
🧠 **Real-life example**: 
- Global ➔ Everyone uses it.
- Local ➔ Private kitchen stock.

---

# ♻️ RECURSION (Function Calling Itself)
```python
def factorial(n):
    if n == 1:
        return 1
    else:
        return n * factorial(n-1)

print(factorial(5))  # ➡️ 120
```
🧠 **Real-life example**: Russian dolls inside each other.

---

# 🛠️ TIPS & TRICKS

### Type Hints
```python
def multiply(x: int, y: int) -> int:
    return x * y
```

### Return Multiple Values
```python
def get_info() -> tuple[str, int]:
    return ("Alice", 30)
```

### Argument Order
```python
def example(a, b=2, *c, d, **e):
    pass
```
🧠 **Order**: Normal ➔ Default ➔ *args ➔ keyword-only ➔ **kwargs

---

# 🌟 Key Concepts (SUPER EASY)

| Word | Meaning |
|:---|:---|
| Module | Ready-made toolbox |
| Function | Recipe card |
| Arguments | Ingredients you provide |
| Return | Dish you get |
| Scope | Where you can use variables |
| Recursion | Function repeating itself |
| Generator | Magic box giving items one-by-one |

---

# 🧠 QUICK REMINDERS

✅ Use `def` to create a function  
✅ Use `return` to send back a result  
✅ Use `yield` to create a generator  
✅ Use `*args` for many items  
✅ Use `**kwargs` for many named items  
✅ Keep functions **small, simple, and focused**

