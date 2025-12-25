
## **Module 3: Functions and Modules**

### 1. Python Functions

* Concept of Functions
* Advantages of Functions
* Built-in Functions
* User-Defined Functions
* Anonymous (Lambda) Functions
* Pass by Value vs Pass by Reference
* Recursion
* Scope of Variables
* Lifetime of Variables

### 2. Python Modules

* Definition of Modules
* Need for Modules
* Creating a Module
* Importing a Module
* Module Search Path
* Reloading Modules
* Standard Python Modules
* Python Packages

---
---

# **MODULE 3: FUNCTIONS AND MODULES**

## **1. Python Functions**

---

## **1.1 Concept of Functions**

### **What is a Function?**

A **function** is a block of organized, reusable code that performs a **specific task**.

Instead of writing the same code again and again, we define it once and reuse it.

### **Why Functions are Needed**

* Reduce code repetition
* Improve readability
* Easy debugging and maintenance
* Modular programming

---

## **1.2 Advantages of Functions**

* **Code Reusability**: Write once, use many times
* **Modularity**: Break large programs into small parts
* **Maintainability**: Easy to modify and update
* **Readability**: Code becomes clean and structured
* **Testing**: Functions can be tested independently

---

## **1.3 Built-in Functions**

### **What are Built-in Functions?**

Functions that are **already provided by Python**.

### **Common Built-in Functions**

| Function  | Purpose           |
| --------- | ----------------- |
| `print()` | Display output    |
| `input()` | Take input        |
| `len()`   | Length of object  |
| `type()`  | Check data type   |
| `range()` | Generate sequence |
| `sum()`   | Sum of elements   |
| `max()`   | Maximum value     |
| `min()`   | Minimum value     |

### **Examples**

```python
x = [1, 2, 3, 4]
print(len(x))
print(max(x))
print(type(x))
```

---

## **1.4 User-Defined Functions**

### **What is a User-Defined Function?**

Functions **created by the user** to perform specific tasks.

### **Syntax**

```python
def function_name(parameters):
    statement(s)
    return value
```

### **Example**

```python
def add(a, b):
    return a + b

result = add(10, 20)
print(result)
```

### **Function Without Return**

```python
def greet(name):
    print("Hello", name)

greet("Shreya")
```

---

## **1.5 Types of Arguments**

### **1. Positional Arguments**

```python
def sub(a, b):
    return a - b

sub(10, 5)
```

### **2. Keyword Arguments**

```python
sub(b=5, a=10)
```

### **3. Default Arguments**

```python
def greet(name="User"):
    print("Hello", name)

greet()
```

### **4. Variable Length Arguments**

```python
def total(*numbers):
    return sum(numbers)

print(total(1, 2, 3))
```

---

## **1.6 Anonymous (Lambda) Functions**

### **What is a Lambda Function?**

* Small, **one-line function**
* No function name
* Uses `lambda` keyword

### **Syntax**

```python
lambda arguments: expression
```

### **Example**

```python
square = lambda x: x * x
print(square(5))
```

### **Use Cases**

* Short operations
* Used with `map()`, `filter()`, `reduce()`

Example:

```python
nums = [1, 2, 3]
print(list(map(lambda x: x * 2, nums)))
```

---

## **1.7 Pass by Value vs Pass by Reference**

### **Pass by Value**

* Copy of value is passed
* Original variable not changed

### **Pass by Reference**

* Reference to object is passed
* Changes affect original object

### **Python Behavior**

Python uses **pass by object reference**.

### **Example with Immutable Object**

```python
def change(x):
    x = 20

a = 10
change(a)
print(a)   # 10
```

### **Example with Mutable Object**

```python
def modify(lst):
    lst.append(100)

l = [1, 2, 3]
modify(l)
print(l)   # [1, 2, 3, 100]
```

---

## **1.8 Recursion**

### **What is Recursion?**

A function **calling itself** to solve a problem.

### **Two Important Parts**

* Base condition
* Recursive call

### **Example: Factorial**

```python
def fact(n):
    if n == 0:
        return 1
    return n * fact(n-1)

print(fact(5))
```

### **Advantages**

* Simple and clean logic
* Useful in tree and graph problems

### **Disadvantages**

* More memory usage
* Risk of infinite recursion

---

## **1.9 Scope of Variables**

### **What is Scope?**

Scope defines **where a variable is accessible**.

### **Types of Scope**

1. Local Scope
2. Global Scope

### **Local Variable**

```python
def func():
    x = 10
    print(x)
```

### **Global Variable**

```python
x = 20
def show():
    print(x)
```

### **Using global Keyword**

```python
x = 5
def change():
    global x
    x = 10
```

---

## **1.10 Lifetime of Variables**

### **What is Lifetime?**

The time during which a variable **exists in memory**.

### **Lifetime Types**

* Local variables exist during function execution
* Global variables exist till program ends

Example:

```python
def test():
    y = 10
    print(y)
```

`y` is destroyed after function execution.

---
---

# **2. Python Modules**

---

## **2.1 Definition of Modules**

### **What is a Module?**

A **module** is a file containing Python code such as:

* Functions
* Variables
* Classes

Saved with a **.py** extension.

Example:

```text
math.py
```

Modules help in **organizing large programs**.

---

## **2.2 Need for Modules**

### **Why Modules are Required**

* Code reusability
* Better organization
* Easy maintenance
* Avoids repetition
* Enables modular programming

Without modules, large programs become:

* Difficult to read
* Hard to debug
* Error-prone

---

## **2.3 Creating a Module**

### **Steps to Create a Module**

1. Create a `.py` file
2. Write functions or variables
3. Save the file

### **Example: Create a Module**

**File name:** `mymath.py`

```python
def add(a, b):
    return a + b

def sub(a, b):
    return a - b
```

---

## **2.4 Importing a Module**

Python provides multiple ways to import modules.

---

### **2.4.1 Import Entire Module**

```python
import mymath

print(mymath.add(10, 5))
```

Access functions using:

```text
module_name.function_name
```

---

### **2.4.2 Import Specific Functions**

```python
from mymath import add, sub

print(add(5, 3))
```

---

### **2.4.3 Import All Functions**

```python
from mymath import *
```

Not recommended for large projects due to name conflicts.

---

### **2.4.4 Import with Alias**

```python
import mymath as mm

print(mm.add(10, 20))
```

---

## **2.5 Module Search Path**

### **What is Module Search Path?**

When a module is imported, Python searches in:

1. Current directory
2. Built-in modules directory
3. Directories in `PYTHONPATH`

### **Check Search Path**

```python
import sys
print(sys.path)
```

---

## **2.6 Reloading Modules**

### **Why Reload a Module?**

* When module code is changed
* Python does not automatically reload imported modules

### **Using importlib**

```python
import importlib
import mymath

importlib.reload(mymath)
```

---

## **2.7 Standard Python Modules**

Python provides many **built-in modules**.

### **Common Standard Modules**

| Module     | Use                        |
| ---------- | -------------------------- |
| `math`     | Mathematical operations    |
| `sys`      | System-specific parameters |
| `os`       | Operating system functions |
| `random`   | Random number generation   |
| `datetime` | Date and time              |
| `time`     | Time-related functions     |

### **Example**

```python
import math
print(math.sqrt(16))
print(math.pi)
```

---

## **2.8 Python Packages**

### **What is a Package?**

A **package** is a collection of related modules stored in a directory.

### **Purpose of Packages**

* Organize modules hierarchically
* Avoid naming conflicts
* Large project management

---

### **2.8.1 Creating a Package**

Steps:

1. Create a folder
2. Add `__init__.py`
3. Add module files

Example:

```text
mypackage/
│
├── __init__.py
├── module1.py
├── module2.py
```

---

### **2.8.2 Importing from a Package**

```python
from mypackage import module1
```

or

```python
from mypackage.module1 import function_name
```

---

### **2.8.3 Standard Python Packages**

Examples:

* `numpy`
* `pandas`
* `matplotlib`
* `scipy`

These are installed using:

```bash
pip install package_name
```

---

## **Difference Between Module and Package**

| Feature    | Module         | Package               |
| ---------- | -------------- | --------------------- |
| Definition | Single file    | Collection of modules |
| Extension  | `.py`          | Directory             |
| Usage      | Small programs | Large projects        |

---