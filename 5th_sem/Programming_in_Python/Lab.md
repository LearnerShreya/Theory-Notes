
**Table of Contents - Python Programming Tasks**

| **Task No.** | **Task Description** | **Topic** |
|--------------|---------------------|-----------|
| **1** | WAP to demonstrate different data types in Python | Data Types & Operations |
| **2** | WAP to perform different Arithmetic Operations on numbers in Python | Data Types & Operations |
| **3** | WAP to create, concatenate and print a string and accessing sub-string from a given string | Data Types & Operations |
| **4** | Write a python script to print the current date in the following format "Sun May 29 02:26:23 IST 2017" | Date & Time |
| **5** | WAP to create, append, and remove lists in python | Data Structures |
| **6** | WAP to demonstrate working with tuples in python | Data Structures |
| **7** | WAP to demonstrate working with dictionaries in python | Data Structures |
| **8** | WAP to find largest of three numbers | Mathematical Problems |
| **9** | WAP to convert temperatures to and from Celsius, Fahrenheit | Mathematical Problems |
| **10** | WAP to construct the star pattern using nested for loop | Patterns & Loops |
| **11** | WAP to prints prime numbers less than 20 | Mathematical Problems |
| **12** | WAP to find factorial of a number using Recursion | Mathematical Problems |
| **13** | WAP to check if triangle is right triangle using Pythagorean Theorem | Mathematical Problems |
| **14** | WAP to define a module to find Fibonacci Numbers and import the module | Modules & Imports |
| **15** | WAP to define a module and import a specific function | Modules & Imports |
| **16** | Write a script named copyfile.py to copy contents between files | File Handling |
| **17** | WAP to print unique words from a text file in alphabetical order | File Handling |
| **18** | Write a Python class to convert an integer to a roman numeral | Object-Oriented Programming |
| **19** | Write a Python class to implement pow(x, n) | Object-Oriented Programming |
| **20** | Write a Python class to reverse a string word by word | Object-Oriented Programming |

---

## Task 1: WAP to demonstrate different data types in Python.
```python
# Numeric Types
integer = 10                                          # Integer
floating_point = 10.5                           # Float
complex_number = 3 + 4j                   # Complex

# Sequence Types
string = "Hello, Shreya!"                       # String
list_example = [1, 2, 3, 4, 5]                # List
tuple_example = (1, 2, 3, 4, 5)             # Tuple

# Boolean Type
is_true = True
is_false = False

# Set Type
set_example = {1, 2, 3, 4, 5}

# Dictionary Type
dict_example = {'name': 'Shreya', 'age': 20, 'city': 'Banka'}

# Binary Types
memory_view = memoryview(bytes(5))                    # Memoryview
byte_array = bytearray(b'hello')                                  # Bytearray
byte_example = bytes(b'hello')                                   # Bytes

print(f'Integer: {integer}')
print(f'Float: {floating_point}')
print(f'Complex: {complex_number}')

print(f'\nString: {string}')
print(f'List: {list_example}')
print(f'Tuple: {tuple_example}')

print(f'\nBoolean True: {is_true}')
print(f'Boolean False: {is_false}')

print(f'\nSet: {set_example}')

print(f'\nDictionary: {dict_example}')

print(f'\nMemoryview: {memory_view}')
print(f'Bytearray: {byte_array}')
print(f'Bytes: {byte_example}')
```

**Output:**
```
Integer: 10
Float: 10.5
Complex: (3+4j)

String: Hello, Shreya!
List: [1, 2, 3, 4, 5]
Tuple: (1, 2, 3, 4, 5)

Boolean True: True
Boolean False: False

Set: {1, 2, 3, 4, 5}

Dictionary: {'name': 'Shreya', 'age': 20, 'city': 'Banka'}

Memoryview: <memory at 0x...>
Bytearray: bytearray(b'hello')
Bytes: b'hello'
```

## Task 2: WAP to perform different Arithmetic Operations on numbers in Python.
```python
a = 10
b = 5

print(f'Addition: {a + b}')
print(f'Subtraction: {a - b}')
print(f'Multiplication: {a * b}')
print(f'Division: {a / b}')
print(f'Modulus: {a % b}')
print(f'Exponentiation: {a ** b}')
print(f'Floor Division: {a // b}')
```

**Output:**
```
Addition: 15
Subtraction: 5
Multiplication: 50
Division: 2.0
Modulus: 0
Exponentiation: 100000
Floor Division: 2
```

## Task 3: WAP to create, concatenate and print a string and accessing sub-string from a given string.
```python
# String creation and operations

str1 = "Hello"
str2 = "World"
concatenated_str = str1 + " " + str2
substring = concatenated_str[1:5]

print(f'Concatenated String: {concatenated_str}')
print(f'Sub-string: {substring}')
```

**Output:**
```
Concatenated String: Hello World
Sub-string: ello
```

## Task 4: Write a python script to print the current date in the following format "Sun May 29 02:26:23 IST 2017"
```python
import datetime

current_date = datetime.datetime.now().strftime("%a %b %d %H:%M:%S IST %Y")
print(f'Current Date: {current_date}')
```

**Output:**
```
Current Date: Thu Jan 01 12:30:45 IST 2023
```

## Task 5: WAP to create, append, and remove lists in python.
```python
# List operations
my_list = [1, 2, 3]
print(f'Initial List: {my_list}')

# Appending to a list
my_list.append(4)
print(f'List after append: {my_list}')

# Removing from a list
my_list.remove(2)
print(f'List after removal: {my_list}')
```

**Output:**
```
Initial List: [1, 2, 3]
List after append: [1, 2, 3, 4]
List after removal: [1, 3, 4]
```

## Task 6: WAP to demonstrate working with tuples in python.
```python
# Tuple operations
my_tuple = (1, 2, 3, 4, 5)
print(f'Tuple: {my_tuple}')

# Accessing elements in a tuple
print(f'First element: {my_tuple[0]}')

# Slicing a tuple
print(f'Slice [1:3]: {my_tuple[1:3]}')

# Concatenating tuples
new_tuple = my_tuple + (6, 7)
print(f'Concatenated Tuple: {new_tuple}')

# Finding length of a tuple
print(f'Length of tuple: {len(my_tuple)}')

# Tuple unpacking
a, b, c, d, e = my_tuple
print(f'Unpacked Values: {a}, {b}, {c}, {d}, {e}')
```

**Output:**
```
Tuple: (1, 2, 3, 4, 5)
First element: 1
Slice [1:3]: (2, 3)
Concatenated Tuple: (1, 2, 3, 4, 5, 6, 7)
Length of tuple: 5
Unpacked Values: 1, 2, 3, 4, 5
```

## Task 7: WAP to demonstrate working with dictionaries in python.
```python
# Dictionary operations
my_dict = {'a': 1, 'b': 2, 'c': 3}
print(f'Dictionary: {my_dict}')

# Accessing elements
print(f"Value for key 'b': {my_dict['b']}")

# Adding elements
my_dict['d'] = 4
print(f'Dictionary after addition: {my_dict}')

# Removing elements using pop
removed_value = my_dict.pop('b')
print(f'Value removed: {removed_value}')
print(f'Dictionary after pop: {my_dict}')

# Removing elements using del
del my_dict['a']
print(f'Dictionary after deletion: {my_dict}')

# Appending elements (using update method)
my_dict.update({'e': 5, 'f': 6})
print(f'Dictionary after update: {my_dict}')

# Accessing all keys and values
keys = my_dict.keys()
values = my_dict.values()
print(f'Keys: {keys}')
print(f'Values: {values}')

# Looping through dictionary
for key, value in my_dict.items():
    print(f'Key: {key}, Value: {value}')
```

**Output:**
```
Dictionary: {'a': 1, 'b': 2, 'c': 3}
Value for key 'b': 2
Dictionary after addition: {'a': 1, 'b': 2, 'c': 3, 'd': 4}
Value removed: 2
Dictionary after pop: {'a': 1, 'c': 3, 'd': 4}
Dictionary after deletion: {'c': 3, 'd': 4}
Dictionary after update: {'c': 3, 'd': 4, 'e': 5, 'f': 6}
Keys: dict_keys(['c', 'd', 'e', 'f'])
Values: dict_values([3, 4, 5, 6])
Key: c, Value: 3
Key: d, Value: 4
Key: e, Value: 5
Key: f, Value: 6
```

## Task 8: WAP to find largest of three numbers.
```python
a = 5
b = 10
c = 3

largest = max(a, b, c)
print(f'Largest number: {largest}')
```

**Output:**
```
Largest number: 10
```

## Task 9: WAP to convert temperatures to and from Celsius, Fahrenheit. [ Formula: c/5 = f-32/9]
```python
# Celsius to Fahrenheit
celsius = 25
fahrenheit = (celsius * 9/5) + 32
print(f'{celsius}C is {fahrenheit}F')

# Fahrenheit to Celsius
fahrenheit = 77
celsius = (fahrenheit - 32) * 5/9
print(f'{fahrenheit}F is {celsius}C')
```

**Output:**
```
25C is 77.0F
77F is 25.0C
```

## Task 10: WAP to construct the following pattern, using a nested for loop 
```
*
*
* *
* * *
* * * *
* * *
* *
*
*
```
```python
n = 4
# Upper part of the pattern
for i in range(n):
    for j in range(i + 1):
        print("*", end=" ")
    print()

# Lower part of the pattern
for i in range(n - 1):
    for j in range(n - i - 1):
        print("*", end=" ")
    print()
```

**Output:**
```
* 
* * 
* * * 
* * * * 
* * * 
* * 
* 
```

## Task 11: WAP to prints prime numbers less than 20.
```python
def is_prime(num):
    if num <= 1:  
        return False
    for i in range(2, num):  
        if num % i == 0:
            return False
    return True

for number in range(2, 20):
    if is_prime(number):
        print(number)
```

**Output:**
```
2
3
5
7
11
13
17
19
```

## Task 12: WAP to find factorial of a number using Recursion.
```python
def factorial(n):
    if n == 1:
        return 1
    else:
        return n * factorial(n - 1)

num = 5
print(f'Factorial of {num} is {factorial(num)}')
```

**Output:**
```
Factorial of 5 is 120
```

## Task 13: WAP that accepts the lengths of three sides of a triangle as inputs. The program output should indicate whether or not the triangle is a right triangle (Recall from the Pythagorean Theorem that in a right triangle, the square of one side equals the sum of the squares of the other two sides).
```python
a = 3
b = 4
c = 5

if a**2 + b**2 == c**2 or a**2 + c**2 == b**2 or b**2 + c**2 == a**2:
    print("The triangle is a right triangle.")
else:
    print("The triangle is not a right triangle.")
```

**Output:**
```
The triangle is a right triangle.
```

## Task 14: WAP to define a module to find Fibonacci Numbers and import the module to another program.

**fibonacci_module.py:**
```python
# fibonacci_module.py
def fibonacci(n):
    a, b = 0, 1
    while a < n:
        print(a, end=' ')
        a, b = b, a + b
    print()
```

**main_program.py:**
```python
# main_program.py
import fibonacci_module

fibonacci_module.fibonacci(10)
```

**Output:**
```
0 1 1 2 3 5 8 
```

## Task 15: WAP to define a module and import a specific function in that module to another program.

**my_module.py:**
```python
# my_module.py
def greet(name):
    return f"Hello, {name}!"
```

**main_program.py:**
```python
# main_program.py
from my_module import greet

print(greet("Shreya"))
```

**Output:**
```
Hello, Shreya!
```

## Task 16: Write a script named copyfile.py. This script should prompt the user for the names of two text files. The contents of the first file should be input and written to the second file.

**source.txt:**
```
This is a sample text file.
It contains multiple lines of text.
```

**copyfile.py:**
```python
# copyfile.py
source_file = input("Enter source file name: ")
dest_file = input("Enter destination file name: ")

# Copy contents
try:
    with open(source_file, 'r') as src:
        data = src.read()
    
    with open(dest_file, 'w') as dst:
        dst.write(data)

    print("File copied successfully.")
except FileNotFoundError:
    print(f"Error: The file {source_file} does not exist.")
except Exception as e:
    print(f"An error occurred: {e}")
```

**Output:**
```
Enter source file name: source.txt
Enter destination file name: dest.txt
File copied successfully.
```

## Task 17: WAP that inputs a text file. The program should print all of the unique words in the file in alphabetical order.

**sample.txt:**
```
This is a sample text file. This file contains some sample text.
```

**unique_words.py:**
```python
# unique_words.py
filename = 'D:\\Shreya\\17\\sample.txt' 
try:
    with open(filename, 'r') as file:
        # Read the file and split into words
        words = file.read().lower().split()
        # Remove punctuation from words
        words = [word.strip('.,!?"\'') for word in words]
    # Get unique words and sort them
    unique_words = sorted(set(words))
    print('Unique words in alphabetical order:')
    for word in unique_words:
        print(word)
except FileNotFoundError:
    print(f"Error: The file {filename} does not exist.")
except Exception as e:
    print(f"An error occurred: {e}")
```

**Output:**
```
Unique words in alphabetical order:
a
contains
file
is
sample
some
text
this
```

## Task 18: Write a Python class to convert an integer to a roman numeral.
```python
class IntegerToRoman:
    def __init__(self):
        self.value_map = [
            (1000, 'M'), (900, 'CM'), (500, 'D'), (400, 'CD'),
            (100, 'C'), (90, 'XC'), (50, 'L'), (40, 'XL'),
            (10, 'X'), (9, 'IX'), (5, 'V'), (4, 'IV'), (1, 'I')
        ]

    def int_to_roman(self, num):
        roman = ''
        while num > 0:
            for i, r in self.value_map:
                while num >= i:
                    roman += r
                    num -= i
        return roman

converter = IntegerToRoman()
print(converter.int_to_roman(1994))
```

**Output:**
```
MCMXCIV
```

## Task 19: Write a Python class to implement pow(x, n)
```python
class Power:
    def pow(self, x, n):
        return x ** n

power = Power()
print(power.pow(2, 3))
```

**Output:**
```
8
```

## Task 20: Write a Python class to reverse a string word by word.
```python
class ReverseString:
    def reverse_words(self, s):
        return ' '.join(reversed(s.split()))

reverser = ReverseString()
print(reverser.reverse_words("Shreya Singh"))
```

**Output:**
```
Singh Shreya
```

---