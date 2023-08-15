# How to Generate Documentation for VA data commons

## Overview

Documentation for VA is usually written in a markdown or google drive file. The steps of converting markdown/google drive/word/etc files to HTML is currently as folows.

1. Convert documentation into markdown format if its not currently in markdown format
2. Convert markdown to rst format via pandocs
3. Convert rst to HTML via sphinx

## Requirements

### Preferred way

Separate virtual environment is recommended for building documentation:

* Create virtual environment in the cloned repository.
```
python3 -m venv .venv
```

* Activate virtual environment.
```
source .venv/bin/activate
```

* Install required packages.
```
python3 -m pip install -r requirements.txt
```

* Use sphinx:
```
sphinx-build -b html source build
```

### Alternative way

* Use official [instruction](https://www.sphinx-doc.org/en/master/usage/installation.html)
* Homebrew `sphinx-doc` package:
```
brew install sphinx-doc
```

## Usage

1. Use `./docs/` as a main working directory.
2. Write any documentation pages in the `source` directory. Use markdown format only.
3. Run `make html` to generate build directory with documentation.
4. Check the result of the build in the `build` directory. The `html/index.html` file is the main page of the documentation.
5. Run `deactivate` when finished working with documentation.

### Adding generated documentation to qa/preprod/prod

1. Having either [gitops-qa](https://github.com/uc-cdis/gitops-qa) (for QA) or [cdis-manifest](https://github.com/uc-cdis/cdis-manifest) (for pre-prod/prod).
2. Run `make html` to generate build directory with documentation.
3. Copy the documentation to either `gitops-qa`/`cdis-manifest` repositories. For example, for QA, assuming that `gitops-qa` is in the same directory as `va-doc` repository, **WARNING** this step will remove all files in the destination directory and copy all files from the source directory:
```
make copy DEST_DIR=../../gitops-qa/qa-mickey.planx-pla.net/dashboard/Public/documentation/
```
4. Commit and push the changes to the repository, either `gitops-qa` or `cdis-manifest`.
5. For next steps refer to the `dashboard` documentation: https://github.com/uc-cdis/cdis-wiki/blob/master/onboarding/services/dashboard.md.
