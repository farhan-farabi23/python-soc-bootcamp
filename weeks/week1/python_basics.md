# 🐍 Python Basics — Week 1 Notes

## 1. Python Introduction

**What is Python?**
Python is a high-level, interpreted, and object-oriented programming language created by **Guido van Rossum** and released in **1991**. It is one of the most popular programming languages in the world.

**Why Use Python?**
- Simple syntax similar to the English language — easy to read and write
- Fewer lines of code compared to many other languages
- Works on different platforms: Windows, Mac, Linux, Raspberry Pi
- Runs on an interpreter — code executes as soon as it is written (great for quick prototyping)
- Massive library support — you rarely need to build everything from scratch
- Used in web development, automation, data analysis, AI, cybersecurity, and more

```python
# Your first Python program
print("Hello, World!")

Output:
Hello, World!
```

> **For cybersecurity:** Python is the #1 scripting language for SOC analysts, penetration testers, and security automation.

---

## 2. Python Syntax & Indentation

Python syntax refers to the set of rules that define how Python code must be written so the interpreter can understand it.

**Key Rules:**
- Python uses **indentation** (spaces at the start of a line) to define code blocks — NOT curly braces `{}`
- Standard indentation is **4 spaces** (PEP 8 style guide)
- Statements with the same indentation belong to the same block
- Mixing tabs and spaces causes an `IndentationError`

```python
# Correct indentation
if 5 > 2:
    print("Five is greater than two!")

Output:
Five is greater than two!
```

```python
# Wrong indentation — this will cause an error
if 5 > 2:
print("Error!")   # IndentationError
```

> **Remember:** In Python, indentation is not just style — it is part of the language syntax.

---

## 3. Python Output — `print()`

The `print()` function displays output to the screen (standard output device).

**Basic Usage:**
```python
print("Hello, Farhan!")

Output:
Hello, Farhan!
```

**Printing Variables:**
```python
name = "Farhan"
age = 23
print(name)
print(age)

Output:
Farhan
23
```

**Key Parameters of `print()`:**

| Parameter | Default | Purpose |
|-----------|---------|---------|
| `sep`     | `' '`   | Separator between multiple values |
| `end`     | `'\n'`  | What to print at the end (newline by default) |

```python
# Using sep and end
print("Python", "is", "awesome", sep="-")
print("Hello", end=" ")
print("World")

Output:
Python-is-awesome
Hello World
```

**Printing Multiple Items:**
```python
x = 5
y = "Farhan"
print(x, y)           # Comma separates with a space

Output:
5 Farhan
```

---

## 4. Python Comments

Comments are lines that Python ignores during execution. They are used to explain code.

### Single-Line Comments
Use the `#` symbol. Everything after `#` on that line is a comment.

```python
# This is a comment
print("Hello!")   # This is an inline comment
```

### Multi-Line Comments
Python has no official multi-line comment syntax. Two common approaches:

**Approach 1 — Multiple `#` lines:**
```python
# This is line 1 of the comment
# This is line 2 of the comment
# This is line 3 of the comment
```

**Approach 2 — Triple quotes (not assigned to a variable):**
```python
"""
This is a multi-line comment.
Python reads it but ignores it
since it is not assigned to any variable.
"""
print("Comments don't affect output")
```

> **Tip:** Use `'''triple single quotes'''` or `"""triple double quotes"""` — both work the same way.

---

## 5. Variables

Variables are used to store data that can be referenced and manipulated during program execution. A variable is essentially a name that is assigned to a value.
- Unlike Java and many other languages, Python variables do not require explicit declaration of type.
- Type of the variable is inferred based on the value assigned.


```
x = 5
name = "Farabi"  
print(x)
print(name)

Output : 
5
Farabi
```

### Rules for Naming Variables
To use variables correctly, the following naming rules should be followed
- Names can contain letters, digits and underscores (_).
- The first character cannot be a digit.
- Names are case-sensitive, so myVar and myvar are treated differently.
- Keywords such as if, else and for cannot be used as variable names.

**Below listed variable names are valid:** 
```
age = 21
_colour = "lilac"
total_score = 90
```
**Below listed variables names are invalid:**
```
1name = "Error"  # Starts with a digit
class = 10       # class is a reserved keyword
user-name = "Farabi"  # Contains a hyphen
```
### Output Variables
The *print()* function is often used to output variables.
```
x = "Farhan Rahman Farabi"
print(x)

Output : 
Farhan Rahman Farabi
```
-You can also use the **+** operator to output multiple variables:
```
a = "Farhan "
b = "Rahman "
c = "Farabi"
print(a + b + c)

Output :
Farhan Rahman Farabi
```
-In the *print()* function, when you try to combine a string and a number with the + operator, Python will give you an error:
```
x = 5
y = " Farhan"
print(x + y)

Output :
TypeError: unsupported operand type(s) for +: 'int' and 'str'
```
-The best way to output multiple variables in the print() function is to separate them with commas, which even support different data types:
```
x = 5
y = "Farhan"
print(x , y)

Output :
5 Farhan
```

### Assigning Values to Variables
**1. Basic Assignment: Variables are assigned values using the = operator.**
```
x = 5
y = 3.14
z = "Hi"
```
**2. Dynamic Typing: Python is dynamically typed, so the same variable can store different data types during execution.**
```
x = 10
x = "Now a string"
```
**3. Assigning Same Value: same value can be assigned to multiple variables in a single line.**
```
a = b = c = 100
print(a, b, c)

Output :
100 100 100
```
**4. Assigning Different Values: Multiple variables can also be assigned different values in a single line.**
```
x, y, z = 1, 2.5, "Python"
print(x, y, z)

Output :
1 2.5 Python
```

### Unpack a Collection
If you have a collection of values in a [list], (tuple) etc. Python allows you to extract the values into variables. This is called unpacking.

```
fruits = ["apple", "banana", "cherry"]
x, y, z = fruits
print(x)
print(y)
print(z)

Output :
apple
banana
cherry
```

#### Object Reference
Let us assign a variable x to value 5.
`x = 5
When x = 5 is executed, Python creates an object to represent the value 5 and makes x reference this object.
`X = 5
Now, let's assign another variable y to the variable x.
`y = x
This statement creates y and references the same object as x, not x itself. This is called a ***Shared Reference***, where multiple variables reference the same object.
`x = 5 = y
Now, if we write
`x = 'Farhan'
Python creates a new object for the value "Farhan" and makes x reference this new object.
```
y = 5
x = Farhan
```
The variable y remains unchanged, still referencing the original object 5. Now, If we assign a new value to y:
`y = "Computer"
```
5 (Garbage)
```
```
x = Farhan
y = Computer
```
Python variables store references to objects, not the actual values themselves. When a variable is reassigned, it starts referencing a new object while the old unreferenced object becomes eligible for garbage collection.

### Variable Reassignment
Here we check whether modifying one variable affects another when both initially reference the same object.
```
x = 1
y = x
y = y + 1
​
print(x)
print(y)

Output:
1
2
```
- Initially, both x and y reference the object 1.
- After y = y + 1, y references a new object 2 while x still references 1, so changing y does not affect x.

### Deleting a Variable
*del* keyword is used to delete a variable from memory. After deletion, the variable can no longer be accessed.
```
x = 10
del x
print(x) 

Output :

ERROR!
Traceback (most recent call last):
  File "<main.py>", line 3, in <module>
NameError: name 'x' is not defined
```
*Explanation:* del x deletes the variable x. Accessing x after deletion raises a NameError because the variable no longer exists.

### Global and Local Variables

Variables store data in memory and scope defines the specific region of a program where a variable is accessible. It dictates the visibility and lifetime of the variable within the source code. Variables are categorized into two primary scopes: Global and Local.

**Local Variables**
Local variables are defined inside a function and exist only during its execution. They cannot be accessed from outside the function.

```
def greet():
    msg = "This is Local Variable"
    print(msg)

greet()

Output : 
This is Local Variable
```
**Global Variables**
Variables that are created outside of a function (as in all of the examples in the previous pages) are known as global variables.

Global variables can be used by everyone, both inside of functions and outside.
```
x = "Farabi"
print(x)

def myfunc():
  print("Farhan Rahman " + x)

myfunc()

Output : 
Farabi
Farhan Rahman Farabi
```

**Global Keyword**
When you create a variable inside a function, that variable is local, and can only be used inside that function.

To create a global variable inside a function, you can use the global keyword.

```
def myfunc():
  global x
  x = "fantastic"

myfunc()

print("Python is " + x)

Output :
Python is fantastic
```

---

## 6. Python Data Types

In programming, data types tell Python what kind of value a variable holds. Python has several built-in data types.

| Category | Data Type | Example |
|----------|-----------|---------|
| Text | `str` | `"Hello"` |
| Numeric | `int`, `float`, `complex` | `5`, `3.14`, `2+3j` |
| Boolean | `bool` | `True`, `False` |
| Sequence | `list`, `tuple`, `range` | `[1,2,3]`, `(1,2)` |
| Mapping | `dict` | `{"key": "value"}` |
| Set | `set`, `frozenset` | `{1, 2, 3}` |
| None | `NoneType` | `None` |

**Checking the type of a variable — use `type()`:**
```python
x = 5
y = "Hello"
z = 3.14

print(type(x))   # <class 'int'>
print(type(y))   # <class 'str'>
print(type(z))   # <class 'float'>
```

**Setting a specific data type:**
```python
x = str("Hello")     # str
x = int(5)           # int
x = float(3.14)      # float
x = bool(True)       # bool
```

---

## 7. Python Numbers

There are **three numeric types** in Python: `int`, `float`, and `complex`.

### Integer (`int`)
Whole numbers — positive or negative — with no decimal point. No size limit in Python.

```python
x = 10
y = -500
z = 1000000000

print(type(x))   # <class 'int'>
```

### Float (`float`)
Numbers with a decimal point, positive or negative.

```python
x = 3.14
y = -0.5
z = 1.5e4    # Scientific notation: 1.5 × 10^4 = 15000.0

print(type(x))   # <class 'float'>
```

### Complex (`complex`)
Numbers with a real part and an imaginary part written with `j`.

```python
x = 2 + 3j
y = 5j

print(type(x))   # <class 'complex'>
print(x.real)    # 2.0  (real part)
print(x.imag)    # 3.0  (imaginary part)
```

### Converting Between Number Types
```python
a = 5        # int
b = float(a) # → 5.0
c = int(3.9) # → 3  (decimal is removed, NOT rounded)
d = complex(2) # → (2+0j)

print(b, c, d)

Output:
5.0  3  (2+0j)
```

---

## 8. Python Casting (Type Conversion)

**Casting** means converting one data type into another. Python supports two kinds:

### Implicit Conversion (Automatic)
Python automatically converts types when needed — usually from smaller to larger type to avoid data loss.

```python
x = 5      # int
y = 2.5    # float
result = x + y

print(result)        # 7.5
print(type(result))  # <class 'float'>
```

### Explicit Conversion (Manual Casting)
You manually convert using built-in functions.

| Function | Converts to | Example |
|----------|------------|---------|
| `int()`  | Integer | `int(3.9)` → `3` |
| `float()` | Float | `float(5)` → `5.0` |
| `str()`  | String | `str(100)` → `"100"` |
| `bool()` | Boolean | `bool(0)` → `False` |

```python
# int() — converts float or string to integer
x = int(3.9)      # → 3  (truncates, does NOT round)
y = int("15")     # → 15

# float() — converts int or string to float
a = float(5)      # → 5.0
b = float("3.14") # → 3.14

# str() — converts number to string
s = str(100)      # → "100"
t = str(3.14)     # → "3.14"
```

> **Important:** `int("hello")` will raise a `ValueError` — you can only cast a string to int if the string actually contains a number.

---

## 9. Python Strings

A string is a sequence of characters enclosed in single `'...'`, double `"..."`, or triple `'''...'''` / `"""..."""` quotes.

### Creating Strings
```python
s1 = 'Hello'
s2 = "World"
s3 = """This is
a multi-line string"""

print(s1)
print(s2)
print(s3)
```

### String Indexing
Each character in a string has an index. Positive indices start at `0` from the left; negative indices start at `-1` from the right.

```
 H  e  l  l  o
 0  1  2  3  4      ← Positive index
-5 -4 -3 -2 -1      ← Negative index
```

```python
name = "Farhan"
print(name[0])    # F
print(name[-1])   # n
print(name[2])    # r
```

### String Slicing
Extract a substring using `string[start:end:step]`. The `end` index is **not included**.

```python
name = "Farhan"
print(name[0:3])    # Far      (index 0, 1, 2)
print(name[2:])     # rhan     (from index 2 to end)
print(name[:3])     # Far      (from start to index 2)
print(name[-3:])    # han      (last 3 characters)
print(name[::-1])   # nahraF   (reversed string)
```

### String Concatenation
```python
first = "Farhan "
last  = "Farabi"

full = first + last        # Using + operator
print(full)                # Farhan Farabi

# f-strings (modern, recommended way)
age = 23
print(f"My name is {first}and I am {age} years old.")

Output:
Farhan Farabi
My name is Farhan and I am 23 years old.
```

### String Length
```python
name = "Farhan"
print(len(name))   # 6
```

---

## 10. Python String Methods

Python has many built-in methods for working with strings. These do **not** change the original string — they return a new one.

| Method | Description | Example |
|--------|-------------|---------|
| `upper()` | Converts to uppercase | `"hello".upper()` → `"HELLO"` |
| `lower()` | Converts to lowercase | `"HELLO".lower()` → `"hello"` |
| `strip()` | Removes leading/trailing whitespace | `"  hi  ".strip()` → `"hi"` |
| `replace()` | Replaces a substring | `"Hello".replace("H","J")` → `"Jello"` |
| `split()` | Splits into a list | `"a,b,c".split(",")` → `["a","b","c"]` |
| `find()` | Returns index of first match | `"Hello".find("l")` → `2` |
| `count()` | Counts occurrences | `"banana".count("a")` → `3` |
| `startswith()` | Checks start of string | `"Hello".startswith("He")` → `True` |
| `endswith()` | Checks end of string | `"Hello".endswith("lo")` → `True` |
| `join()` | Joins list into a string | `"-".join(["a","b","c"])` → `"a-b-c"` |

**Examples:**
```python
text = "  Hello, Farhan!  "

print(text.strip())            # "Hello, Farhan!"
print(text.lower())            # "  hello, farhan!  "
print(text.upper())            # "  HELLO, FARHAN!  "
print(text.replace("Farhan", "World"))  # "  Hello, World!  "

sentence = "Python is fun"
words = sentence.split(" ")
print(words)                   # ['Python', 'is', 'fun']
```

---

## 11. Python Booleans

A Boolean represents one of two values: **`True`** or **`False`**. Note the capital first letter — `true` and `false` are NOT valid in Python.

### Basic Boolean
```python
x = True
y = False

print(type(x))   # <class 'bool'>
```

### Comparison Operators (Return Booleans)

| Operator | Meaning | Example | Result |
|----------|---------|---------|--------|
| `==` | Equal to | `5 == 5` | `True` |
| `!=` | Not equal to | `5 != 3` | `True` |
| `>`  | Greater than | `5 > 3` | `True` |
| `<`  | Less than | `5 < 3` | `False` |
| `>=` | Greater than or equal | `5 >= 5` | `True` |
| `<=` | Less than or equal | `3 <= 5` | `True` |

```python
print(10 > 5)     # True
print(10 == 5)    # False
print(10 != 5)    # True
```

### `bool()` Function
Converts any value to `True` or `False`.

```python
print(bool(1))       # True
print(bool(0))       # False
print(bool(""))      # False  (empty string)
print(bool("Hi"))    # True
print(bool([]))      # False  (empty list)
print(bool([1,2]))   # True
```

### Truthy vs Falsy Values

| Falsy (evaluates to `False`) | Truthy (evaluates to `True`) |
|-----------------------------|------------------------------|
| `0`, `0.0` | Any non-zero number |
| `""` (empty string) | Any non-empty string |
| `[]`, `()`, `{}` | Non-empty collections |
| `None` | Any object |
| `False` | `True` |

```python
# Practical example
name = ""
if name:
    print("Hello,", name)
else:
    print("Name is empty!")   # This runs — empty string is Falsy

Output:
Name is empty!
```

---

## 12. Short Circuit Evaluation

Python uses **short circuit evaluation** with `and` / `or` — it stops evaluating as soon as the result is determined.

### `and` — stops at the first `False`
If the first operand is `False`, Python skips the second entirely.

```python
x = 0
y = 10

print(x and y)    # 0  — x is Falsy, so Python returns x without checking y
print(y and x)    # 0  — y is Truthy, so Python evaluates x and returns it
```

### `or` — stops at the first `True`
If the first operand is `True`, Python skips the second entirely.

```python
x = 5
y = 0

print(x or y)     # 5  — x is Truthy, Python returns x without checking y
print(y or x)     # 5  — y is Falsy, so Python evaluates and returns x
```

### Practical Use
```python
# Safe default value — avoids errors when a variable might be empty
name = ""
display = name or "Guest"
print(display)    # Guest

# Guard check — avoids calling a function if the condition is already False
user_logged_in = False
user_logged_in and load_dashboard()   # load_dashboard() is never called
```

> **Key rule:** `and` returns the first Falsy value (or the last value if all are Truthy). `or` returns the first Truthy value (or the last value if all are Falsy).

---

## 13. Python Lists

A list is an **ordered, mutable** collection that can hold items of any type, including mixed types.

### Creating a List
```python
fruits = ["apple", "banana", "cherry"]
mixed  = [1, "hello", 3.14, True]
empty  = []
```

### Indexing & Slicing
```python
fruits = ["apple", "banana", "cherry"]

print(fruits[0])      # apple
print(fruits[-1])     # cherry
print(fruits[0:2])    # ['apple', 'banana']
```

### Essential List Methods

| Method | Description |
|--------|-------------|
| `append(x)` | Adds `x` to the end |
| `insert(i, x)` | Inserts `x` at index `i` |
| `remove(x)` | Removes the first occurrence of `x` |
| `pop(i)` | Removes & returns item at index `i` (default: last) |
| `sort()` | Sorts the list in place |
| `reverse()` | Reverses the list in place |
| `index(x)` | Returns the index of first occurrence of `x` |
| `count(x)` | Counts how many times `x` appears |
| `clear()` | Removes all items |

```python
nums = [3, 1, 4, 1, 5]

nums.append(9)          # [3, 1, 4, 1, 5, 9]
nums.insert(0, 0)       # [0, 3, 1, 4, 1, 5, 9]
nums.remove(1)          # removes first 1 → [0, 3, 4, 1, 5, 9]
nums.pop()              # removes 9 → [0, 3, 4, 1, 5]
nums.sort()             # [0, 1, 3, 4, 5]
nums.reverse()          # [5, 4, 3, 1, 0]
print(nums.count(1))    # 1
print(nums.index(3))    # 2
```

---

## 14. Python Tuples

A tuple is an **ordered, immutable** collection. Once created, its values cannot be changed.

### Creating a Tuple
```python
coords  = (10, 20)
single  = (42,)          # trailing comma required for single-item tuple
no_paren = 1, 2, 3       # parentheses are optional
```

### Indexing & Slicing
```python
t = ("a", "b", "c", "b")

print(t[0])       # a
print(t[-1])      # b
print(t[1:3])     # ('b', 'c')
```

### Tuple Methods
Tuples only have two built-in methods because they are immutable.

| Method | Description |
|--------|-------------|
| `count(x)` | Counts how many times `x` appears |
| `index(x)` | Returns the index of the first occurrence of `x` |

```python
t = (1, 2, 3, 2, 2)

print(t.count(2))    # 3
print(t.index(3))    # 2
```

> **When to use a tuple over a list:** Use tuples for data that should not change — coordinates, RGB values, function return pairs. They are faster and safer than lists for fixed data.

---

## 15. Python Sets

A set is an **unordered, unindexed** collection with **no duplicate values**. Useful for membership testing and removing duplicates.

### Creating a Set
```python
fruits = {"apple", "banana", "cherry"}
nums   = {1, 2, 2, 3, 3}    # duplicates are removed automatically
print(nums)                  # {1, 2, 3}

empty_set = set()            # NOT {} — that creates an empty dict
```

### Essential Set Methods

| Method | Description |
|--------|-------------|
| `add(x)` | Adds element `x` |
| `remove(x)` | Removes `x` — raises `KeyError` if not found |
| `discard(x)` | Removes `x` — no error if not found |
| `union(s)` | Returns all items from both sets |
| `intersection(s)` | Returns only items in both sets |
| `difference(s)` | Returns items in this set but not in `s` |
| `issubset(s)` | Returns `True` if all items exist in `s` |

```python
a = {1, 2, 3, 4}
b = {3, 4, 5, 6}

a.add(10)                      # {1, 2, 3, 4, 10}
a.discard(10)                  # {1, 2, 3, 4}

print(a.union(b))              # {1, 2, 3, 4, 5, 6}
print(a.intersection(b))       # {3, 4}
print(a.difference(b))         # {1, 2}
print({1, 2}.issubset(a))      # True
```

> **Cybersecurity use:** Sets are great for comparing lists of IPs, finding common/unique entries between logs or scan results.

---

## 16. Python Dictionaries

A dictionary stores data as **key-value pairs**. Keys must be unique and immutable; values can be anything.

### Creating a Dictionary
```python
user = {
    "name": "Farhan",
    "age": 23,
    "role": "SOC Analyst"
}
```

### Accessing & Modifying
```python
print(user["name"])          # Farhan
user["age"] = 24             # update value
user["city"] = "Dhaka"       # add new key
del user["city"]             # delete a key
```

### Essential Dictionary Methods

| Method | Description |
|--------|-------------|
| `get(key)` | Returns value for `key`, or `None` if not found (no error) |
| `keys()` | Returns all keys |
| `values()` | Returns all values |
| `items()` | Returns all key-value pairs as tuples |
| `update(d)` | Merges another dict `d` into this one |
| `pop(key)` | Removes and returns the value for `key` |
| `clear()` | Removes all key-value pairs |

```python
user = {"name": "Farhan", "age": 23, "role": "SOC Analyst"}

print(user.get("name"))         # Farhan
print(user.get("email"))        # None  (no KeyError)

print(user.keys())              # dict_keys(['name', 'age', 'role'])
print(user.values())            # dict_values(['Farhan', 23, 'SOC Analyst'])
print(user.items())             # dict_items([('name', 'Farhan'), ...])

user.update({"age": 24, "city": "Dhaka"})
print(user.pop("city"))         # Dhaka — removed from dict
```

### Looping Through a Dictionary
```python
for key, value in user.items():
    print(f"{key}: {value}")

Output:
name: Farhan
age: 24
role: SOC Analyst
```

---

## 17. Conditional Statements

Conditional statements let Python make decisions — executing different blocks of code based on whether a condition is `True` or `False`.

### `if` Statement
```python
age = 20

if age >= 18:
    print("You are an adult.")

Output:
You are an adult.
```

### `if / else` Statement
```python
age = 15

if age >= 18:
    print("Adult")
else:
    print("Minor")

Output:
Minor
```

### `if / elif / else` Statement
Use `elif` (else if) to check multiple conditions in order. Python stops at the first `True` condition.

```python
score = 75

if score >= 90:
    print("Grade: A")
elif score >= 80:
    print("Grade: B")
elif score >= 70:
    print("Grade: C")
else:
    print("Grade: F")

Output:
Grade: C
```

### Nested `if`
An `if` inside another `if`.

```python
x = 10

if x > 0:
    if x > 5:
        print("x is greater than 5")
    else:
        print("x is between 1 and 5")

Output:
x is greater than 5
```

### Short-Hand `if` (Ternary Operator)
A one-line `if / else` for simple assignments.

```python
age = 20
status = "Adult" if age >= 18 else "Minor"
print(status)    # Adult
```

### Logical Operators in Conditions

| Operator | Meaning | Example |
|----------|---------|---------|
| `and` | Both conditions must be True | `x > 0 and x < 10` |
| `or` | At least one condition must be True | `x < 0 or x > 10` |
| `not` | Reverses the condition | `not x == 5` |

```python
x = 5

if x > 0 and x < 10:
    print("x is a single digit positive number")

Output:
x is a single digit positive number
```

---

## 18. Python Loops

Loops are used to repeatedly execute a block of code.

---

### `for` Loop

A `for` loop iterates over a sequence (list, tuple, string, range, etc.).

```python
fruits = ["apple", "banana", "cherry"]

for fruit in fruits:
    print(fruit)

Output:
apple
banana
cherry
```

**Looping through a string:**
```python
for char in "Python":
    print(char)

Output:
P
y
t
h
o
n
```

**`range()` function** — generates a sequence of numbers.

| Usage | Generates |
|-------|-----------|
| `range(5)` | `0, 1, 2, 3, 4` |
| `range(2, 6)` | `2, 3, 4, 5` |
| `range(0, 10, 2)` | `0, 2, 4, 6, 8` |

```python
for i in range(1, 6):
    print(i)

Output:
1
2
3
4
5
```

---

### `while` Loop

A `while` loop keeps running as long as its condition is `True`.

```python
count = 1

while count <= 5:
    print(count)
    count += 1

Output:
1
2
3
4
5
```

> **Warning:** Always make sure the condition eventually becomes `False`, or the loop will run forever (infinite loop).

---

### Loop Control Statements

| Statement | Description |
|-----------|-------------|
| `break` | Exits the loop immediately |
| `continue` | Skips the rest of the current iteration and moves to the next |
| `pass` | Does nothing — used as a placeholder |

**`break` — exit early:**
```python
for i in range(1, 10):
    if i == 5:
        break
    print(i)

Output:
1
2
3
4
```

**`continue` — skip an iteration:**
```python
for i in range(1, 6):
    if i == 3:
        continue
    print(i)

Output:
1
2
4
5
```

**`pass` — placeholder (no action):**
```python
for i in range(5):
    pass    # loop runs but does nothing — useful while writing code structure
```

---

### Nested Loops
A loop inside another loop. The inner loop completes fully for each iteration of the outer loop.

```python
for i in range(1, 4):
    for j in range(1, 4):
        print(i, j)

Output:
1 1
1 2
1 3
2 1
...
```

---

