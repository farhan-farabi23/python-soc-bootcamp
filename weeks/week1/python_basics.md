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

*** Below listed variable names are valid: *** 
```
age = 21
_colour = "lilac"
total_score = 90
```
***Below listed variables names are invalid:**
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
*** 1. Basic Assignment: Variables are assigned values using the = operator. ***
```
x = 5
y = 3.14
z = "Hi"
```
*** 2. Dynamic Typing: Python is dynamically typed, so the same variable can store different data types during execution. ***
```
x = 10
x = "Now a string"
```
*** 3. Assigning Same Value: same value can be assigned to multiple variables in a single line. ***
```
a = b = c = 100
print(a, b, c)

Output :
100 100 100
```
*** 4. Assigning Different Values: Multiple variables can also be assigned different values in a single line. ***
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

