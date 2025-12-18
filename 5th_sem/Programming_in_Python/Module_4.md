
## **Module 4: Exception Handling, Files, and OOPS**

### 1. Exception Handling

* Concept of Exceptions
* Built-in Exceptions
* Exception Handling Mechanism
* User-Defined Exceptions

### 2. File Management in Python

* File Operations

  * Opening Files
  * File Modes
  * File Attributes
  * File Encoding
  * Closing Files
* Reading from Files

  * read()
* Writing to Files

  * write()
* File Pointer Methods

  * tell()
  * seek()
* Renaming Files
* Deleting Files
* Directory Handling in Python

### 3. Classes and Objects (OOPS in Python)

* Object Oriented Programming Concepts
* Designing Classes
* Creating Objects
* Accessing Class Attributes
* Modifying Class Attributes
* Built-in Class Attributes
* Garbage Collection
* Destroying Objects

---
---

# **1. Exception Handling**

---

## **1.1 Concept of Exceptions**

### **What is an Exception?**

An **exception** is an **error that occurs during the execution of a program**, which disrupts the normal flow of instructions.

Example:

```python
x = 10 / 0
```

This causes a runtime error.

---

### **Types of Errors in Python**

1. **Syntax Errors**

   * Occur due to incorrect syntax
   * Detected before execution

Example:

```python
if x > 5
    print(x)
```

2. **Runtime Errors (Exceptions)**

   * Occur during program execution
   * Can be handled using exception handling

---

### **Why Exception Handling is Needed**

* Prevent program crash
* Handle unexpected situations gracefully
* Improve program reliability
* Display meaningful error messages

---

## **1.2 Built-in Exceptions**

Python provides many predefined exceptions.

### **Common Built-in Exceptions**

| Exception           | Cause                       |
| ------------------- | --------------------------- |
| `ZeroDivisionError` | Division by zero            |
| `ValueError`        | Invalid value               |
| `TypeError`         | Wrong data type             |
| `IndexError`        | Invalid index               |
| `KeyError`          | Key not found in dictionary |
| `FileNotFoundError` | File does not exist         |
| `NameError`         | Variable not defined        |

### **Example**

```python
x = int("abc")   # ValueError
```

---

## **1.3 Exception Handling Mechanism**

Python handles exceptions using **try–except blocks**.

---

### **1.3.1 try–except Block**

### **Syntax**

```python
try:
    statement(s)
except ExceptionType:
    statement(s)
```

### **Example**

```python
try:
    x = 10 / 0
except ZeroDivisionError:
    print("Cannot divide by zero")
```

---

### **1.3.2 Multiple except Blocks**

```python
try:
    a = int(input("Enter number: "))
    print(10 / a)
except ValueError:
    print("Invalid input")
except ZeroDivisionError:
    print("Division by zero not allowed")
```

---

### **1.3.3 try–except–else**

The `else` block executes **only if no exception occurs**.

```python
try:
    x = 10 / 2
except ZeroDivisionError:
    print("Error")
else:
    print("Success:", x)
```

---

### **1.3.4 try–except–finally**

The `finally` block **always executes**, whether exception occurs or not.

```python
try:
    file = open("data.txt", "r")
except FileNotFoundError:
    print("File not found")
finally:
    print("Execution completed")
```

---

## **1.4 User-Defined Exceptions**

### **What is a User-Defined Exception?**

Custom exceptions created by programmers to handle specific error conditions.

---

### **Steps to Create User-Defined Exception**

1. Create a class
2. Inherit from `Exception`
3. Raise the exception

---

### **Example**

```python
class AgeError(Exception):
    pass

age = int(input("Enter age: "))
if age < 18:
    raise AgeError("Age must be 18 or above")
else:
    print("Eligible")
```

---

### **Using try with User-Defined Exception**

```python
try:
    age = int(input("Enter age: "))
    if age < 18:
        raise AgeError
except AgeError:
    print("Custom exception occurred")
```

---

## **Key Exam Points (Exception Handling)**

* Difference between syntax error and exception
* Purpose of try–except
* Use of `else` and `finally`
* Built-in vs user-defined exceptions

---
---

# **2. File Management in Python**

---

## **2.1 Introduction to File Handling**

### **What is File Handling?**

File handling allows Python programs to:

* Store data permanently
* Read data from files
* Write data into files
* Modify existing files

Files help in **persistent storage**, unlike variables which store data temporarily.

---

## **2.2 File Operations**

---

## **2.2.1 Opening Files**

### **open() Function**

Used to open a file.

### **Syntax**

```python
file_object = open("filename", "mode")
```

### **Example**

```python
f = open("data.txt", "r")
```

---

## **2.2.2 File Modes**

| Mode | Description             |
| ---- | ----------------------- |
| `r`  | Read (default)          |
| `w`  | Write (overwrites file) |
| `a`  | Append                  |
| `x`  | Create new file         |
| `b`  | Binary mode             |
| `t`  | Text mode               |
| `r+` | Read and write          |
| `w+` | Write and read          |

### **Example**

```python
f = open("data.txt", "w")
```

---

## **2.2.3 File Attributes**

File objects have attributes.

| Attribute | Description        |
| --------- | ------------------ |
| `name`    | File name          |
| `mode`    | File mode          |
| `closed`  | File closed or not |

### **Example**

```python
f = open("data.txt", "r")
print(f.name)
print(f.mode)
print(f.closed)
```

---

## **2.2.4 File Encoding**

### **What is Encoding?**

Encoding defines how characters are stored in files.

### **Common Encoding**

* UTF-8 (default and most common)

### **Example**

```python
f = open("data.txt", "r", encoding="utf-8")
```

---

## **2.2.5 Closing Files**

### **close() Method**

Closes the file and frees resources.

```python
f.close()
```

### **Using with Statement (Recommended)**

Automatically closes file.

```python
with open("data.txt", "r") as f:
    data = f.read()
```

---

## **2.3 Reading from Files**

---

## **2.3.1 read() Method**

### **Definition**

Reads entire file content as a string.

### **Syntax**

```python
file.read(size)
```

### **Example**

```python
with open("data.txt", "r") as f:
    content = f.read()
    print(content)
```

---

## **2.4 Writing to Files**

---

## **2.4.1 write() Method**

### **Definition**

Writes data to a file.

### **Syntax**

```python
file.write(string)
```

### **Example**

```python
with open("data.txt", "w") as f:
    f.write("Python File Handling")
```

### **Important Point**

* `write()` returns number of characters written
* Does not add newline automatically

---

## **2.5 File Pointer Methods**

---

## **2.5.1 tell() Method**

### **Purpose**

Returns current position of file pointer.

### **Example**

```python
with open("data.txt", "r") as f:
    print(f.tell())
```

---

## **2.5.2 seek() Method**

### **Purpose**

Moves file pointer to specified position.

### **Syntax**

```python
file.seek(offset, from_where)
```

* `from_where`:

  * 0: Beginning
  * 1: Current position
  * 2: End of file

### **Example**

```python
with open("data.txt", "r") as f:
    f.seek(5)
    print(f.read())
```

---

## **2.6 Renaming Files**

### **Using os Module**

```python
import os
os.rename("old.txt", "new.txt")
```

---

## **2.7 Deleting Files**

```python
import os
os.remove("data.txt")
```

---

## **2.8 Directory Handling in Python**

### **Common Directory Operations**

| Function       | Purpose                   |
| -------------- | ------------------------- |
| `os.mkdir()`   | Create directory          |
| `os.rmdir()`   | Remove directory          |
| `os.getcwd()`  | Current working directory |
| `os.chdir()`   | Change directory          |
| `os.listdir()` | List directory contents   |

### **Examples**

```python
import os

os.mkdir("MyFolder")
print(os.getcwd())
print(os.listdir())
```

---

## **Key Exam Points (File Handling)**

* Difference between `r`, `w`, and `a`
* Importance of `with` statement
* Use of `seek()` and `tell()`
* File vs directory operations

---
---

# **3. Classes and Objects (OOPS in Python)**

---

## **3.1 Object Oriented Programming (OOPS) Concepts**

### **What is OOPS?**

Object Oriented Programming is a programming approach where programs are built using **objects** that represent real-world entities.

### **Core OOPS Concepts**

* Class
* Object
* Encapsulation
* Inheritance
* Polymorphism
* Abstraction

Python supports all OOPS concepts.

---

## **3.2 Designing Classes**

### **What is a Class?**

A **class** is a blueprint or template used to create objects.

### **Syntax**

```python
class ClassName:
    statement(s)
```

### **Example**

```python
class Student:
    pass
```

---

## **3.3 Creating Objects**

### **What is an Object?**

An **object** is an instance of a class.

### **Syntax**

```python
object_name = ClassName()
```

### **Example**

```python
s1 = Student()
```

---

## **3.4 Accessing Class Attributes**

### **Class Attributes**

Variables defined inside a class.

### **Example**

```python
class Student:
    college = "IKGPTU"
    
    def display(self):
        print(self.college)
```

Accessing attributes:

```python
s1 = Student()
print(s1.college)
```

---

## **3.5 Modifying Class Attributes**

### **Using Object**

```python
s1.college = "PTU"
print(s1.college)
```

### **Using Class Name**

```python
Student.college = "Punjab Technical University"
```

---

## **3.6 Instance Attributes**

### **What are Instance Attributes?**

Attributes unique to each object.

### **Using **init** Constructor**

```python
class Student:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def show(self):
        print(self.name, self.age)
```

### **Example**

```python
s1 = Student("Shreya", 21)
s1.show()
```

---

## **3.7 Built-in Class Attributes**

Python provides built-in attributes for classes.

| Attribute    | Description          |
| ------------ | -------------------- |
| `__dict__`   | Namespace dictionary |
| `__doc__`    | Documentation string |
| `__name__`   | Class name           |
| `__module__` | Module name          |
| `__bases__`  | Base classes         |

### **Example**

```python
print(Student.__name__)
print(Student.__dict__)
```

---

## **3.8 Garbage Collection**

### **What is Garbage Collection?**

Automatic process of **freeing unused memory**.

### **How Python Handles Garbage Collection**

* Reference counting
* Automatic cleanup

### **Example**

```python
x = 10
x = None
```

Memory for `10` is released.

---

## **3.9 Destroying Objects**

### **Destructor Method**

```python
__del__()
```

### **Purpose**

Called when an object is destroyed.

### **Example**

```python
class Demo:
    def __del__(self):
        print("Object destroyed")

obj = Demo()
del obj
```

---

## **Difference Between Class and Object**

| Class     | Object          |
| --------- | --------------- |
| Blueprint | Instance        |
| Logical   | Physical        |
| No memory | Occupies memory |

---

## **Key Exam & Viva Points (OOPS)**

* Difference between class and object
* Purpose of `__init__`
* Class vs instance attributes
* Garbage collection meaning
* Destructor usage

---