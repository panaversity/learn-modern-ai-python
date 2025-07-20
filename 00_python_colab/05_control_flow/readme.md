# 🌟 Control Flow, Decision Making, and Loops in Python

## 1. What is Control Flow?

➔ **Control flow** means how your program decides **which code to run first, next, or skip** based on some conditions.

Python uses:
- `if`
- `elif`
- `else`
- **Comparison operators** (`>`, `<`, `==`, etc.)
- **Logical operators** (`and`, `or`, `not`)

---

## 2. Comparison Operators

➔ Used to **compare** two values.  
They **return** `True` or `False`.

| Operator | Meaning                  | Example             |
|:--------:|:-------------------------:|:-------------------:|
| ==       | Equal to                  | `5 == 5 → True`      |
| !=       | Not equal to               | `5 != 3 → True`      |
| >        | Greater than               | `7 > 3 → True`       |
| <        | Less than                  | `2 < 8 → True`       |
| >=       | Greater than or equal to   | `5 >= 5 → True`      |
| <=       | Less than or equal to      | `3 <= 4 → True`      |

### Example:
```python
x: int = 10
y: int = 20

print("x == y =", x == y)  # False
print("x != y =", x != y)  # True
print("x > y  =", x > y)   # False
print("x < y  =", x < y)   # True
print("x >= y =", x >= y)  # False
print("x <= y =", x <= y)  # True
```

---

## 3. Logical Operators

➔ Combine multiple conditions.

| Operator | Meaning                          | Example                   |
|:--------:|:---------------------------------:|:-------------------------:|
| and      | Both conditions must be `True`    | `5 > 2 and 6 > 3 → True`   |
| or       | At least one must be `True`        | `5 < 2 or 6 > 3 → True`    |
| not      | Reverses the condition            | `not (5 > 2) → False`      |

### Example:
```python
age: int = 25
is_student: bool = True

if age > 18 and is_student:
    print("You are eligible for a student discount.")

if age < 12 or age > 60:
    print("You qualify for a special discount.")

if not is_student:
    print("You are not a student.")
```

---

## 4. if Statement

➔ **Check a condition**, and if it's `True`, run the code inside.

### Example:
```python
num: int = 10

if num > 0:
    print("The number is positive.")
```

---

## 5. else Statement

➔ **Run when the if condition is False**.

### Example:
```python
num: int = -5

if num > 0:
    print("The number is positive.")
else:
    print("The number is not positive.")
```

---

## 6. elif Statement

➔ **Check another condition** if the previous ones were False.

### Example:
```python
num: int = 0

if num > 0:
    print("The number is positive.")
elif num < 0:
    print("The number is negative.")
else:
    print("The number is zero.")
```

---

## 7. Nested if Statements

➔ **if inside another if**.

### Example:
```python
num: int = 10

if num > 0:
    if num % 2 == 0:
        print("The number is positive and even.")
    else:
        print("The number is positive and odd.")
else:
    print("The number is negative.")
```

---

## 8. Practical Examples

### Example 1: Simple Calculator
```python
operation: str = input("Enter the operation (+, -, *, /): ")
num1: float = float(input("Enter the first number: "))
num2: float = float(input("Enter the second number: "))

if operation == '+':
    result = num1 + num2
elif operation == '-':
    result = num1 - num2
elif operation == '*':
    result = num1 * num2
elif operation == '/':
    if num2 != 0:
        result = num1 / num2
    else:
        result = "Error: Division by zero."
else:
    result = "Invalid operation."

print("Result:", result)
```

---

### Example 2: Advanced Calculator
```python
def calculator():
    """
    A calculator that can do +, -, *, /, %, //, and ** operations.
    """
    while True:
        operation = input("Enter the operation (+, -, *, /, %, //, ** or 'q' to quit): ")

        if operation.lower() == 'q':
            break

        if operation not in ('+', '-', '*', '/', '%', '//', '**'):
            print("Invalid operation.")
            continue

        try:
            num1 = float(input("Enter the first number: "))
            num2 = float(input("Enter the second number: "))
        except ValueError:
            print("Invalid input. Please enter numbers only.")
            continue

        if operation == '+':
            result = num1 + num2
        elif operation == '-':
            result = num1 - num2
        elif operation == '*':
            result = num1 * num2
        elif operation == '/':
            if num2 != 0:
                result = num1 / num2
            else:
                print("Error: Division by zero.")
                continue
        elif operation == '%':
            result = num1 % num2
        elif operation == '//':
            if num2 != 0:
                result = num1 // num2
            else:
                print("Error: Division by zero.")
                continue
        elif operation == '**':
            result = num1 ** num2

        print("Result:", result)

calculator()
```

---

### Example 3: Grading System
```python
def grading_system(marks):
    """
    Returns grade based on marks.
    """
    if marks >= 90:
        grade = "A+"
    elif marks >= 80:
        grade = "A"
    elif marks >= 70:
        grade = "B"
    elif marks >= 60:
        grade = "C"
    elif marks >= 50:
        grade = "D"
    else:
        grade = "F"
    return grade

while True:
    try:
        marks = float(input("Enter the marks: "))
        if 0 <= marks <= 100:
            break
        else:
            print("Marks must be between 0 and 100.")
    except ValueError:
        print("Invalid input. Please enter a number.")

grade = grading_system(marks)

print(f"The grade for {marks} marks is: {grade}")
```

---

# ✨ match-case Statement (Python 3.10+)

➔ **A better way to replace multiple if-elif-else**.

### Example:
```python
def check_status(code):
    """
    Check HTTP status codes.
    """
    match code:
        case 200:
            print("OK")
        case 400:
            print("Bad Request")
        case 404:
            print("Not Found")
        case _:
            print("Unknown Status")

check_status(200)  # Output: OK
check_status(404)  # Output: Not Found
check_status(500)  # Output: Unknown Status
```

---

# 🔄 Loops and Iterations in Python

## 1. What are Loops?

➔ **Loops** repeat code multiple times.

Python has two main types:
- `for` loop — known number of times
- `while` loop — unknown number, repeat until condition becomes False

---

## 2. for Loop (Fixed repetitions)

### Example: List
```python
fruits: list = ["apple", "banana", "cherry"]

for fruit in fruits:
    print(fruit)
```
**Output:**
```
apple
banana
cherry
```

---

### Example: String
```python
word: str = "Python"

for letter in word:
    print(letter)
```
**Output:**
```
P
y
t
h
o
n
```

---

## 3. for Loop with else

➔ **`else` runs if the loop didn't break early.**

### Example:
```python
numbers = [1, 2, 3]

for num in numbers:
    print(num)
else:
    print("All numbers printed without break.")
```
**Output:**
```
1
2
3
All numbers printed without break.
```

---

# ✅ Summary

- **if-elif-else** is used for decision making.
- **Logical operators** combine multiple conditions.
- **match-case** is cleaner (Python 3.10+).
- **Loops** help repeat actions.
- **for-else** structure is useful for some special cases.

