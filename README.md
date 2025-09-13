# better-onboarding
A total redo of the onboarding process 

**NOTE THIS IS THE SOURCE REPO, NOT THE PUBLISHED VERSION. THE PUBLISHED VERSION CAN BE FOUND [HERE](https://software.dallasformularacing.com/)!**

# Table of contents

# Setup

## Dependencies
* [Python 3.11.X](https://www.python.org/downloads/release/python-3119/) or higher (Linked is the final version of 3.11 with an installer)
* [Pipenv](https://pipenv.pypa.io/en/latest/#quick-start) (Install using `pip install pipenv`)


## Installation
1. Clone the repo `git clone https://github.com/DallasFormulaRacing/better-onboarding.git`
2. Make a new branch in the repo for your changes `git checkout -b <branch-name>`
3. In the root directory of the project, run `pipenv install` to install dependencies and build your virtual environment.
4. Run `pipenv shell` to enter the virtual environment.
5. Run `mkdocs serve --livereload` to start a local server and enable auto page refresh on file changes. 
6. You can now view the site at [`http://127.0.0.1:8000`](http://127.0.0.1:8000).

# Guidelines
* All content should be in the `docs` folder, and then sorted under the respective subfolder.
* All images and other file assets should be located under the `docs/assets` folder.
* All pages should be properly named and linked in the `mkdocs.yml` file to maintain sidebar functionality.
* Upon completing your changes, make a PR to the `src` branch for review.

## ALL OTHER STYLE AND CONTENT GUIDELINES ARE LOCATED IN THE [HERE](https://software.dallasformularacing.com/policies/style-guide/).