
## **Module 5: Advanced Python Concepts**

### 1. Generators and Iterators

* Iterators
* Generators
* any() Function
* all() Function
* with Statement
* Data Compression

### 2. Collections Module

* namedtuple()
* deque
* ChainMap
* Counter
* OrderedDict
* DefaultDict
* UserDict
* UserList
* UserString

### 3. Python Date and Time

* Date Module
* Time Module
* DateTime Module

---
---

# Generators and Iterators

## Iterators

An iterator is an object in Python that allows us to traverse through all the elements of a collection (such as lists or tuples) one element at a time.

### Iterator Protocol
Any object that has:
- The `__iter__()` method (returns an iterator object) and
- The `__next__()` method (returns the next item of the collection)

follows the iterator protocol.

### Example
```python
# Creating a list
my_list = [1, 2, 3, 4]

# Creating an iterator object from the list
iterator = iter(my_list)

# Using the next() function to access elements
print(next(iterator))  # Outputs: 1
print(next(iterator))  # Outputs: 2
```

**Explanation:**
- `iter(my_list)` returns an iterator object.
- `next(iterator)` fetches the next item in the list.

---

## Generators

A generator is a special type of iterator that allows us to iterate over values one at a time, but unlike normal iterators, we can define them with a function using `yield` instead of returning a value.

### Generator Example
```python
def my_generator():
    yield 1
    yield 2
    yield 3

# Calling the generator function
gen = my_generator()

print(next(gen))  # Outputs: 1
print(next(gen))  # Outputs: 2
```

**Explanation:**
- `yield` returns a value and pauses the function, allowing it to resume when `next()` is called again.

### Use Case of Generators
- Saves memory as it doesn’t load all values at once, unlike lists.

---

## any() and all() Functions

- `any()`: Returns `True` if any element in an iterable is true.
- `all()`: Returns `True` if all elements in an iterable are true.

### Example
```python
# any() returns True if at least one item is true
print(any([False, False, True]))  # Outputs: True

# all() returns True if all items are true
print(all([True, True, True]))  # Outputs: True
```

---

## with Statement

The `with` statement is used to simplify working with resources like file handling. It automatically closes the resource after the block of code is executed.

### Example
```python
with open('example.txt', 'r') as file:
    content = file.read()
    print(content)

# The file is automatically closed here
```

**Explanation:**
- `with` ensures that the file is closed, even if an error occurs during the file operations.

---

# Data Compression in Python

Data compression means reducing the size of data to save space or speed up data transfer. In Python, you can compress text, files, images, or audio using special tools called libraries. These libraries make it easy to compress and decompress data. Let’s look at some simple ways to use these libraries for compression.

## 1. Using zlib for Text Compression (Lossless)

The `zlib` library compresses data and allows you to restore the original data later.

### Example: Compress and Decompress Text
```python
import zlib

# Original text (converted to bytes)
text = b"This is an example of data compression in Python. " * 10

# Compress the text
compressed_text = zlib.compress(text)
print(f"Compressed data: {compressed_text}")

# Decompress to get the original text
decompressed_text = zlib.decompress(compressed_text)
print(f"Decompressed text: {decompressed_text.decode()}")  # Convert bytes back to text
```

---

## 2. Using gzip to Compress Files (Lossless)

The `gzip` library is used for compressing and decompressing files.

### Example: Compress and Decompress a File
```python
import gzip

# Write compressed data to a file
with gzip.open('example.txt.gz', 'wb') as f:
    f.write(b"This is a file compressed with gzip.")

# Read and decompress the file
with gzip.open('example.txt.gz', 'rb') as f:
    content = f.read()
    print(content.decode())  # Output the original content
```

---

## 3. Using zipfile for Multiple Files (Lossless)

The `zipfile` library allows you to compress multiple files into a single `.zip` file.

### Example: Create and Extract a Zip File
```python
import zipfile

# Compress files into a zip archive
with zipfile.ZipFile('example.zip', 'w') as zipf:
    zipf.write('example.txt')  # Replace 'example.txt' with your file name

# Extract files from the zip archive
with zipfile.ZipFile('example.zip', 'r') as zipf:
    zipf.extractall('extracted_files')  # All files will be extracted here
```

---

## 4. Using Pillow for Image Compression (Lossy)

For compressing images, we use the Pillow library. It can save images with lower quality to reduce file size.

### Example: Compress an Image
```python
from PIL import Image

# Open an image file
image = Image.open('example.jpg')

# Save the image with lower quality to reduce size
image.save('compressed_example.jpg', quality=30)  # Quality ranges from 0 (lowest) to 100 (highest)

print("Image compressed successfully.")
```

---

## 5. Using pydub for Audio Compression (Lossy)

The `pydub` library lets you compress audio files like MP3 or WAV.

### Example: Compress an Audio File
```python
from pydub import AudioSegment

# Load an audio file (requires ffmpeg installed)
audio = AudioSegment.from_file("example.wav")

# Compress to MP3 format with reduced quality
audio.export("compressed_example.mp3", format="mp3", bitrate="128k")

print("Audio compressed successfully.")
```

---

## Key Points for Beginners:
- **Lossless Compression:** You can restore the exact original data after decompression (e.g., zlib, gzip, zipfile).
- **Lossy Compression:** Some quality is lost, but the file size becomes much smaller (e.g., for images and audio).
- **When to Use:**
  - Use lossless for text or important files.
  - Use lossy for images, videos, or audio where a slight reduction in quality is okay.

By using these Python libraries, you can easily manage and save space for your data!

---

## Data Compression (Basic Example)

Data compression techniques allow you to reduce the size of data.

### Example using list comprehension (a basic form of compression):
```python
# Original list
nums = [1, 2, 3, 4, 5]

# Compressed list (squared numbers)
squares = [x*x for x in nums]

print(squares)  # Outputs: [1, 4, 9, 16, 25]
```

**Explanation:**
- The list comprehension `[x*x for x in nums]` creates a new list by squaring each element of the original list.

---

# Collections Module

In Python, the `collections` module includes specialized container data types that extend the functionality of basic collections like lists, tuples, sets, and dictionaries. These types are designed to help us handle and organize data more efficiently and effectively.

Some common types of collections include:
- **`namedtuple()`:** A tuple-like object that allows us to access elements by name instead of by position, making our code more readable.
- **`deque`:** A double-ended queue that enables fast appends and pops from both ends of the collection, useful for implementing queues or stacks.
- **`ChainMap`:** A collection that combines multiple dictionaries into one. We can search through them as if they were a single dictionary without merging them.
- **`Counter`:** A collection that counts how often each element appears in an iterable (e.g., a list or string), making it useful for frequency analysis.
- **`OrderedDict`:** A dictionary that maintains the order of items based on their insertion order, which regular dictionaries in earlier Python versions did not guarantee.
- **`DefaultDict`:** A dictionary that provides a default value when a key does not exist, making it easier to avoid errors when working with missing keys.
- **`UserDict`:** A wrapper around dictionaries that allows us to customize the behavior of dictionaries, such as adding special functionality when modifying data.
- **`UserList`:** A wrapper around lists that lets us create custom lists with additional behavior, such as logging changes or applying transformations.
- **`UserString`:** A wrapper around strings that lets us add custom methods or modify how string data behaves.

These specialized collections provide additional functionality to help us manage and manipulate data more effectively.

---

## 1. namedtuple()

### What it is:
It's like creating a custom type of "tuple" (an ordered collection of items) where each item has a name. Instead of accessing the data by position (like `person[0]`), you can use a name (like `person.name`).

### Why it's useful:
It makes our code easier to read and understand because each value is labeled with a name.

### Python Code:
```python
from collections import namedtuple
Person = namedtuple('Person', ['name', 'age'])
person = Person(name='John', age=30)
print(person.name)  # Outputs: John
```

---

## 2. deque()

### What it is:
A special type of list that allows you to add or remove items from both the front and the back very quickly.

### Why it's useful:
It's great for situations where you need to manage a queue (first in, first out) or a stack (last in, first out).

### Python Code:
```python
from collections import deque
d = deque([1, 2, 3])
d.appendleft(0)  # Adds 0 to the front
d.append(4)      # Adds 4 to the back
print(d)  # Outputs: deque([0, 1, 2, 3, 4])
```

---

## 3. ChainMap()

### What it is:
Combines multiple dictionaries into one, allowing you to search through them all at once as if they were one big dictionary.

### Why it's useful:
It helps you work with several dictionaries together without actually merging them into one.

### Python Code:
```python
from collections import ChainMap
dict1 = {'a': 1, 'b': 2}
dict2 = {'b': 3, 'c': 4}
chain = ChainMap(dict1, dict2)
print(chain['b'])  # Outputs: 2 (from dict1)
```

---

## 4. Counter()

### What it is:
A special type of dictionary that counts how many times each item appears in a list or other collection.

### Why it's useful:
It helps you quickly see how often something occurs, like counting the number of apples or oranges in a list.

### Python Code:
```python
from collections import Counter
data = ['apple', 'orange', 'apple', 'banana', 'orange', 'apple']
counter = Counter(data)
print(counter)  # Outputs: Counter({'apple': 3, 'orange': 2, 'banana': 1})
```

---

## 5. OrderedDict()

### What it is:
A type of dictionary that remembers the order in which items were added. Unlike regular dictionaries (which don't guarantee order), `OrderedDict` keeps the items in the order you inserted them.

### Why it's useful:
It’s helpful when you need to maintain the order of items, such as when working with ordered data.

### Python Code:
```python
from collections import OrderedDict
od = OrderedDict([('one', 1), ('two', 2), ('three', 3)])
od.move_to_end('two')  # Moves 'two' to the end
print(od)  # Outputs: OrderedDict([('one', 1), ('three', 3), ('two', 2)])
```

---

## 6. defaultdict()

### What it is:
A type of dictionary that automatically provides a default value for keys that don’t exist.

### Why it's useful:
Instead of getting an error when you access a key that doesn’t exist, you get a default value (like 0 or an empty list).

### Python Code:
```python
from collections import defaultdict
dd = defaultdict(int)  # Defaults to 0
dd['apple'] += 1
dd['orange'] += 2
print(dd)  # Outputs: defaultdict(<class 'int'>, {'apple': 1, 'orange': 2})
```

---

## 7. UserDict

### What it is:
A wrapper around dictionaries that lets you customize how the dictionary behaves. You can create your own version of a dictionary with special features.

### Why it's useful:
It allows you to add custom behavior, like printing a message whenever a dictionary item is changed.

### Python Code:
```python
from collections import UserDict
class MyDict(UserDict):
    def __setitem__(self, key, value):
        print(f"Setting {key} to {value}")
        super().__setitem__(key, value)

d = MyDict()
d['name'] = 'Alice'  # Outputs: Setting name to Alice
```

---

## 8. UserList

### What it is:
A wrapper around lists that lets you create custom lists with special behavior.

### Why it's useful:
It allows you to modify a list to fit your specific needs, like printing a message every time an item is added.

### Python Code:
```python
from collections import UserList
class MyList(UserList):
    def append(self, item):
        print(f"Adding {item} to the list")
        super().append(item)

l = MyList()
l.append(10)  # Outputs: Adding 10 to the list
```

---

## 9. UserString

### What it is:
A wrapper around strings that lets you create custom strings with special features.

### Why it's useful:
You can add your own methods to modify how strings work, like adding a method to reverse the string.

### Python Code:
```python
from collections import UserString
class MyString(UserString):
    def reverse(self):
        return self.data[::-1]

s = MyString("Hello")
print(s.reverse())  # Outputs: olleH
```

---

## In Summary:
These tools help you manage and work with collections of data, such as lists and dictionaries, in more flexible ways. Some of them add new features, like automatically counting items, remembering the order of items, or allowing you to create custom behaviors for how your data is stored or accessed. They are especially helpful when you're working with large or complex sets of data.

---

## Collections Module Examples

### namedtuple()
A namedtuple is like a regular tuple but with named fields.

#### Example:
```python
from collections import namedtuple

# Define a namedtuple
Point = namedtuple('Point', ['x', 'y'])

# Create an instance
p = Point(2, 3)

print(p.x)  # Outputs: 2
print(p.y)  # Outputs: 3
```

**Explanation:**
- `Point` is a tuple-like class, but you can access elements using names (x, y) instead of indices.

---

### deque
A deque (double-ended queue) allows you to append and pop items from both ends efficiently.

#### Example:
```python
from collections import deque

# Create a deque
d = deque([1, 2, 3])

# Append and pop from both ends
d.append(4)
d.appendleft(0)

print(d)  # Outputs: deque([0, 1, 2, 3, 4])
```

---

### ChainMap
`ChainMap` groups multiple dictionaries into one view.

#### Example:
```python
from collections import ChainMap

# Two dictionaries
dict1 = {'a': 1, 'b': 2}
dict2 = {'b': 3, 'c': 4}

# Create a ChainMap
chain = ChainMap(dict1, dict2)

print(chain['b'])  # Outputs: 2 (from the first dictionary)
```

---

### Counter
A `Counter` is a dictionary subclass that counts the occurrences of items.

#### Example:
```python
from collections import Counter

# Create a Counter
count = Counter([1, 2, 2, 3, 3, 3])

print(count)  # Outputs: Counter({3: 3, 2: 2, 1: 1})
```

---

### OrderedDict
An `OrderedDict` remembers the order in which items are inserted.

#### Example:
```python
from collections import OrderedDict

# Create an OrderedDict
od = OrderedDict()

od['a'] = 1
od['b'] = 2

print(od)  # Outputs: OrderedDict([('a', 1), ('b', 2)])
```

---

### DefaultDict
A `DefaultDict` is like a normal dictionary, but it provides a default value for non-existent keys.

#### Example:
```python
from collections import defaultdict

# Create a DefaultDict with a default type of int
dd = defaultdict(int)

dd['a'] += 1

print(dd['a'])  # Outputs: 1
print(dd['b'])  # Outputs: 0 (default value for int)
```

---

### UserDict, UserList, UserString
These are wrapper classes that can be used to create custom versions of dicts, lists, and strings. They are used when you want to modify the behavior of these data types.

---

# Python Date and Time

Python provides the `datetime` module to work with dates and times. This module allows you to perform operations like fetching the current date, formatting dates, calculating differences, and more.

---

## 1. Importing the datetime Module

To use the `datetime` module:
```python
from datetime import datetime
```
This is the way to import the `datetime` class from the `datetime` module. This import allows us to directly access the `datetime` class to create, manipulate, and format date and time objects.

---

## 2. Getting the Current Date and Time

Use `datetime.now()` to fetch the current date and time.

#### Example:
```python
from datetime import datetime
now = datetime.now()  # Fetch current date and time
print(now)  # Outputs: 2024-11-30 16:20:45.123456
```

**What it returns:** A `datetime` object containing year, month, day, hour, minute, second, and microsecond.

**Type:** `<class 'datetime.datetime'>`

---

## 3. Formatting Dates and Times

Use the `strftime()` method to format a `datetime` object into a string.

#### Example:
```python
formatted_date = now.strftime("%Y-%m-%d %H:%M:%S")
print(formatted_date)  # Outputs: 2024-11-30 16:20:45
```

#### Common Format Codes:
| Code | Description | Example |
|------|-------------|---------|
| `%Y` | Year (4 digits) | 2024 |
| `%m` | Month (2 digits) | 11 |
| `%d` | Day (2 digits) | 30 |
| `%H` | Hour (24-hour format) | 16 |
| `%M` | Minute | 20 |
| `%S` | Second | 45 |
| `%A` | Full weekday name | Saturday |
| `%B` | Full month name | November |

---

## 4. Parsing Strings into Datetime

Use `strptime()` to convert a string into a `datetime` object.

#### Example:
```python
date_str = "2024-11-30 16:20:45"
date_obj = datetime.strptime(date_str, "%Y-%m-%d %H:%M:%S")
print(date_obj)  # Outputs: 2024-11-30 16:20:45
```

---

## 5. Getting Specific Parts of a Datetime

You can extract individual components like year, month, day, etc.

#### Example:
```python
print("Year:", now.year)  # Outputs: 2024
print("Month:", now.month)  # Outputs: 11
print("Day:", now.day)  # Outputs: 30
print("Hour:", now.hour)  # Outputs: 16
print("Minute:", now.minute)  # Outputs: 20
print("Second:", now.second)  # Outputs: 45
```

---

## 6. Date Arithmetic

You can add or subtract days, hours, or minutes using `timedelta`.

#### Example:
```python
from datetime import timedelta
future_date = now + timedelta(days=7)  # Adds 7 days
print(future_date)  # Outputs: 2024-12-07 16:20:45

past_date = now - timedelta(hours=5)  # Subtracts 5 hours
print(past_date)  # Outputs: 2024-11-30 11:20:45
```

---

## 7. Comparing Dates

`Datetime` objects can be compared using comparison operators (`<`, `>`, `==`, etc.).

#### Example:
```python
date1 = datetime(2024, 11, 30)
date2 = datetime(2024, 12, 1)
if date1 < date2:
    print("date1 is earlier than date2")
```

---

## 8. Other Useful Methods

| Method | Description |
|--------|-------------|
| `today()` | Returns the current date without time. |
| `date()` | Extracts the date part of a datetime. |
| `time()` | Extracts the time part of a datetime. |
| `weekday()` | Returns the day of the week as an integer (0=Monday). |

#### Example:
```python
print("Today's date:", now.date())  # Outputs: 2024-11-30
print("Current time:", now.time())  # Outputs: 16:20:45.123456
print("Day of the week:", now.weekday())  # Outputs: 5 (Saturday)
```

---

## Summary
1. Use `datetime.now()` to get the current date and time.
2. Use `strftime()` for formatting and `strptime()` for parsing strings into datetime.
3. Perform arithmetic with `timedelta`.
4. Extract individual components like year, month, day, etc.
5. Compare dates directly using comparison operators.

---

## Python Date and Time (Simple Example)

Python's `datetime` module provides an efficient way to work with dates and times.

#### Example:
```python
from datetime import datetime

# Get current date and time
now = datetime.now()
print(now)  # Outputs: current date and time

# Formatting the date
formatted_date = now.strftime("%Y-%m-%d %H:%M:%S")
print(formatted_date)  # Outputs: formatted date
```

**Explanation:**
- `datetime.now()` returns the current date and time.
- `strftime()` formats the date into a readable string.