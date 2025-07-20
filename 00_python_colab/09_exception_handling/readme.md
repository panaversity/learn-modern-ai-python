# Python Exception Handling

## Overview

In Python, **exception handling** allows us to manage errors in a controlled way, preventing the program from crashing unexpectedly. This is done using blocks such as `try`, `except`, `else`, and `finally`. Proper exception handling improves the stability and robustness of a program.

## Table of Contents

- [Why Use Exception Handling?](#why-use-exception-handling)
- [Try Block](#1-the-try-block)
- [Except Block](#2-the-except-block)
- [Else Block](#3-the-else-block)
- [Finally Block](#4-the-finally-block)
- [Putting It All Together](#putting-it-all-together)
- [Example: Handling Errors in Real Life Code](#example-handling-errors-in-real-life-code)
- [Practice Problem](#practice-problem)
- [Throwing Exceptions in Functions](#throwing-exceptions-in-functions)
- [Custom Exceptions](#custom-exceptions)
- [Summary](#summary)

## Why Use Exception Handling?

1. **Prevents Crashes**: Keeps the program running even if something goes wrong.
2. **Graceful Error Recovery**: Instead of crashing, we show a helpful error message.
3. **Cleaner Code**: Helps separate error-handling logic from normal code.
4. **Resource Management**: Ensures resources (like files) are properly closed, even if there's an error.

---

## 1. The Try Block

The `try` block is where we place code that may cause an error. If an error happens, the program will jump to the `except` block.

```python
try:
    result = 10 / 0  # This will cause an error because dividing by 0 is not allowed.
except:
    print("An error occurred!")
```

### Output:
```
An error occurred!
```

---

## 2. The Except Block

The `except` block handles specific errors. You can catch a specific error type (e.g., division by zero) or handle all errors.

```python
try:
    result = 10 / 0  # Trying to divide by 0.
except ZeroDivisionError:
    print("Cannot divide by zero!")  # This will catch the specific error of dividing by 0.
```

### Output:
```
Cannot divide by zero!
```

---

## 3. The Else Block

The `else` block runs only if there are no errors in the `try` block. It's like saying, "If everything works fine, do this."

```python
try:
    result = 10 / 2  # No error here, so the else block will run.
except ZeroDivisionError:
    print("Cannot divide by zero!")
else:
    print(f"Division successful. Result: {result}")  # This runs only if there's no error.
```

### Output:
```
Division successful. Result: 5.0
```

---

## 4. The Finally Block

The `finally` block always runs, no matter if there was an error or not. It's used for cleanup, like closing files or releasing resources.

```python
try:
    result = 10 / 0  # This will raise an error.
except ZeroDivisionError:
    print("Cannot divide by zero!")
finally:
    print("This will always execute.")  # This runs no matter what.
```

### Output:
```
Cannot divide by zero!
This will always execute.
```

---

## Putting It All Together

Here’s an example that combines all four blocks.

```python
def divide_numbers(a, b):
    try:
        result = a / b  # Try dividing a by b.
    except ZeroDivisionError:
        print("Error: Cannot divide by zero!")  # If dividing by 0, print this message.
    except TypeError:
        print("Error: Invalid input type. Numbers required.")  # If the inputs aren't numbers, print this message.
    else:
        print(f"Division successful. Result: {result}")  # If no errors, print the result.
    finally:
        print("Operation complete.")  # This always runs, no matter what.

# Test cases
divide_numbers(10, 2)  # This will divide normally
divide_numbers(10, 0)  # This will cause a division by zero error
divide_numbers(10, "2")  # This will cause a type error because "2" is a string, not a number
```

### Output:
```
Division successful. Result: 5.0
Operation complete.
Error: Cannot divide by zero!
Operation complete.
Error: Invalid input type. Numbers required.
Operation complete.
```

---

## Example: Handling Errors in Real Life Code

Here’s a more complex example that handles data generation and calculations.

```python
import random

def generate_random_data(num_samples):
    try:
        if not isinstance(num_samples, int) or num_samples <= 0:
            raise ValueError("Number of samples must be a positive integer.")  # Raise error if num_samples is invalid.
        data = [(random.randint(1, 100), random.randint(1, 100)) for _ in range(num_samples)]  # Create random data.
        return data
    except ValueError as ve:
        print(f"Error: {ve}")  # Handle ValueError (invalid input for num_samples).
        return []
    except Exception as e:
        print(f"An unexpected error occurred: {e}")  # Handle any other unexpected errors.
        return []

def calculate_ratios(data):
    ratios = []
    try:
        for num1, num2 in data:
            if num2 == 0:
                raise ZeroDivisionError("Cannot divide by zero.")  # Handle division by zero error.
            ratio = num1 / num2  # Calculate the ratio.
            ratios.append(ratio)
        return ratios
    except ZeroDivisionError as zde:
        print(f"Error: {zde}")  # Handle division by zero error.
        return []
    except TypeError as te:
        print(f"Error: {te}")  # Handle type error if data is not correct.
        return []
    except Exception as e:
        print(f"An unexpected error occurred: {e}")  # Handle any other unexpected errors.
        return []

def process_data(num_samples):
    data = generate_random_data(num_samples)  # Generate random data.
    if not data:  # If there was an error generating data (empty list), return empty.
        return []
    return calculate_ratios(data)  # Calculate ratios based on the data.

# Example usage
results = process_data(10)  # Try with valid input
if results:
    print("Calculated ratios:", results)
else:
    print("Data processing failed due to an error.")
```

### Output:
```
Calculated ratios: [0.48, 2.3, 1.39, 2.93, 0.59, 0.8, 16.25, 0.72, 4.14, 0.92]
```

---

## Practice Problem

Write a Python program that asks the user for two numbers and divides them. Use exception handling to catch any errors that might occur, such as division by zero or invalid input.

```python
try:
    num1 = float(input("Enter the first number: "))  # Get first number from user
    num2 = float(input("Enter the second number: "))  # Get second number from user
    result = num1 / num2  # Try to divide
except ValueError:  # Handle invalid input errors
    print("Error: Invalid input. Please enter numbers.")
except ZeroDivisionError:  # Handle division by zero
    print("Error: Cannot divide by zero.")
else:
    print(f"The result is: {result}")  # Print the result if no errors occurred
finally:
    print("Thank you for using the program!")  # This runs no matter what
```

### Output for division by zero:
```
Enter the first number: 0
Enter the second number: 0
Error: Cannot divide by zero.
Thank you for using the program!
```

---

## Throwing Exceptions in Functions

In Python, you can raise exceptions manually using the `raise` keyword. This stops the function and triggers the error.

```python
def divide(a, b):
    if b == 0:
        raise ValueError("Division by zero is not allowed!")  # Manually raise an error
    return a / b

try:
    result = divide(5, 0)  # This will raise an exception
except ValueError as e:
    print(f"Error: {e}")  # Catch and handle the error
```

### Output:
```
Error: Division by zero is not allowed!
```

---

## Custom Exceptions

You can create your own exception classes to handle special situations.

```python
class NegativeNumberError(Exception):
    """Custom exception for negative numbers"""
    pass

def check_positive(n):
    if n < 0:
        raise NegativeNumberError("Negative numbers are not allowed!")
    return f"{n} is positive"

try:
    print(check_positive(-5))  # This will raise a custom error
except NegativeNumberError as e:
    print(f"Custom Exception Caught: {e}")
```

### Output:
```
Custom Exception Caught: Negative numbers are not allowed!
```

---

## Summary

- **try block**: Code that might cause an error.
- **except block**: Handles the error if it occurs.
- **else block**: Runs if no errors occurred in the `try` block.
- **finally block**: Always runs, no matter what.
- **raise**: Used to manually throw an error from a function.
- **Custom Exceptions**: You can create your own error types to handle special cases in your program.


