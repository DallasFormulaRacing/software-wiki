# [better-onboarding ![GitHub](https://img.shields.io/badge/GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/DallasFormulaRacing/better-onboarding/)

## Basic information

---

### PM info

* Name - William D.
* GitHub - @Skribb11es
* Discord - [Skribb11es](https://discord.com/users/859093011711787039)

### Contributors

<a href = "https://github.com/dallasformularacing/better-onboarding/graphs/contributors">
  <img src = "https://contrib.rocks/image?repo=dallasformularacing/better-onboarding" width="3%">
</a>

### Description

This project is a ground up redesign of the previous onboarding process. Started in Fall of 2024, the goal of this project is to both improve the process for bringing new members onto the team, as well as serve as a platform for DFR Software to document and showcase its projects.

## Working with the source

When preparing to document a project you may be working on, please note that you will be expected to follow the [Style Guide](../policies/style-guide.md). If you fail to follow these guidelines your PR may be rejected or sent back for changes.

### Dependencies
* [Python 3.11.X](https://www.python.org/downloads/release/python-3119/) or higher (Linked is the final version of 3.11 with an installer)
* [Pipenv](https://pipenv.pypa.io/en/latest/#quick-start) (Install using `pip install pipenv`)


### Installation
1. Clone the repo `git clone https://github.com/DallasFormulaRacing/better-onboarding.git`
2. Make a new branch in the repo for your changes `git checkout -b <branch-name>`
3. In the root directory of the project, run `pipenv install` to install dependencies and build your virtual environment.
4. Run `pipenv shell` to enter the virtual environment.
5. Run `mkdocs serve --livereload` to start a local server and enable auto page refresh on file changes. 
6. You can now view the site at [`http://127.0.0.1:8000`](http://127.0.0.1:8000).

### Guidelines
* All content should be in the `docs` folder, and then sorted under the respective subfolder.
* All images and other file assets should be located under the `docs/assets` folder.
* All pages should be properly named and linked in the `mkdocs.yml` file to maintain sidebar functionality.
* Upon completing your changes, make a PR to the `src` branch for review.
* ALL OTHER STYLE AND CONTENT GUIDELINES ARE LOCATED IN THE [STYLE GUIDE](../policies/style-guide.md).