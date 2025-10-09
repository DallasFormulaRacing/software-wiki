# Best Development Practices

This document aims to outline the best practices to follow when contributing to any DFR Software project. 

Many of the practices outlined here are based upon industry standards, and should be applied across any of the projects that you work on both within DFR and on any outside work. (generally)

Also noted, many of these practices are not strictly required, everyone has their own style and way of programming and working. The guidelines that should be strictly followed are marked with a <span style="color: #E97600;"><b>*</b></span> in their section heading.

Most of this should be easy to follow and practically second nature after a bit of practice. So while it might seem like a lot, it should become second nature in no time.

## Code quality

Maintaining consistent code quality is critical for long term support and maintainability of any project.

### Clean code <span style="color: #E97600;"><b>*</b></span>

Maintaining clean code, that is not only readable, but easily understandable is a major priority for DFR.

#### Naming conventions <span style="color: #E97600;"><b>*</b></span>

Variables, functions, classes, and other identifiers should be named clear and concise. Avoid utilizing lengthy names, and instead aim for names that are descriptive yet succinct.

**Examples**

```python
# Proper naming convention

def calculate_area(radius):
    return 3.14 * radius * radius
```

```python
# Poor naming convention

def ca(r):
    return 3.14 * r * r
```

#### The single responsibility principle <span style="color: #E97600;"><b>*</b></span>

The single responsibility principle states that a function, class, or module should only have one primary function or responsibility. This means that each component of a program should be focused on a single task, making it easier to understand and maintain.

**Examples**

```python
# Proper implementation of the single responsibility principle

def calculate_area(radius):
    return 3.14 * radius * radius

def calculate_circumference(radius):
    return 2 * 3.14 * radius
```

```python
# Poor implementation of the single responsibility principle

def calculate_area_and_circumference(radius):
    area = 3.14 * radius * radius
    circumference = 2 * 3.14 * radius
    return area, circumference
```

#### The DRY principle <span style="color: #E97600;"><b>*</b></span>

The DRY (Don't Repeat Yourself) principle is a method of development intended to both make file structure and code more efficient. It focuses on reducing the repetition of code blocks, instead favoring the use of functions, classes, and modules, similar to OOP (Object Oriented Programming).

**Examples**

```python
# Proper implementation of the DRY principle

def create_circle(radius):
    return {
        "area": 3.14 * radius * radius,
        "circumference": 2 * 3.14 * radius
    }

circle1 = create_circle(5)
circle2 = create_circle(10)
circle3 = create_circle(15)
```

```python
# Poor implementation of the DRY principle

circle1 = {
    "area": 3.14 * 5 * 5,
    "circumference": 2 * 3.14 * 5
}

circle2 = {
    "area": 3.14 * 10 * 10,
    "circumference": 2 * 3.14 * 10
}

circle3 = {
    "area": 3.14 * 15 * 15,
    "circumference": 2 * 3.14 * 15
}
```

#### Consistent formatting <span style="color: #E97600;"><b>*</b></span>

Having consistent formatting across a codebase is essential for maintainability and readability. This includes consistent casing, line breaks, and indentation.

---

##### Casing <span style="color: #E97600;"><b>*</b></span>

Consistent casing is a must. You are welcome to chose your preferred casing style, but it must be consistent across the entire codebase of a project. Meaning that if you have started work on an existing project that uses [snake_case](https://en.wikipedia.org/wiki/Snake_case), you should continue to use [snake_case](https://en.wikipedia.org/wiki/Snake_case).

[snake_case](https://en.wikipedia.org/wiki/Snake_case) is the most "[pythonic](https://peps.python.org/pep-0008/)" casing style, and will be the preferred casing style for any new projects.

**Examples**

```python
# Proper casing
def calculate_area(radius):
    return 3.14 * radius * radius

def calculate_circumference(radius):
    return 2 * 3.14 * radius
```

```python
# Poor casing
def CalculateArea(radius):
    return 3.14 * radius * radius

def calculate_circumference(radius):
    return 2 * 3.14 * radius
```

---

##### Line breaks <span style="color: #E97600;"><b>*</b></span>

Line breaks should be used to improve the readability of code. This includes breaking up long lines of code, and adding blank lines between functions and classes.

Between functions and classes, there should be a double line break, and within a function or class there should be a single blank line between logic statements, loops, conditionals, and unrelated variables.

**Examples**

```python
# Proper use of line breaks

from math import pi

radius = 5
area = None

def calculate_area(radius):
    if radius < 0:
        return 0

    return pi * radius * radius

area = calculate_area(radius)
```

```python
# Poor use of line breaks

from math import pi

radius = 5

area = None

def calculate_area(radius):
    if radius < 0:
        return 0
    return pi * radius * radius
area = calculate_area(radius)
```

---

##### Indentation

As long as the code runs, and is readable, the specific indentation style is not important. It is however important that comments are indented to the same level as the code they are referencing, along with any data structures that you might explode for visibility.

**Examples**

```python
# Proper indentation

def create_circle(radius):
    # returns a dict with area and circumference of a circle
    return {
        "area": 3.14 * radius * radius,
        "circumference": 2 * 3.14 * radius
    }
```

```python
# Poor indentation

def create_circle(radius):
# returns a dict with area and circumference of a circle
    return {
    "area": 3.14 * radius * radius,
    "circumference": 2 * 3.14 * radius
    }
```

---

#### Code comments

Code comments aren't specifically required, as if you follow the above guidelines your code should already be readable and self explanatory. However, comments may still prove useful and thus are encouraged.

Proper comments should explain the specific function of a single line of code in a way that is clear and concise. You should avoid sweeping comments that cover large blocks of code, as they tend to me more confusing than actually helpful.

**Examples**

```python
# Proper use of code comments

def create_circle(radius):
    # Calculates area and circumference of a 
    # circle and returns them in a dictionary
    return {
        "area": 3.14 * radius * radius,
        "circumference": 2 * 3.14 * radius
    }
```

```python
# Poor use of code comments

# This func returns a dict with a circle
def create_circle(radius):
    return {
        "area": 3.14 * radius * radius,
        "circumference": 2 * 3.14 * radius
    }
```

# His fatass fr fr

[![](https://cdn.discordapp.com/attachments/886290995627573269/1425966552351637544/image.png?ex=68e98257&is=68e830d7&hm=8530e14fcfd4e28e6dba589f939a5080507e03bd244addbf379f6f4cd5e50ffa&)](https://media.tenor.com/HwkyC4TKeyUAAAAe/doge-smile-smile.png)