# Best Development Practices

This document aims to outline the best practices to follow when contributing to any DFR Software project. 

Many of the practices outlined here are based upon industry standards, and should be applied across any of the projects that you work on both within DFR and on any outside work. (generally)

Also noted, many of these practices are not strictly required, everyone has their own style and way of programming and working. The guidelines that should be strictly followed are marked with a "<span style="color: #E97600;"><b>*</b></span>" in their section heading.

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

#### Sensitive information <span style="color: #E97600;"><b>*</b></span>

!!! danger "NEVER commit sensitive information to a public repository"
    This should go without saying, but you should <span style="color: #E97600;"><b>NEVER</b></span> commit sensitive information to a public repository! This includes API keys, database credentials, client secrets, connection strings, and any information that is not public knowledge.

    There are ways to undo mistaken commits, but that requires rebasing the entire repository, disabling the old credentials / api keys, reissuing new ones, and tracking down every project that needed that credential to function, then updating it. Neither you, nor anyone else, wants, nor should have to do that if you just use environment variables with a proper [.gitignore](#gitignore-files).

Environment variables should <span style="color: #E97600;"><b>ALWAYS</b></span> be used for sensitive information, there is no excuse, even for testing. It is incredibly easy and convenient to hardcode a variable for testing, but it is just as easy to forget to remove it before committing!

For the purposes of DFR this should be done with a `.env` file for local development. These can be loaded into your environment on run via the [python-dotenv](https://pypi.org/project/python-dotenv/) package.

**Example `.env` file**

```env
API_KEY=your_api_key_here
DB_USER=your_db_user_here
DB_PASSWORD=your_db_password_here
```

**Example usage with `python-dotenv`**

```python
from dotenv import load_dotenv
import os

load_dotenv()  # take environment variables from .env.

api_key = os.getenv("API_KEY")
db_user = os.getenv("DB_USER")
db_password = os.getenv("DB_PASSWORD")
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

### `.gitignore` files <span style="color: #E97600;"><b>*</b></span>

`.gitignore` files, as the name implies, are used to specify Git what files and directories to ignore when uploading the project to the remote. This is incredibly useful and important, as it allows us to avoid uploading both unnecessary files, and potentially sensitive information to a public repository.

**Example**

```gitignore
# Byte-compiled / optimized / DLL files
__pycache__/

# Virtual environment
venv/

# Potentially unneeded files and directories
testing/
logs/
*.log
*.tmp

# Sensitive environment files
*.env
```

## Version control and dependency management

Version control and dependency management are critical parts of the software development cycle. Version control, in our case via GitHub, allows multiple developers to work on the same project without clashing with each other's work. Dependency management ensures that all the developers on a project are using the same versions of libraries and packages, along with making sure that upon deployment we know exactly what dependencies are needed to run the project.

### Version Control

All, besides a select few, of our projects will utilize [GitHub](https://github.com/) for version control, and you should be familiar with the basics of Git and GitHub in order to be a contributing member to DFR Software.

If you need a refresher, or need to learn the basics of Git and GitHub, please refer to the [Learning Git/Github](../onboarding/learning-Git.md) onboarding document.

#### Forking and branching <span style="color: #E97600;"><b>*</b></span>

Once you are a member of the DFR Software team on GitHub, you have access to all of our repositories. However, these repositories are write protected on their `main` branch, meaning you will not be able to push any changes directly to `main`. 

Instead, you will be required to create a new branch off of `main` for any changes you wish to make. This is done to ensure that all of our production code is never altered without prior review, both to ensure that we aren't allowing anyone to clear our repos, contribute with malicious code, or simply make a mistake that could break the entire project.

When making a new branch, you should keep the name descriptive of the change you are making. For example, if you are fixing a bug with data processing in one of our projects you might name your branch `data-processing-bugfix`.

**Example**

```shell
git clone <repo-url>

cd repo-name

git checkout -b branch-name

# make your changes

git add .

git commit -m "Fixed bug with data processing"

git push origin branch-name
```

#### Commits and pull requests messages <span style="color: #E97600;"><b>*</b></span>

Commit messages and pull request (PR) descriptions + titles should be clear, concise, and descriptive. Following the [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) specification is highly recommended, as it provides a clear and consistent way to structure commit messages.

All commit messages should be short, concise, and to the point. They should briefly describe the change made, and that's it.

Likewise all PR titles should be short, concise, and to the point. They should include the type of change, outlined in the [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) specification, along with the title, for example `fix: data processing bug`. The PR description should be more detailed, outlining the changes made, along with any relevant information for the reviewer.

**Examples**

Local commit message:
```shell
git commit -m "fix: data processing bug"
```

Pull request title and description:
```markdown
<!-- PR Title -->
fix: data processing bug

<!-- PR Description -->
This PR fixes a bug with data processing that was causing incorrect data to be processed. The bug was due to a typo in the data processing function.
```

#### Reviewing and merging <span style="color: #E97600;"><b>*</b></span>

As a reviewer, you should ensure that the code you are looking over follows all of the guidelines outlined in this document. If you find any issues, take note of them, comment on the lines that you notice issues, and request changes.

Once all the changes look good, remediate any potential merge conflicts, validating that everything still works as expected, and then merge the PR.

As a contributor, you should ensure that you have addressed all the comments made by the reviewer, and that your code follows all of the guidelines outlined in this document. Once you have made the necessary changes, request another review from the same reviewer, or another team member if they are unavailable.

### Dependency Management <span style="color: #E97600;"><b>*</b></span>

All [Python](https://www.python.org/) projects should utilize [Pipenv](https://pipenv.pypa.io/en/latest/) for dependency management.

If your project is not written in [Python](https://www.python.org/), you should use the dependency management tool that is most appropriate for your language and framework, for example [npm](https://www.npmjs.com/) for [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript).

#### Pipenv <span style="color: #E97600;"><b>*</b></span>

[Pipenv](https://pipenv.pypa.io/en/latest/) is an incredibly powerful, yet simple, tool that allows us to manage our dependencies, setup virtual environments, and validate our dependencies on the fly. 

To get started with [Pipenv](https://pipenv.pypa.io/en/latest/), you will first need to install it. You can do this via [pip](https://pip.pypa.io/en/stable/), the package manager for [Python](https://www.python.org/).

```shell
pip install pipenv
```

Assuming you have [Python](https://www.python.org/) configured correctly, you will now be able to restart your terminal, and use the `pipenv` command.

To create a new [Pipenv](https://pipenv.pypa.io/en/latest/) environment, or setup an existing one, navigate to your project directory, and run the following command:

```shell
pipenv install
```

This will setup a totally new virtual environment for your project, along with a corresponding `Pipfile` and its lock file, `Pipfile.lock`.

Any dependencies from here on out will be installed for your project via [Pipenv](https://pipenv.pypa.io/en/latest/), and will be added to your `Pipfile` and `Pipfile.lock` automatically.

To install a new dependency, simply run the following command:

```shell
pipenv install <package-name>
```

To access the virtual environment via the command line, you can use the following command:

```shell
pipenv shell
```

From here you can run any [Python](https://www.python.org/) commands like normal, and they will be executed within the virtual environment.

To select the virtual environment within [VSCode](https://code.visualstudio.com/), simply open the command palette via `Ctrl + Shift + P`, and search for `Python: Select Interpreter`. From this menu you should see a virtual environment sharing the name of your project, followed by 8 random characters. Select this environment, and you are good to go!

**Example environment name**

`software-wiki-8h4j3k2l`
