

## **Module 2: Control Structures and Native Data Types**

### 1. Control Structures

* Decision Making Statements

  * if
  * if-else
  * elif
  * nested if
* Python Loops

  * while loop
  * for loop
* Loop Control Statements

  * break
  * continue
  * pass
* Assert Statement

### 2. Python Native Data Types

* Numbers
* Lists
* Tuples
* Sets
* Dictionaries

  * Dictionary Functions
  * Dictionary Methods
* Strings

  * String Operations
  * String Methods

---
---

# **1. Control Structures**

---

## **1.1 Control Structures in Python**

### **What are Control Structures?**

Control structures determine the **flow of execution** of a program.
They allow the program to:

* Make decisions
* Repeat actions
* Skip or stop execution

### **Types of Control Structures**

1. Decision Making Statements
2. Looping Statements
3. Control Statements

---

## **1.2 Decision Making Statements**

Decision making statements execute code **based on conditions**.

---

## **1.2.1 if Statement**

### **Definition**

Executes a block of code **only if the condition is true**.

### **Syntax**

```python
if condition:
    statement(s)
```

### **Example**

```python
x = 10
if x > 5:
    print("x is greater than 5")
```

### **Explanation**

* Condition is checked
* If true, block executes
* If false, block is skipped

---

## **1.2.2 if–else Statement**

### **Definition**

Provides an **alternative block** if condition is false.

### **Syntax**

```python
if condition:
    statement(s)
else:
    statement(s)
```

### **Example**

```python
age = 18
if age >= 18:
    print("Eligible to vote")
else:
    print("Not eligible to vote")
```

---

## **1.2.3 elif Statement**

### **Definition**

Used to check **multiple conditions**.

### **Syntax**

```python
if condition1:
    statement(s)
elif condition2:
    statement(s)
else:
    statement(s)
```

### **Example**

```python
marks = 75

if marks >= 90:
    print("Grade A")
elif marks >= 60:
    print("Grade B")
else:
    print("Grade C")
```

---

## **1.2.4 Nested if Statement**

### **Definition**

An `if` inside another `if`.

### **Syntax**

```python
if condition1:
    if condition2:
        statement(s)
```

### **Example**

```python
x = 10

if x > 0:
    if x % 2 == 0:
        print("Positive even number")
```

---

## **1.3 Python Loops**

Loops are used to **execute a block repeatedly**.

---

## **1.3.1 while Loop**

### **Definition**

Executes as long as condition is true.

### **Syntax**

```python
while condition:
    statement(s)
```

### **Example**

```python
i = 1
while i <= 5:
    print(i)
    i += 1
```

### **Important Points**

* Condition checked before execution
* Can result in infinite loop if not handled properly

---

## **1.3.2 for Loop**

### **Definition**

Used to iterate over a **sequence**.

### **Syntax**

```python
for variable in sequence:
    statement(s)
```

### **Example**

```python
for i in range(1, 6):
    print(i)
```

### **Using for with List**

```python
fruits = ["apple", "banana", "mango"]
for fruit in fruits:
    print(fruit)
```

---

## **1.4 Loop Control Statements**

Used to **alter normal loop execution**.

---

## **1.4.1 break Statement**

### **Definition**

Terminates the loop immediately.

### **Example**

```python
for i in range(1, 10):
    if i == 5:
        break
    print(i)
```

---

## **1.4.2 continue Statement**

### **Definition**

Skips the current iteration and continues with next.

### **Example**

```python
for i in range(1, 6):
    if i == 3:
        continue
    print(i)
```

---

## **1.4.3 pass Statement**

### **Definition**

Does nothing. Used as a placeholder.

### **Example**

```python
for i in range(5):
    pass
```

Used when:

* Statement required syntactically
* Logic to be added later

---

## **1.5 Assert Statement**

### **Definition**

Used for **debugging**.
Checks a condition and raises error if false.

### **Syntax**

```python
assert condition, message
```

### **Example**

```python
x = 10
assert x > 0, "x must be positive"
```

### **If condition fails**

```python
AssertionError: x must be positive
```

---
---

# **2. Python Native Data Types**

---

## **2.1 Python Native Data Types – Overview**

### **What are Native Data Types?**

Native data types are **built-in data structures** provided by Python to store and manipulate data efficiently.

### **Main Native Data Types**

* Numbers
* Lists
* Tuples
* Sets
* Dictionaries
* Strings

---

## **2.2 Numbers**

### **Types of Numeric Data**

1. **int** – Integer numbers
2. **float** – Decimal numbers
3. **complex** – Real and imaginary numbers

### **Examples**

```python
a = 10        # int
b = 3.14      # float
c = 2 + 3j    # complex
```

### **Numeric Operations**

```python
print(a + b)
print(a * b)
print(abs(-10))
print(pow(2, 3))
```

---

## **2.3 Lists**

### **What is a List?**

A list is an **ordered, mutable collection** of elements.

### **Characteristics**

* Allows duplicate values
* Can store different data types
* Index starts from 0

### **Creating a List**

```python
list1 = [1, 2, 3, "Python", 4.5]
```

### **Accessing Elements**

```python
print(list1[0])
print(list1[-1])
```

### **List Operations**

```python
print(len(list1))
print(list1 + [10, 20])
print(list1 * 2)
```

### **List Methods**

```python
list1.append(100)
list1.insert(2, "AI")
list1.remove(2)
list1.pop()
list1.sort()
list1.reverse()
```

---

## **2.4 Tuples**

### **What is a Tuple?**

A tuple is an **ordered, immutable collection**.

### **Characteristics**

* Cannot be modified
* Faster than lists
* Uses parentheses

### **Creating a Tuple**

```python
tup = (1, 2, 3, "Python")
```

### **Accessing Tuple Elements**

```python
print(tup[1])
```

### **Tuple Methods**

```python
tup.count(2)
tup.index("Python")
```

### **Why Tuples are Used**

* Data protection
* Fixed data
* Performance optimization

---

## **2.5 Sets**

### **What is a Set?**

A set is an **unordered collection of unique elements**.

### **Characteristics**

* No duplicate values
* Unordered
* Mutable

### **Creating a Set**

```python
set1 = {1, 2, 3, 4}
```

### **Set Operations**

```python
set1.add(5)
set1.remove(2)
set1.discard(10)
```

### **Set Mathematical Operations**

```python
a = {1, 2, 3}
b = {3, 4, 5}

print(a | b)   # Union
print(a & b)   # Intersection
print(a - b)   # Difference
```

---

## **2.6 Dictionaries**

### **What is a Dictionary?**

A dictionary stores data in **key–value pairs**.

### **Characteristics**

* Unordered (in older versions)
* Keys must be unique
* Values can be any type

### **Creating Dictionary**

```python
student = {
    "name": "Shreya",
    "age": 21,
    "course": "AI"
}
```

### **Accessing Values**

```python
print(student["name"])
print(student.get("age"))
```

---

### **2.6.1 Dictionary Functions**

```python
len(student)
type(student)
```

---

### **2.6.2 Dictionary Methods**

| Method     | Purpose                 |
| ---------- | ----------------------- |
| `keys()`   | Returns keys            |
| `values()` | Returns values          |
| `items()`  | Returns key-value pairs |
| `update()` | Updates dictionary      |
| `pop()`    | Removes key             |
| `clear()`  | Clears dictionary       |

Example:

```python
student.update({"age": 22})
student.pop("course")
```

---

## **2.7 Strings**

### **What is a String?**

A string is a **sequence of characters**.

### **Creating Strings**

```python
s1 = "Python"
s2 = 'AI'
s3 = """Data Science"""
```

### **String Indexing**

```python
print(s1[0])
print(s1[-1])
```

---

### **2.7.1 String Operations**

| Operation     | Example             |
| ------------- | ------------------- |
| Concatenation | `"Hello" + "World"` |
| Repetition    | `"Hi" * 3`          |
| Membership    | `'P' in "Python"`   |
| Slicing       | `s1[1:4]`           |

---

### **2.7.2 String Methods**

| Method      | Purpose           |
| ----------- | ----------------- |
| `upper()`   | Uppercase         |
| `lower()`   | Lowercase         |
| `strip()`   | Remove spaces     |
| `replace()` | Replace substring |
| `split()`   | Split string      |
| `find()`    | Find substring    |
| `count()`   | Count occurrence  |

Example:

```python
text = "  Python Programming  "
print(text.strip())
print(text.upper())
print(text.replace("Python", "AI"))
```

---