## Decorators in Python

### Short idea first

A **decorator** in Python is a function that **adds extra behavior to another function** without changing the original function’s code.

Think of it like:

> wrapping a gift
> the gift stays the same, but the wrapper adds something extra.

---

## Why decorators are needed

They help you:

* add **logging**
* add **authentication**
* measure **execution time**
* check **permissions**
* avoid repeating the same code again and again

All without modifying the original function logic.

---

## Core concept behind decorators

In Python:

* **Functions are first-class objects**
* You can pass a function as an argument
* You can return a function from another function

Decorators are built on this idea.

---

## Basic example (without @ syntax)

```python
def my_decorator(func):
    def wrapper():
        print("Before function execution")
        func()
        print("After function execution")
    return wrapper

def say_hello():
    print("Hello")

say_hello = my_decorator(say_hello)
say_hello()
```

### Output

```
Before function execution
Hello
After function execution
```

What happened:

* `say_hello` was **wrapped** inside `wrapper`
* Extra behavior was added before and after the function call

---

## Same example using `@decorator` syntax

This is the common and clean way.

```python
def my_decorator(func):
    def wrapper():
        print("Before function execution")
        func()
        print("After function execution")
    return wrapper

@my_decorator
def say_hello():
    print("Hello")

say_hello()
```

`@my_decorator` is just a shortcut for:

```python
say_hello = my_decorator(say_hello)
```

---

## Decorator with arguments in function

Most real functions take arguments.

```python
def my_decorator(func):
    def wrapper(*args, **kwargs):
        print("Before execution")
        result = func(*args, **kwargs)
        print("After execution")
        return result
    return wrapper

@my_decorator
def add(a, b):
    return a + b

print(add(3, 4))
```

### Output

```
Before execution
After execution
7
```

Why `*args` and `**kwargs`?

* To support **any number of arguments**
* Makes the decorator reusable

---

## Real-world example: execution time decorator

```python
import time

def timer(func):
    def wrapper(*args, **kwargs):
        start = time.time()
        result = func(*args, **kwargs)
        end = time.time()
        print("Time taken:", end - start)
        return result
    return wrapper

@timer
def slow_function():
    time.sleep(2)

slow_function()
```

This is heavily used in performance analysis.

---

## Decorator with parameters (advanced but important)

```python
def repeat(n):
    def decorator(func):
        def wrapper(*args, **kwargs):
            for _ in range(n):
                func(*args, **kwargs)
        return wrapper
    return decorator

@repeat(3)
def greet():
    print("Hello")

greet()
```

Output:

```
Hello
Hello
Hello
```

Here:

* `repeat(3)` is called first
* It returns a decorator
* That decorator wraps the function

---

## Built-in decorators you must know

| Decorator       | Use                          |
| --------------- | ---------------------------- |
| `@staticmethod` | Method without `self`        |
| `@classmethod`  | Method with `cls`            |
| `@property`     | Access method like attribute |

Example:

```python
class Student:
    def __init__(self, marks):
        self._marks = marks

    @property
    def marks(self):
        return self._marks
```

Usage:

```python
s = Student(90)
print(s.marks)   # no parentheses
```

---

## Key points to remember

* Decorators **modify behavior**, not logic
* Original function code stays untouched
* `@decorator` is just syntax sugar
* Always use `*args` and `**kwargs` for reusable decorators
* Widely used in **frameworks** like Flask, Django, FastAPI

---

## Common mistake

Forgetting to return the function result inside `wrapper`.

Wrong:

```python
func()
```

Correct:

```python
return func()
```

---