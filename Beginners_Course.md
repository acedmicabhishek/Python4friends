# Python for Beginners: A Complete Course


## 1. Getting Started

### Installation
1.  **Download Python**: Visit [python.org](https://www.python.org/) and download the latest version.
2.  **IDE**: We recommend **VS Code**. Install the "Python" extension by Microsoft.

### Your First Script
Create a file named `hello.py` and type:
```python
print("Hello, Python World!")
```
Run it by typing `python hello.py` in your terminal.

---

## 2. Fundamentals

### Variables & Data Types
Variables are containers for storing data values.
```python
name = "Alice"          # String (str)
age = 25                # Integer (int)
height = 5.6            # Float (float)
is_student = True       # Boolean (bool)
```

### Basic Operators
- **Arithmetic**: `+`, `-`, `*`, `/`, `//` (floor division), `%` (modulus), `**` (exponent)
- **Comparison**: `==`, `!=`, `>`, `<`, `>=`, `<=`
- **Logical**: `and`, `or`, `not`

### Input & Output
```python
user_name = input("Enter your name: ")
print(f"Hello, {user_name}! Nice to meet you.")
```

---

## 3. Control Flow

### Conditional Statements
Make decisions in your code.
```python
age = int(input("Enter your age: "))
if age >= 18:
    print("You are an adult.")
elif age >= 13:
    print("You are a teenager.")
else:
    print("You are a child.")
```

### Loops
#### For Loops (Iterating)
```python
fruits = ["apple", "banana", "cherry"]
for fruit in fruits:
    print(f"I love {fruit}")

for i in range(5):
    print(f"Iteration {i}")
```

#### While Loops (Conditional)
```python
count = 0
while count < 5:
    print(f"Count is {count}")
    count += 1
```

---

## 4. Data Structures

### Lists (Ordered & Mutable)
```python
colors = ["red", "green", "blue"]
colors.append("yellow")
print(colors[0])      # red
print(colors[1:3])    # ['green', 'blue']
```

### Dictionaries (Key-Value Pairs)
```python
student = {
    "name": "Bob",
    "grade": "A",
    "subjects": ["Math", "Science"]
}
print(student["name"])
```

### Tuples (Immutable) & Sets (Unique)
```python
coords = (10.0, 20.0)    # Tuple
unique_ids = {1, 2, 3, 3} # Set -> {1, 2, 3}
```

---

## 5. Functions & Modules

### Defining Functions
```python
def greet(name, greeting="Hello"):
    return f"{greeting}, {name}!"

msg = greet("Charlie")
print(msg)
```

### Modules
Use libraries to extend functionality.
```python
import math
import random

print(math.sqrt(16))
print(random.randint(1, 10))
```

---

## 6. Final Project: Simple CLI Calculator

Let's build a basic calculator:
```python
def add(x, y): return x + y
def subtract(x, y): return x - y

print("Select operation: 1.Add, 2.Subtract")
choice = input("Enter choice (1/2): ")
num1 = float(input("Enter first number: "))
num2 = float(input("Enter second number: "))

if choice == '1':
    print(f"Result: {add(num1, num2)}")
elif choice == '2':
    print(f"Result: {subtract(num1, num2)}")
else:
    print("Invalid Input")
```

---
[Return to Main README](README.md)
