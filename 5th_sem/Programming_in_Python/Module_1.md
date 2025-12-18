
## **Module 1: Introduction to Python Programming**

### 1. Introduction to Python Programming Language

* Programming Language
* History and Origin of Python
* Features of Python
* Limitations of Python
* Major Applications of Python
* Getting and Installing Python
* Setting up Path and Environment Variables
* Running Python Programs
* First Python Program
* Python Interactive Help Feature
* Differences between Python and Other Programming Languages

### 2. Python Data Types and Input/Output

* Keywords
* Identifiers
* Python Statements
* Indentation Rules
* Documentation and Comments
* Variables
* Multiple Assignment
* Understanding Data Types
* Data Type Conversion
* Python Input Functions
* Python Output Functions
* Import Command

### 3. Operators and Expressions

* Operators in Python

  * Arithmetic Operators
  * Relational Operators
  * Logical Operators
  * Assignment Operators
  * Bitwise Operators
  * Membership Operators
  * Identity Operators
* Expressions
* Operator Precedence
* Operator Associativity
* Non-Associative Operators

---
---

# **1. Introduction to Python Programming Language**

---

## **1.1 Programming Language**

### **What is a Programming Language?**

A **programming language** is a formal language used to communicate instructions to a computer. These instructions tell the computer **what to do**, **how to do**, and **when to do**.

### **Why Programming Languages Are Needed**

* Computers understand only **binary (0 and 1)**
* Programming languages act as a **bridge between humans and machines**
* They help write instructions in a **human-readable form**

### **Types of Programming Languages**

1. **Low-Level Languages**

   * Machine Language
   * Assembly Language
2. **High-Level Languages**

   * C, C++, Java, Python, JavaScript

Python is a **high-level programming language**, which makes it easy to read, write, and understand.

---

## **1.2 History and Origin of Python**

### **Creator of Python**

* Python was created by **Guido van Rossum**
* Development started in **December 1989**
* First released in **1991**

### **Why the Name “Python”?**

* Named after the British comedy show **“Monty Python’s Flying Circus”**
* It has **nothing to do with the snake**

### **Development Goals**

Guido van Rossum wanted Python to be:

* Simple and easy to learn
* Powerful yet readable
* Suitable for beginners and professionals

### **Major Python Versions**

* Python 1.x (1994)
* Python 2.x (2000)

  * Not supported after 2020
* Python 3.x (2008 – present)

  * Improved performance and clarity

Today, **Python 3** is the standard version used.

---

## **1.3 Features of Python**

### **1. Simple and Easy to Learn**

* Uses English-like syntax
* Less code compared to other languages

Example:

```python
print("Hello, World!")
```

### **2. Interpreted Language**

* Code is executed **line by line**
* No need for compilation

### **3. High-Level Language**

* No need to manage memory manually
* Easy interaction with system resources

### **4. Open Source**

* Free to use and distribute
* Large community support

### **5. Object-Oriented**

* Supports classes and objects
* Encourages code reuse

### **6. Portable**

* Runs on Windows, Linux, macOS without changes

### **7. Extensive Standard Library**

* Built-in modules for:

  * Math
  * File handling
  * Networking
  * Date and time

### **8. Dynamically Typed**

* No need to declare variable types

Example:

```python
x = 10
x = "Python"
```

---

## **1.4 Limitations of Python**

### **1. Slower Execution Speed**

* Interpreted language
* Slower than C or C++

### **2. Memory Consumption**

* Uses more memory than low-level languages

### **3. Not Ideal for Mobile Development**

* Limited support for mobile apps

### **4. Runtime Errors**

* Errors are found during execution, not compilation

### **5. Weak in Hardware-Level Programming**

* Not suitable for device drivers or kernel development

---

## **1.5 Major Applications of Python**

### **1. Web Development**

* Frameworks:

  * Django
  * Flask
  * FastAPI

### **2. Data Science and Analytics**

* Libraries:

  * NumPy
  * Pandas
  * Matplotlib
  * Seaborn

### **3. Machine Learning and AI**

* TensorFlow
* PyTorch
* Scikit-learn

### **4. Automation and Scripting**

* Task automation
* File handling
* Web scraping

### **5. Game Development**

* Pygame

### **6. Desktop Applications**

* Tkinter
* PyQt

### **7. Cybersecurity**

* Ethical hacking
* Penetration testing

---

## **1.6 Getting and Installing Python**

### **Steps to Install Python**

1. Visit official website: **python.org**
2. Download Python 3.x version
3. Run installer
4. Select **“Add Python to PATH”**
5. Complete installation

### **Verify Installation**

```bash
python --version
```

or

```bash
python3 --version
```

---

## **1.7 Setting Up Path and Environment Variables**

### **What is PATH?**

* PATH tells the OS where Python is installed
* Allows running Python from any directory

### **Why PATH is Important**

Without PATH:

```bash
'python' is not recognized as an internal or external command
```

### **Adding Python to PATH**

* Done automatically if checkbox is selected during installation
* Otherwise added manually through environment variables

---

## **1.8 Running Python Programs**

### **Ways to Run Python**

1. Interactive Mode
2. Script Mode

### **Interactive Mode**

```bash
python
>>> print("Hello")
```

### **Script Mode**

* Save file as `program.py`

```bash
python program.py
```

---

## **1.9 First Python Program**

### **Hello World Program**

```python
print("Hello, World!")
```

### **Explanation**

* `print()` is a built-in function
* Displays output on the screen

---

## **1.10 Python Interactive Help Feature**

### **Using help()**

```python
help(print)
```

### **Using dir()**

```python
dir(str)
```

### **Using documentation**

```python
print.__doc__
```

These tools help understand:

* Functions
* Methods
* Classes

---

## **1.11 Differences Between Python and Other Languages**

| Feature           | Python      | C / C++  | Java           |
| ----------------- | ----------- | -------- | -------------- |
| Syntax            | Simple      | Complex  | Moderate       |
| Compilation       | Interpreted | Compiled | Compiled + JVM |
| Memory Management | Automatic   | Manual   | Automatic      |
| Code Length       | Short       | Long     | Moderate       |
| Learning Curve    | Easy        | Hard     | Moderate       |

---
---

# **2. Python Data Types and Input / Output**

---

## **2.1 Keywords**

### **What are Keywords?**

Keywords are **reserved words** in Python that have **predefined meanings**.
They **cannot be used as variable names, function names, or identifiers**.

### **Examples of Keywords**

`if, else, elif, for, while, break, continue, return, def, class, import, try, except, True, False, None`

### **Check Python Keywords**

```python
import keyword
print(keyword.kwlist)
```

---

## **2.2 Identifiers**

### **What are Identifiers?**

Identifiers are **names given to variables, functions, classes, or objects**.

### **Rules for Identifiers**

* Must start with a letter (a–z, A–Z) or underscore (_)
* Cannot start with a digit
* Cannot use keywords
* Case-sensitive

### **Valid Identifiers**

```python
name
total_sum
_count
StudentName
```

### **Invalid Identifiers**

```python
2value     # starts with digit
class      # keyword
total-sum  # special character
```

---

## **2.3 Python Statements**

### **What is a Statement?**

A statement is an **instruction executed by the Python interpreter**.

### **Types of Statements**

1. **Simple Statements**

```python
x = 10
print(x)
```

2. **Compound Statements**

```python
if x > 5:
    print("Greater")
```

---

## **2.4 Indentation Rules**

### **What is Indentation?**

Indentation refers to **spaces at the beginning of a line**.

### **Why Indentation is Important**

* Python uses indentation to define **blocks of code**
* Replaces braces `{}` used in other languages

### **Correct Indentation**

```python
if x > 0:
    print("Positive")
```

### **Incorrect Indentation**

```python
if x > 0:
print("Positive")  # Error
```

---

## **2.5 Documentation and Comments**

### **Comments**

Used to explain code.

#### **Single-line Comment**

```python
# This is a comment
```

#### **Multi-line Comment**

```python
"""
This is a
multi-line comment
"""
```

### **Documentation Strings (Docstrings)**

Used to document functions, classes, or modules.

```python
def add(a, b):
    """This function returns sum of two numbers"""
    return a + b
```

Access docstring:

```python
print(add.__doc__)
```

---

## **2.6 Variables**

### **What is a Variable?**

A variable is a **name that refers to a value stored in memory**.

### **Variable Assignment**

```python
x = 10
name = "Python"
```

### **Dynamic Typing**

Python decides data type at runtime.

```python
x = 10
x = "Hello"
```

---

## **2.7 Multiple Assignment**

### **Assigning Multiple Values**

```python
a, b, c = 10, 20, 30
```

### **Assign Same Value**

```python
x = y = z = 100
```

### **Swapping Variables**

```python
a, b = b, a
```

---

## **2.8 Understanding Data Types**

### **What is a Data Type?**

Data type defines **type of data** stored in a variable.

### **Built-in Data Types**

* Numeric: int, float, complex
* Sequence: list, tuple, string
* Set: set
* Mapping: dict
* Boolean: bool
* None: NoneType

### **Check Data Type**

```python
x = 10
print(type(x))
```

---

## **2.9 Data Type Conversion**

### **Implicit Type Conversion**

Python converts automatically.

```python
x = 10
y = 2.5
z = x + y
```

### **Explicit Type Conversion**

User converts manually.

```python
x = int(5.6)
y = float(10)
z = str(100)
```

### **Type Casting Functions**

* int()
* float()
* str()
* list()
* tuple()
* set()

---

## **2.10 Python Input Functions**

### **input() Function**

Used to take input from user.

```python
name = input("Enter your name: ")
print(name)
```

### **Important Note**

`input()` always returns **string**.

Convert input:

```python
age = int(input("Enter age: "))
```

---

## **2.11 Python Output Functions**

### **print() Function**

Displays output.

```python
print("Hello Python")
```

### **Multiple Values**

```python
print("Age:", age)
```

### **Separator and End**

```python
print("A", "B", "C", sep="-")
print("Hello", end=" ")
print("World")
```

---

## **2.12 Import Command**

### **What is Import?**

Used to access **functions and variables from modules**.

### **Import Whole Module**

```python
import math
print(math.sqrt(16))
```

### **Import Specific Function**

```python
from math import sqrt
print(sqrt(25))
```

### **Import with Alias**

```python
import math as m
print(m.pi)
```

---
---

# **3. Operators and Expressions**

---

## **3.1 Operators in Python**

### **What is an Operator?**

An **operator** is a symbol that performs an operation on one or more operands (values or variables).

Example:

```python
a = 10
b = 5
c = a + b
```

Here, `+` is the operator and `a`, `b` are operands.

---

## **3.2 Types of Operators in Python**

---

## **3.2.1 Arithmetic Operators**

Used to perform mathematical operations.

| Operator | Meaning        | Example  | Output |
| -------- | -------------- | -------- | ------ |
| `+`      | Addition       | `5 + 3`  | 8      |
| `-`      | Subtraction    | `5 - 3`  | 2      |
| `*`      | Multiplication | `5 * 3`  | 15     |
| `/`      | Division       | `5 / 2`  | 2.5    |
| `//`     | Floor Division | `5 // 2` | 2      |
| `%`      | Modulus        | `5 % 2`  | 1      |
| `**`     | Exponent       | `2 ** 3` | 8      |

Example:

```python
a = 10
b = 3
print(a + b)
print(a // b)
print(a ** b)
```

---

## **3.2.2 Relational (Comparison) Operators**

Used to compare values.
Result is **True or False**.

| Operator | Meaning               |
| -------- | --------------------- |
| `==`     | Equal to              |
| `!=`     | Not equal             |
| `>`      | Greater than          |
| `<`      | Less than             |
| `>=`     | Greater than or equal |
| `<=`     | Less than or equal    |

Example:

```python
a = 10
b = 20
print(a > b)
print(a == b)
```

---

## **3.2.3 Logical Operators**

Used to combine conditional statements.

| Operator | Meaning                      |
| -------- | ---------------------------- |
| `and`    | True if both are true        |
| `or`     | True if at least one is true |
| `not`    | Reverses the result          |

Example:

```python
x = 5
print(x > 3 and x < 10)
print(not(x > 10))
```

---

## **3.2.4 Assignment Operators**

Used to assign values.

| Operator | Example  | Equivalent  |
| -------- | -------- | ----------- |
| `=`      | `x = 5`  | `x = 5`     |
| `+=`     | `x += 3` | `x = x + 3` |
| `-=`     | `x -= 2` | `x = x - 2` |
| `*=`     | `x *= 4` | `x = x * 4` |
| `/=`     | `x /= 2` | `x = x / 2` |
| `%=`     | `x %= 2` | `x = x % 2` |

Example:

```python
x = 10
x += 5
print(x)
```

---

## **3.2.5 Bitwise Operators**

Operate on binary numbers.

| Operator | Meaning     |    |
| -------- | ----------- | -- |
| `&`      | AND         |    |
| `        | `           | OR |
| `^`      | XOR         |    |
| `~`      | NOT         |    |
| `<<`     | Left shift  |    |
| `>>`     | Right shift |    |

Example:

```python
a = 5  # 101
b = 3  # 011
print(a & b)
print(a | b)
```

---

## **3.2.6 Membership Operators**

Used to test membership in a sequence.

| Operator | Meaning        |
| -------- | -------------- |
| `in`     | Exists in      |
| `not in` | Does not exist |

Example:

```python
list1 = [1, 2, 3]
print(2 in list1)
print(5 not in list1)
```

---

## **3.2.7 Identity Operators**

Used to compare memory location.

| Operator | Meaning          |
| -------- | ---------------- |
| `is`     | Same object      |
| `is not` | Different object |

Example:

```python
a = 10
b = 10
print(a is b)
```

---

## **3.3 Expressions**

### **What is an Expression?**

An expression is a **combination of operands and operators** that produces a value.

Example:

```python
x = 5 + 3 * 2
```

Types:

* Arithmetic expressions
* Relational expressions
* Logical expressions

---

## **3.4 Operator Precedence**

### **What is Operator Precedence?**

Defines the **order in which operators are evaluated**.

### **Precedence Order (High → Low)**

1. `()`
2. `**`
3. `+ -` (unary)
4. `* / // %`
5. `+ -`
6. Relational (`< <= > >=`)
7. Equality (`== !=`)
8. Logical `and`
9. Logical `or`
10. Assignment (`=`)

Example:

```python
result = 10 + 2 * 3
print(result)  # 16
```

---

## **3.5 Operator Associativity**

### **What is Associativity?**

Determines **direction of evaluation** when operators have same precedence.

### **Types**

* Left to Right
* Right to Left

Example:

```python
x = 10 - 5 - 2
# evaluated as (10 - 5) - 2
```

Exponent operator:

```python
print(2 ** 3 ** 2)  # Right to Left
```

---

## **3.6 Non-Associative Operators**

Some operators **cannot be chained together**.

Example:

```python
# Invalid
# 10 < 20 < 30  (allowed in Python but logically separate)

# Correct approach
10 < 20 and 20 < 30
```

Examples of non-associative comparisons:

* `<`
* `>`
* `<=`
* `>=`

---