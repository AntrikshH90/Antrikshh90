# 🐍 Python Roadmap — Zero to Advanced

> A complete, self-contained guide covering **theory**, **coding questions**, **practice exercises** and **projects** for every level of Python mastery.

---

## 📌 Table of Contents

1. [How to Use This Roadmap](#how-to-use-this-roadmap)
2. [Phase 1 — Absolute Beginner (0 → Foundations)](#phase-1--absolute-beginner)
3. [Phase 2 — Beginner+ (Core Python)](#phase-2--beginner-core-python)
4. [Phase 3 — Intermediate (OOP & Modules)](#phase-3--intermediate-oop--modules)
5. [Phase 4 — Intermediate+ (File I/O, Errors & Libraries)](#phase-4--intermediate-file-io-errors--libraries)
6. [Phase 5 — Advanced (Decorators, Generators & Concurrency)](#phase-5--advanced-decorators-generators--concurrency)
7. [Phase 6 — Expert (Internals, Packaging & Performance)](#phase-6--expert-internals-packaging--performance)
8. [Domain Tracks](#domain-tracks)
9. [Practice Projects — All Levels](#practice-projects--all-levels)
10. [Mock Interview Questions](#mock-interview-questions)
11. [Resources & References](#resources--references)

---

## How to Use This Roadmap

| Symbol | Meaning |
|--------|---------|
| 📖 | Theory / Concept |
| 💻 | Coding Exercise |
| 🧩 | Challenge / Problem |
| 🏗️ | Project |
| ✅ | Checkpoint — test yourself before moving on |

Work through each phase **in order**. Complete every ✅ checkpoint before advancing.

---

## Phase 1 — Absolute Beginner

> **Goal:** Write and run your first Python program; understand the REPL, variables and basic data types.

### 📖 1.1 What is Python?
- Interpreted, high-level, dynamically-typed language created by Guido van Rossum (1991).
- Runs on CPython (reference), PyPy, Jython, MicroPython, etc.
- The Python REPL (`python3`) lets you experiment line-by-line.
- Source files have the `.py` extension; run with `python3 script.py`.

### 📖 1.2 Installing Python & Setting Up the Environment
- Download Python ≥ 3.10 from python.org.
- Recommended IDEs: **VS Code** (with Pylance), **PyCharm**, **Jupyter Notebook**.
- Use `python3 --version` to confirm the installation.
- Virtual environments: `python3 -m venv .venv && source .venv/bin/activate`.

### 📖 1.3 Variables, Data Types & Type System
```python
# Variable assignment — no declaration needed
name = "Antriksh"   # str
age  = 20           # int
gpa  = 8.5          # float
flag = True         # bool
nothing = None      # NoneType

# Type checking
print(type(name))   # <class 'str'>

# Dynamic typing
x = 10
x = "hello"         # valid — x now holds a str
```

**Built-in scalar types:** `int`, `float`, `complex`, `bool`, `str`, `bytes`, `NoneType`.

**Type conversion (casting):**
```python
int("42")       # → 42
float(7)        # → 7.0
str(3.14)       # → "3.14"
bool(0)         # → False  (falsy values: 0, "", [], {}, None)
```

### 📖 1.4 Operators
| Category | Operators |
|----------|-----------|
| Arithmetic | `+ - * / // % **` |
| Comparison | `== != < > <= >=` |
| Logical | `and or not` |
| Assignment | `= += -= *= /= //= %= **=` |
| Bitwise | `& \| ^ ~ << >>` |
| Identity | `is  is not` |
| Membership | `in  not in` |

### 📖 1.5 Input & Output
```python
name = input("Enter your name: ")   # always returns str
print(f"Hello, {name}!")            # f-string (Python 3.6+)
print("Pi is {:.2f}".format(3.14159))
```

### 💻 Coding Exercises — Phase 1
1. Print your name, age, and university on separate lines.
2. Take two numbers as input and print their sum, difference, product and quotient.
3. Convert Celsius to Fahrenheit: `F = C * 9/5 + 32`.
4. Swap two variables **without** a temporary variable.
5. Check whether a number is even or odd using the modulo operator.

### 🧩 Challenges — Phase 1
1. Write a program that prints the area and perimeter of a rectangle given length and width.
2. Given a year as input, determine if it is a leap year.
3. A shopkeeper gives a 10% discount for bills over ₹500. Take the bill amount and print the final payable amount.

### ✅ Checkpoint 1
- [ ] Can you explain the difference between `==` and `is`?
- [ ] What is the result of `10 // 3` and `10 % 3`?
- [ ] What does `bool([])` evaluate to and why?

---

## Phase 2 — Beginner+ (Core Python)

> **Goal:** Master control flow, loops, and Python's core data structures.

### 📖 2.1 Conditional Statements
```python
score = int(input("Score: "))

if score >= 90:
    grade = "A"
elif score >= 75:
    grade = "B"
elif score >= 50:
    grade = "C"
else:
    grade = "F"

print(f"Grade: {grade}")
```

**Ternary (conditional expression):**
```python
result = "pass" if score >= 50 else "fail"
```

### 📖 2.2 Loops
```python
# for loop with range
for i in range(1, 6):        # 1 2 3 4 5
    print(i, end=" ")

# while loop
n = 10
while n > 0:
    print(n, end=" ")
    n -= 1

# break / continue / else on loops
for n in range(2, 10):
    for x in range(2, n):
        if n % x == 0:
            break
    else:
        print(n, "is prime")
```

### 📖 2.3 Lists
```python
fruits = ["apple", "banana", "cherry"]

# Indexing & slicing
print(fruits[0])        # apple
print(fruits[-1])       # cherry
print(fruits[1:3])      # ['banana', 'cherry']

# Mutation
fruits.append("mango")
fruits.insert(1, "avocado")
fruits.remove("banana")
popped = fruits.pop()   # removes last element

# List comprehension
squares = [x**2 for x in range(1, 11)]
evens   = [x   for x in range(20) if x % 2 == 0]

# Useful methods: sort(), reverse(), index(), count(), copy()
fruits.sort()
```

### 📖 2.4 Tuples
```python
point = (3, 4)            # immutable
x, y = point              # tuple unpacking
singleton = (42,)         # note the trailing comma
```
Use tuples for **fixed collections** (coordinates, RGB values, DB records).

### 📖 2.5 Dictionaries
```python
person = {"name": "Antriksh", "age": 20, "city": "Kanpur"}

# Access
print(person["name"])
print(person.get("email", "N/A"))   # safe access with default

# Mutation
person["email"] = "antriksh@example.com"
del person["city"]

# Iteration
for key, value in person.items():
    print(f"{key}: {value}")

# Dict comprehension
squares_d = {x: x**2 for x in range(1, 6)}
```

### 📖 2.6 Sets
```python
a = {1, 2, 3, 4}
b = {3, 4, 5, 6}

print(a | b)    # union        {1,2,3,4,5,6}
print(a & b)    # intersection {3,4}
print(a - b)    # difference   {1,2}
print(a ^ b)    # symmetric diff {1,2,5,6}
```

### 📖 2.7 Strings (Deep Dive)
```python
s = "Hello, Python!"

# Methods
s.upper()             # "HELLO, PYTHON!"
s.lower()
s.split(", ")         # ['Hello', 'Python!']
s.replace("Python", "World")
s.strip()             # remove leading/trailing whitespace
s.startswith("He")    # True
s.find("Python")      # index or -1

# Multiline & raw strings
multi = """Line 1
Line 2"""
raw   = r"C:\Users\name"     # backslash is literal

# String formatting
pi = 3.14159
f"{pi:.2f}"           # '3.14'
"{:>10}".format("right")   # right-aligned in 10 chars
```

### 💻 Coding Exercises — Phase 2
1. Print multiplication table (1–10) for a number entered by the user.
2. Find the largest and smallest element in a list without using `max()`/`min()`.
3. Count the frequency of each character in a string using a dictionary.
4. Reverse a string using slicing.
5. Check if a string is a palindrome.
6. Remove duplicates from a list while preserving order.
7. Merge two dictionaries; if a key exists in both, sum the values.
8. Given a list of numbers, separate even and odd numbers into two lists using list comprehension.
9. Generate all prime numbers up to N using the Sieve of Eratosthenes.
10. FizzBuzz: print 1–100; multiples of 3 → "Fizz", 5 → "Buzz", both → "FizzBuzz".

### 🧩 Challenges — Phase 2
1. **Anagram check** — Two strings are anagrams if they contain the same characters.
2. **Two Sum** — Given a list of integers and a target, return the indices of two numbers that add up to the target.
3. **Caesar Cipher** — Encrypt/decrypt a message by shifting letters by a given key.
4. **Word frequency** — Count word occurrences in a paragraph and display the top-5 most frequent.
5. **Matrix addition** — Add two 2-D matrices represented as nested lists.

### ✅ Checkpoint 2
- [ ] What is the difference between a list and a tuple?
- [ ] Explain dictionary `get()` vs direct access `d["key"]`.
- [ ] What does a set comprehension look like?

---

## Phase 3 — Intermediate (OOP & Modules)

> **Goal:** Write reusable code using functions, modules and object-oriented programming.

### 📖 3.1 Functions
```python
# Basic definition
def greet(name, greeting="Hello"):
    """Return a greeting string."""
    return f"{greeting}, {name}!"

print(greet("Antriksh"))           # Hello, Antriksh!
print(greet("Antriksh", "Hi"))     # Hi, Antriksh!

# *args and **kwargs
def total(*args):
    return sum(args)

def describe(**kwargs):
    for k, v in kwargs.items():
        print(f"{k} = {v}")

# Lambda functions
square = lambda x: x ** 2

# Higher-order functions
nums = [3, 1, 4, 1, 5, 9, 2]
sorted_nums = sorted(nums, key=lambda x: -x)   # descending

# map / filter / reduce
doubled   = list(map(lambda x: x * 2, nums))
positives = list(filter(lambda x: x > 0, nums))

from functools import reduce
product   = reduce(lambda a, b: a * b, nums)
```

### 📖 3.2 Scope & Closures
```python
x = "global"

def outer():
    x = "outer"
    def inner():
        nonlocal x
        x = "inner"
        print(x)        # inner
    inner()
    print(x)            # inner  (nonlocal modified it)

outer()
print(x)                # global (unchanged)
```

**Closure:** a function that captures variables from its enclosing scope.
```python
def make_counter():
    count = 0
    def counter():
        nonlocal count
        count += 1
        return count
    return counter

c = make_counter()
c()   # 1
c()   # 2
```

### 📖 3.3 Object-Oriented Programming (OOP)

#### Classes & Objects
```python
class Animal:
    kingdom = "Animalia"           # class variable

    def __init__(self, name, sound):
        self.name  = name          # instance variable
        self.sound = sound

    def speak(self):
        return f"{self.name} says {self.sound}"

    def __repr__(self):
        return f"Animal(name={self.name!r})"


dog = Animal("Rex", "Woof")
print(dog.speak())
print(Animal.kingdom)
```

#### Inheritance & Polymorphism
```python
class Dog(Animal):
    def __init__(self, name, breed):
        super().__init__(name, "Woof")
        self.breed = breed

    def fetch(self, item):
        return f"{self.name} fetches the {item}!"


class Cat(Animal):
    def speak(self):                # overriding (polymorphism)
        return f"{self.name} says Meow"


animals = [Dog("Rex", "Labrador"), Cat("Whiskers", "Meow")]
for a in animals:
    print(a.speak())               # polymorphic call
```

#### Encapsulation & Properties
```python
class BankAccount:
    def __init__(self, owner, balance=0):
        self.owner    = owner
        self.__balance = balance    # name-mangled private

    @property
    def balance(self):
        return self.__balance

    @balance.setter
    def balance(self, amount):
        if amount < 0:
            raise ValueError("Balance cannot be negative")
        self.__balance = amount

    def deposit(self, amount):
        self.balance += amount

    def withdraw(self, amount):
        if amount > self.__balance:
            raise ValueError("Insufficient funds")
        self.balance -= amount
```

#### Abstract Classes & Interfaces
```python
from abc import ABC, abstractmethod

class Shape(ABC):
    @abstractmethod
    def area(self):  ...

    @abstractmethod
    def perimeter(self): ...

class Circle(Shape):
    def __init__(self, r): self.r = r
    def area(self):        return 3.14159 * self.r ** 2
    def perimeter(self):   return 2 * 3.14159 * self.r
```

#### Dunder (Magic) Methods
| Method | Triggered by |
|--------|-------------|
| `__init__` | `ClassName(...)` |
| `__str__` | `str(obj)`, `print(obj)` |
| `__repr__` | `repr(obj)`, REPL echo |
| `__len__` | `len(obj)` |
| `__getitem__` | `obj[key]` |
| `__setitem__` | `obj[key] = val` |
| `__eq__` | `obj1 == obj2` |
| `__lt__` | `obj1 < obj2` |
| `__add__` | `obj1 + obj2` |
| `__iter__`, `__next__` | `for x in obj` |
| `__enter__`, `__exit__` | `with obj:` |

### 📖 3.4 Modules & Packages
```python
# Importing
import math
from math import sqrt, pi
import numpy as np                 # third-party alias

# Creating a module: save as mymath.py
def add(a, b): return a + b

# Creating a package: directory with __init__.py
# mypackage/
#   __init__.py
#   utils.py
#   models.py
```

### 📖 3.5 Standard Library Highlights
| Module | Purpose |
|--------|---------|
| `os` | OS interaction, paths |
| `sys` | Python runtime info |
| `pathlib` | Object-oriented paths |
| `datetime` | Dates and times |
| `random` | Random numbers |
| `math` | Math functions |
| `collections` | `Counter`, `defaultdict`, `deque`, `namedtuple` |
| `itertools` | Infinite iterators, combinatorics |
| `functools` | `reduce`, `lru_cache`, `partial` |
| `json` | JSON encode/decode |
| `re` | Regular expressions |
| `copy` | Shallow & deep copy |

### 💻 Coding Exercises — Phase 3
1. Implement a `Stack` class with `push`, `pop`, `peek`, and `is_empty` methods.
2. Implement a `Queue` class using Python's `deque`.
3. Create a `Student` class. Overload `>` and `<` to compare students by GPA.
4. Write a function that memoizes results using a dictionary (manual LRU cache).
5. Implement a `Vector2D` class supporting `+`, `-`, `*` (scalar), `abs()` and `==`.

### 🧩 Challenges — Phase 3
1. **Linked List** — Implement a singly linked list with `insert`, `delete`, `search` and `display`.
2. **Binary Search Tree** — Implement BST with `insert`, `inorder`, `search`, `delete`.
3. **Design Pattern — Singleton** — Ensure only one instance of a class exists.
4. **Design Pattern — Observer** — Implement a basic event system.
5. **Deck of Cards** — Model a standard 52-card deck using OOP; implement `shuffle` and `deal`.

### ✅ Checkpoint 3
- [ ] Explain the difference between `__str__` and `__repr__`.
- [ ] When would you use `@staticmethod` vs `@classmethod`?
- [ ] What is Method Resolution Order (MRO)?

---

## Phase 4 — Intermediate+ (File I/O, Errors & Libraries)

> **Goal:** Handle files, exceptions robustly, work with common third-party libraries.

### 📖 4.1 File Handling
```python
# Reading
with open("data.txt", "r", encoding="utf-8") as f:
    content = f.read()              # whole file as str
    # OR
    lines = f.readlines()           # list of lines
    # OR
    for line in f:                  # memory-efficient
        print(line.strip())

# Writing
with open("output.txt", "w", encoding="utf-8") as f:
    f.write("Hello, World!\n")

# Appending
with open("log.txt", "a") as f:
    f.write("New log entry\n")
```

### 📖 4.2 Working with CSV & JSON
```python
import csv, json

# CSV read
with open("students.csv") as f:
    reader = csv.DictReader(f)
    for row in reader:
        print(row["name"], row["grade"])

# CSV write
with open("out.csv", "w", newline="") as f:
    writer = csv.DictWriter(f, fieldnames=["name", "score"])
    writer.writeheader()
    writer.writerow({"name": "Antriksh", "score": 95})

# JSON
data = {"name": "Antriksh", "skills": ["Python", "AI"]}
json_str = json.dumps(data, indent=2)
parsed   = json.loads(json_str)

with open("data.json", "w") as f:
    json.dump(data, f, indent=2)
```

### 📖 4.3 Exception Handling
```python
# try / except / else / finally
try:
    result = int(input("Enter a number: "))
except ValueError as e:
    print(f"Invalid input: {e}")
except ZeroDivisionError:
    print("Cannot divide by zero")
else:
    print(f"Result: {result}")   # runs only if no exception
finally:
    print("Always runs")

# Raising exceptions
def divide(a, b):
    if b == 0:
        raise ZeroDivisionError("denominator cannot be zero")
    return a / b

# Custom exceptions
class InsufficientFundsError(Exception):
    def __init__(self, amount, balance):
        super().__init__(f"Cannot withdraw {amount}; balance is {balance}")
        self.amount  = amount
        self.balance = balance
```

**Common built-in exceptions:**
`ValueError`, `TypeError`, `KeyError`, `IndexError`, `AttributeError`,
`FileNotFoundError`, `PermissionError`, `OSError`, `OverflowError`,
`RecursionError`, `StopIteration`, `NotImplementedError`.

### 📖 4.4 Context Managers
```python
# Using contextlib
from contextlib import contextmanager

@contextmanager
def managed_resource(name):
    print(f"Acquiring {name}")
    try:
        yield name
    finally:
        print(f"Releasing {name}")

with managed_resource("DB connection") as res:
    print(f"Using {res}")
```

### 📖 4.5 Regular Expressions
```python
import re

text = "Contact us at support@example.com or admin@test.org"

# Find all emails
emails = re.findall(r"[a-zA-Z0-9_.+-]+@[a-zA-Z0-9-]+\.[a-zA-Z0-9-.]+", text)

# Replace
clean = re.sub(r"\d+", "#", "Order 12345 shipped on day 7")

# Groups
m = re.search(r"(\d{4})-(\d{2})-(\d{2})", "Date: 2024-07-15")
if m:
    year, month, day = m.groups()
```

### 📖 4.6 Virtual Environments & Package Management
```bash
# Create and activate
python3 -m venv .venv
source .venv/bin/activate        # Linux/macOS
.venv\Scripts\activate           # Windows

# Install packages
pip install requests pandas numpy matplotlib

# Freeze / restore
pip freeze > requirements.txt
pip install -r requirements.txt
```

### 💻 Coding Exercises — Phase 4
1. Read a text file and count the number of words, lines and characters.
2. Parse a CSV of students; calculate class average and print students above average.
3. Build a simple file-based contact book (save/load contacts as JSON).
4. Validate email addresses using `re` without using any library.
5. Write a context manager class (not `@contextmanager`) for timing code blocks.

### 🧩 Challenges — Phase 4
1. **Log Parser** — Parse a server log file; extract timestamps and error messages; write a summary CSV.
2. **Config Reader** — Read a `.ini` configuration using `configparser`; handle missing keys gracefully.
3. **Retry Decorator** — Create a `@retry(n)` decorator that retries a function up to `n` times on exception.
4. **File Organizer** — Move files in a directory into sub-folders by extension (`.py`, `.pdf`, `.jpg`, etc.).
5. **Word Frequency HTML** — Count words in a paragraph and generate a minimal HTML bar-chart page.

### ✅ Checkpoint 4
- [ ] Why should you always use `with` when opening files?
- [ ] Explain the difference between `except Exception` and a bare `except:`.
- [ ] What does a regex `?` quantifier mean?

---

## Phase 5 — Advanced (Decorators, Generators & Concurrency)

> **Goal:** Write Pythonic, high-performance code using advanced language features.

### 📖 5.1 Decorators
```python
import functools, time

# Basic decorator
def logger(func):
    @functools.wraps(func)
    def wrapper(*args, **kwargs):
        print(f"Calling {func.__name__}")
        result = func(*args, **kwargs)
        print(f"Done {func.__name__}")
        return result
    return wrapper

# Decorator with arguments
def repeat(n):
    def decorator(func):
        @functools.wraps(func)
        def wrapper(*args, **kwargs):
            for _ in range(n):
                func(*args, **kwargs)
        return wrapper
    return decorator

@repeat(3)
def hello():
    print("Hello!")

# Class-based decorator
class Timer:
    def __init__(self, func):
        functools.update_wrapper(self, func)
        self.func = func
    def __call__(self, *args, **kwargs):
        start = time.perf_counter()
        result = self.func(*args, **kwargs)
        print(f"{self.func.__name__}: {time.perf_counter()-start:.4f}s")
        return result
```

### 📖 5.2 Generators & Iterators
```python
# Generator function
def fibonacci():
    a, b = 0, 1
    while True:
        yield a
        a, b = b, a + b

gen = fibonacci()
first_10 = [next(gen) for _ in range(10)]

# Generator expression (lazy)
squares_gen = (x**2 for x in range(1_000_000))  # no memory spike

# Custom iterator (protocol)
class Countdown:
    def __init__(self, start):
        self.current = start
    def __iter__(self):
        return self
    def __next__(self):
        if self.current <= 0:
            raise StopIteration
        self.current -= 1
        return self.current + 1

# yield from
def flatten(nested):
    for item in nested:
        if isinstance(item, list):
            yield from flatten(item)
        else:
            yield item
```

### 📖 5.3 Comprehensions (All Four)
```python
# List
squares    = [x**2 for x in range(10)]

# Dict
sq_dict    = {x: x**2 for x in range(10)}

# Set
sq_set     = {x**2 for x in range(-5, 6)}     # removes duplicates

# Generator
sq_gen     = (x**2 for x in range(10))         # lazy evaluation
```

### 📖 5.4 Type Hints & Annotations (Python 3.10+)
```python
from typing import Optional, Union, Any
from collections.abc import Callable, Generator, Iterator

def greet(name: str, times: int = 1) -> str:
    return (f"Hello, {name}!\n") * times

def process(items: list[int]) -> dict[int, int]:
    return {x: x**2 for x in items}

# Using | (Union in 3.10+)
def parse(value: str | int | None) -> float:
    return float(value) if value is not None else 0.0
```

### 📖 5.5 Dataclasses
```python
from dataclasses import dataclass, field

@dataclass(order=True, frozen=True)
class Point:
    x: float
    y: float

    def distance_to_origin(self) -> float:
        return (self.x**2 + self.y**2) ** 0.5

@dataclass
class Student:
    name: str
    grades: list[int] = field(default_factory=list)

    @property
    def average(self) -> float:
        return sum(self.grades) / len(self.grades) if self.grades else 0.0
```

### 📖 5.6 Concurrency

#### Threading
```python
import threading

def download(url):
    print(f"Downloading {url}")   # simulate I/O

threads = [threading.Thread(target=download, args=(url,)) for url in urls]
for t in threads: t.start()
for t in threads: t.join()
```

#### Multiprocessing
```python
from multiprocessing import Pool

def square(n):
    return n * n

with Pool(processes=4) as pool:
    results = pool.map(square, range(100))
```

#### Asyncio (async/await)
```python
import asyncio

async def fetch(url: str) -> str:
    await asyncio.sleep(1)          # simulates async I/O
    return f"Data from {url}"

async def main():
    urls = ["url1", "url2", "url3"]
    results = await asyncio.gather(*[fetch(u) for u in urls])
    print(results)

asyncio.run(main())
```

### 📖 5.7 Functional Programming Extras
```python
from functools import lru_cache, partial, reduce

# Memoization
@lru_cache(maxsize=None)
def fib(n: int) -> int:
    if n < 2: return n
    return fib(n-1) + fib(n-2)

# Partial application
double = partial(lambda x, n: x * n, n=2)

# Compose functions
def compose(*fns):
    return reduce(lambda f, g: lambda x: f(g(x)), fns)

add1   = lambda x: x + 1
times3 = lambda x: x * 3
add1_then_times3 = compose(times3, add1)
print(add1_then_times3(4))   # (4+1)*3 = 15
```

### 💻 Coding Exercises — Phase 5
1. Write a `@memoize` decorator that caches function results.
2. Create an infinite generator that yields primes.
3. Implement your own `map()` and `filter()` as generators.
4. Flatten an arbitrarily nested list using `yield from`.
5. Write an async web scraper skeleton using `asyncio` + `aiohttp`.
6. Implement a thread-safe counter using `threading.Lock`.

### 🧩 Challenges — Phase 5
1. **Pipeline** — Build a data-processing pipeline using generators (read CSV → filter → transform → write).
2. **Rate Limiter** — Decorator that limits how many times a function can be called per second.
3. **Lazy Evaluation** — Implement a lazy list class that evaluates elements on demand.
4. **Async Chat** — Simple async TCP echo server using `asyncio.start_server`.
5. **Parallel Image Processing** — Use `multiprocessing.Pool` to resize a folder of images concurrently.

### ✅ Checkpoint 5
- [ ] What is the GIL and how does it affect threading vs multiprocessing?
- [ ] Explain `yield` vs `yield from`.
- [ ] When would you choose `asyncio` over threading?

---

## Phase 6 — Expert (Internals, Packaging & Performance)

> **Goal:** Understand CPython internals, publish packages, profile and optimise code.

### 📖 6.1 CPython Internals (Overview)
- **GIL (Global Interpreter Lock):** Only one thread executes Python bytecode at a time; I/O-bound tasks benefit from threading; CPU-bound tasks need multiprocessing.
- **Reference counting + cyclic GC:** Objects are freed when refcount reaches 0; `gc` module handles cycles.
- **Bytecode:** Python source → `.pyc` bytecode (view with `dis` module).
```python
import dis
def add(a, b): return a + b
dis.dis(add)
```
- **Memory model:** Everything is an object; integers -5 to 256 are interned (cached).

### 📖 6.2 Metaclasses
```python
# A metaclass controls class creation
class SingletonMeta(type):
    _instances = {}
    def __call__(cls, *args, **kwargs):
        if cls not in cls._instances:
            cls._instances[cls] = super().__call__(*args, **kwargs)
        return cls._instances[cls]

class Database(metaclass=SingletonMeta):
    def __init__(self, url): self.url = url
```

### 📖 6.3 Descriptors
```python
class Validator:
    """Descriptor that validates numeric ranges."""
    def __set_name__(self, owner, name):
        self.name = name

    def __get__(self, obj, objtype=None):
        if obj is None: return self
        return obj.__dict__.get(self.name)

    def __set__(self, obj, value):
        if not isinstance(value, (int, float)):
            raise TypeError(f"{self.name} must be numeric")
        obj.__dict__[self.name] = value

class Circle:
    radius = Validator()
    def __init__(self, r): self.radius = r
```

### 📖 6.4 Profiling & Optimization
```python
# cProfile
import cProfile
cProfile.run("my_function()")

# timeit
import timeit
timeit.timeit("'-'.join(str(n) for n in range(100))", number=10_000)

# Line profiler (pip install line_profiler)
# memory_profiler (pip install memory_profiler)

# Useful tricks
# 1. Prefer list comprehensions over for-loops for speed
# 2. Use local variable references inside tight loops
# 3. Use slots for memory-critical classes
class Point:
    __slots__ = ("x", "y")
    def __init__(self, x, y): self.x, self.y = x, y
```

### 📖 6.5 Packaging & Distribution
```
my_package/
├── src/
│   └── my_package/
│       ├── __init__.py
│       └── core.py
├── tests/
│   └── test_core.py
├── pyproject.toml
├── README.md
└── LICENSE
```

`pyproject.toml` (minimal):
```toml
[build-system]
requires = ["hatchling"]
build-backend = "hatchling.build"

[project]
name = "my-package"
version = "0.1.0"
description = "A short description"
requires-python = ">=3.10"
dependencies = []
```

```bash
pip install build twine
python -m build            # creates dist/
twine upload dist/*        # publish to PyPI
```

### 📖 6.6 Testing with pytest
```python
# tests/test_math.py
import pytest
from my_package.core import add, divide

def test_add():
    assert add(2, 3) == 5

def test_add_floats():
    assert add(0.1, 0.2) == pytest.approx(0.3)

def test_divide_by_zero():
    with pytest.raises(ZeroDivisionError):
        divide(1, 0)

@pytest.mark.parametrize("a,b,expected", [
    (1, 2, 3), (0, 0, 0), (-1, 1, 0)
])
def test_add_parametrized(a, b, expected):
    assert add(a, b) == expected
```

### 💻 Coding Exercises — Phase 6
1. Use `dis` to compare the bytecode of `x += 1` vs `x = x + 1`.
2. Implement a descriptor that enforces type checking for class attributes.
3. Profile a matrix multiplication loop; optimise it with `numpy`.
4. Write a `pytest` test suite for a `BankAccount` class covering all edge cases.
5. Package a utility library and install it locally with `pip install -e .`.

### 🧩 Challenges — Phase 6
1. **Mini ORM** — Build a simple SQLite ORM with `__init_subclass__` for table mapping.
2. **Plugin System** — Use `importlib` to dynamically load plugins from a directory.
3. **C Extension** — Write a simple C extension with `ctypes` or `cffi`.
4. **Async Queue Worker** — Build a job queue using `asyncio.Queue` and multiple worker coroutines.
5. **Bytecode Hacker** — Modify function bytecode at runtime to add logging without decorators.

### ✅ Checkpoint 6
- [ ] What is the difference between `__new__` and `__init__`?
- [ ] Explain how `__slots__` saves memory.
- [ ] How does `lru_cache` work internally?

---

## Domain Tracks

After completing all six phases, choose one or more domain tracks.

### 🌐 Web Development
| Technology | Purpose |
|-----------|---------|
| **Flask** | Micro web framework; REST APIs |
| **FastAPI** | Modern async REST APIs with auto OpenAPI docs |
| **Django** | Full-stack batteries-included framework |
| **SQLAlchemy** | ORM & DB toolkit |
| **Pydantic** | Data validation with type hints |

**Key topics:** routing, templating (Jinja2), authentication (JWT/OAuth), databases (PostgreSQL/SQLite), Docker deployment.

### 🤖 Data Science & Machine Learning
| Library | Purpose |
|---------|---------|
| **NumPy** | N-dimensional arrays, linear algebra |
| **Pandas** | DataFrames, data wrangling |
| **Matplotlib / Seaborn** | Visualisation |
| **Scikit-learn** | Classical ML algorithms |
| **TensorFlow / PyTorch** | Deep learning |

**Key topics:** EDA, feature engineering, model training, hyperparameter tuning, model deployment.

### 🔧 DevOps / Scripting / Automation
| Tool | Purpose |
|------|---------|
| **paramiko** | SSH automation |
| **fabric** | Remote command execution |
| **Ansible** (Python-based) | Infrastructure automation |
| **Docker SDK** | Container management via Python |
| **Airflow** | Workflow orchestration |

### 🔒 Cybersecurity
| Library | Purpose |
|---------|---------|
| **scapy** | Packet manipulation |
| **cryptography** | Cryptographic recipes |
| **hashlib** | Hashing (SHA, MD5) |
| **socket** | Low-level networking |

---

## Practice Projects — All Levels

### 🟢 Beginner Projects
| # | Project | Key Concepts |
|---|---------|-------------|
| 1 | **Calculator** | Functions, input/output, conditionals |
| 2 | **Number Guessing Game** | Loops, random, input validation |
| 3 | **Simple To-Do List** (CLI) | Lists, file I/O, loops |
| 4 | **Temperature Converter** | Functions, arithmetic |
| 5 | **Rock Paper Scissors** | Conditionals, random, loops |
| 6 | **BMI Calculator** | Input, arithmetic, conditionals |
| 7 | **Simple Quiz App** | Dictionaries, loops, scoring |
| 8 | **Password Strength Checker** | Strings, re module |
| 9 | **Multiplication Table Generator** | Nested loops, formatting |
| 10 | **Contact Book** (JSON persistence) | Dictionaries, JSON, file I/O |

### 🟡 Intermediate Projects
| # | Project | Key Concepts |
|---|---------|-------------|
| 11 | **Student Grade Management System** | OOP, file I/O, sorting |
| 12 | **Bank Management System** | OOP, exceptions, classes |
| 13 | **Library Management System** | OOP, inheritance, JSON |
| 14 | **Text-Based Adventure Game** | OOP, game loop, classes |
| 15 | **Web Scraper** (BeautifulSoup) | HTTP, parsing, CSV/JSON output |
| 16 | **Weather CLI App** (OpenWeatherMap API) | HTTP, JSON, API keys |
| 17 | **Expense Tracker** | OOP, CSV, matplotlib charts |
| 18 | **URL Shortener** | Dictionaries, JSON, file I/O |
| 19 | **Markdown to HTML Converter** | re, string processing |
| 20 | **File Organizer** | os, pathlib, shutil |

### 🔴 Advanced Projects
| # | Project | Key Concepts |
|---|---------|-------------|
| 21 | **REST API** (Flask/FastAPI) | HTTP, routing, JSON, authentication |
| 22 | **Real-Time Chat App** | asyncio, WebSockets |
| 23 | **Automated Stock Price Alert** | API, threading, email (smtplib) |
| 24 | **Image Recognition App** | Keras/PyTorch, CNN |
| 25 | **Personal Finance Dashboard** | Pandas, Matplotlib, Flask |
| 26 | **Command-Line Database** | SQLite, argparse |
| 27 | **Web Crawler with Robots.txt Respect** | asyncio, aiohttp, HTML parsing |
| 28 | **Code Formatter Tool** | AST, tokenize |
| 29 | **Mini Docker Clone** | os, subprocess, namespaces |
| 30 | **Distributed Task Queue** | Redis, asyncio, multiprocessing |

---

## Mock Interview Questions

### 🟢 Easy
1. What are mutable vs immutable types in Python? Give examples.
2. Explain the difference between `deepcopy` and `shallowcopy`.
3. What is list slicing? What does `lst[::-1]` do?
4. What are *args and **kwargs?
5. How does Python handle memory management?
6. What is a lambda function? When would you use it?
7. Difference between `append()` and `extend()` on a list?
8. What is the difference between `range()` and `xrange()`? (Python 2 vs 3)
9. How do you read a file line by line efficiently?
10. What does `if __name__ == "__main__":` do?

### 🟡 Medium
1. How does Python's GIL affect multi-threaded programs?
2. Explain the MRO (Method Resolution Order) in Python's multiple inheritance.
3. What are generators and how are they different from iterators?
4. What is a decorator? Write one from scratch.
5. What is the difference between `@classmethod` and `@staticmethod`?
6. Explain `__slots__` and when you'd use it.
7. How does `functools.lru_cache` work?
8. What is the `with` statement and how do you create a custom context manager?
9. How does Python's `sorted()` compare to list's `.sort()`?
10. Explain coroutines vs threads for concurrency.

### 🔴 Hard
1. Explain CPython reference counting and cyclic garbage collection.
2. Implement a thread-safe singleton without using a library.
3. How does `asyncio` work under the hood (event loop, coroutines, tasks, futures)?
4. What is a metaclass? When would you use one?
5. Describe how Python descriptors work (`__get__`, `__set__`, `__delete__`).
6. How does Python's `import` system work? What is `sys.modules`?
7. Explain the C-level implementation of Python's `dict` (hash table, open addressing).
8. How do you detect and fix memory leaks in a Python application?
9. What are `__init_subclass__` and `__class_getitem__`?
10. Design a LRU Cache class using `OrderedDict` in O(1) time for both get and put.

---

## Resources & References

### 📚 Books
| Title | Author | Level |
|-------|--------|-------|
| *Python Crash Course* | Eric Matthes | Beginner |
| *Automate the Boring Stuff with Python* | Al Sweigart | Beginner |
| *Learning Python* | Mark Lutz | Beginner–Intermediate |
| *Fluent Python* | Luciano Ramalho | Intermediate–Advanced |
| *Python Cookbook* | David Beazley & Brian K. Jones | Advanced |
| *High Performance Python* | Micha Gorelick & Ian Ozsvald | Expert |
| *Architecture Patterns with Python* | Percival & Gregory | Expert |

### 🌐 Online Resources
| Resource | URL | Level |
|----------|-----|-------|
| Official Python Docs | python.org/doc | All |
| Real Python | realpython.com | All |
| Python Tutor (visualiser) | pythontutor.com | Beginner |
| LeetCode (Python tag) | leetcode.com | All |
| HackerRank Python Track | hackerrank.com | Beginner–Intermediate |
| Codewars | codewars.com | All |
| Talk Python to Me (podcast) | talkpython.fm | All |
| PyMOTW-3 (stdlib tour) | pymotw.com/3 | Intermediate |

### 🎥 Video Courses
- **CS Dojo** — Python for Beginners (YouTube)
- **Corey Schafer** — Python Tutorials (YouTube)
- **Tech With Tim** — Python Projects (YouTube)
- **sentdex** — Python Machine Learning (YouTube)
- **MIT 6.0001** — Introduction to CS and Programming in Python (OCW)

---

## 📅 Suggested Learning Schedule

| Week | Phase | Daily Time |
|------|-------|-----------|
| 1–2 | Phase 1 (Basics) | 1–2 hours |
| 3–4 | Phase 2 (Core Structures) | 1–2 hours |
| 5–7 | Phase 3 (OOP & Modules) | 2 hours |
| 8–9 | Phase 4 (Files, Errors) | 2 hours |
| 10–12 | Phase 5 (Advanced Features) | 2–3 hours |
| 13–16 | Phase 6 (Expert Topics) | 2–3 hours |
| 17+ | Domain Track + Projects | 3+ hours |

> **Tip:** Solve at least **one coding problem per day** on LeetCode/HackerRank throughout all phases.

---

<div align="center">
  <b>🚀 Happy Coding — Built with ❤️ by Antriksh Yadav</b><br>
  <a href="https://github.com/AntrikshH90">GitHub</a> · 
  <a href="https://linkedin.com/in/antriksh97">LinkedIn</a>
</div>
