# Project Documentation Guidelines

When documenting a project it is important to follow the style and formatting guidelines found in our [Style Guide](style-guide.md). This document will only cover the specific requirements of documenting a project.

!!! warning "IMPORTANT"
    Your project documentation should follow the structure outlined in this document. This means that your title should be followed by a `Basic information` section, a `Showcase` section (if you have one), and then a `Working with the source` section. 
    
    It should also be noted that all of these sections should be properly nested using markdown headers. The `Basic information`, `Showcase`, and `Working with the source` sections should be H2 headers, while all subsections should be H3 headers. Any further subsections should be H4 headers, and so on.

## General layout

---

### Title

The title of your project should should include the name, as well as a link to the source of the project. You should also include a matching shield in the title to indicate the location of the source code. 

An example of this can be found below:

```md
# [PROJECT TITLE ![GitHub](https://img.shields.io/badge/GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/DallasFormulaRacing/PROJECT-REPO/)
```

To view all the available shields visit [this repository](https://github.com/inttter/md-badges), or go directly to [shields.io](https://shields.io/).

### Basic information

Within your `Basic information` section, you should include the following details:

#### PM info
* Name - Full first name and last initial - `John D.`
* GitHub - GitHub handle - `@JohnDoe123`
* Discord - Discord user as a URL - `[John D.](https://discord.com/users/{DISCORD_ID})`

#### Contributors

This is a semi-static codeblock that should be inserted, and have the repo name changed to match your project. If your project is not on GitHub, you should list the contributors manually.

##### GitHub project

```html
### Contributors

<a href = "https://github.com/dallasformularacing/{REPO_NAME}/graphs/contributors">
  <img src = "https://contrib.rocks/image?repo=dallasformularacing/{REPO_NAME}" width="3%">
</a>
```
##### Non-GitHub project

```md
### Contributors

* Full first name and last initial - Discord handle
* John D. - JohnDoe123
* Jane S. - JaneSmith123
```

#### Description

A brief description of the project, its purpose, and any relevant information. This should be about 2-3 sentences long, but if you need to over this limit that is fine.

### Showcase

If your project has a UI/UX component, or you just have something you want to show off, this is your playground. Include screenshots, gifs, or even videos of your project in action. This section is optional, but highly encouraged. This section is totally open ended, as long as you adhere to the [Style Guide](style-guide.md).

### Working with the source

Here you will properly document the inner workings of your project, this should include any project dependencies, detailed installation instructions, and any other relevant information for working with the source code.

#### Dependencies
List any dependencies required to work with the source code of your project. This should include any languages, frameworks, libraries, or tools needed to properly run and develop the project, along with direct links or brief installation instructions. In the case of a Python project, you should include the python version, as well as any packages you installed using `pip`, and a single line for each package with their respective install commands, for example: 

```
* [Python 3.11.X](https://www.python.org/downloads/release/python-3119/) or higher (Linked is the final version of 3.11 with an installer)
* [Pipenv](https://pipenv.pypa.io/en/latest/#quick-start) (Install using `pip install pipenv`)
```

#### Installation
A numbered step by step list of instructions for installing, or building your project locally. This should start any commands for cloning, building, and running the project. An example of this can be found below:

```md
1. Clone the repo `git clone https://github.com/DallasFormulaRacing/better-onboarding.git`
2. Make a new branch in the repo for your changes `git checkout -b <branch-name>`
3. In the root directory of the project, run `pipenv install` to install dependencies and build your virtual environment.
4. Run `pipenv shell` to enter the virtual environment.
5. Run `mkdocs serve --livereload` to start a local server and enable auto page refresh on file changes. 
6. You can now view the site at [`http://127.0.0.1:8000`](http://127.0.0.1:8000).
```

#### Guidelines
A bulleted list of guidelines that you expect contributors to follow when working with the source code. An example of this can be found below:

```md
* All content should be in the `docs` folder, and then sorted under the respective subfolder.
* All images and other file assets should be located under the `docs/assets` folder.
* All pages should be properly named and linked in the `mkdocs.yml` file to maintain sidebar functionality.
* Upon completing your changes, make a PR to the `src` branch for review.
```