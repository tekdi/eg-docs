---
sidebar_position: 2
tags: [python, styleguide]
---

# Ruff

## About
- Ruff is a superfast Python **linter + formatter**
- Ruff can help you with linting, formatting code as per configuration
- It also lets you sort imports as per `isort` standard

### Links
- [Ruff Homepage](https://docs.astral.sh/ruff/)

## Installation
- You can install pylint in your project's venv using command `pip install ruff` or `pip3 install ruff`

## Config file for ruff.toml
- Create and use a file named `ruff.toml` in your python project root folder
- You can use the `ruff.toml` file contents given below

```yml
# Exclude a variety of commonly ignored directories.
exclude = [
    ".bzr",
    ".direnv",
    ".eggs",
    ".git",
    ".git-rewrite",
    ".hg",
    ".ipynb_checkpoints",
    ".mypy_cache",
    ".nox",
    ".pants.d",
    ".pyenv",
    ".pytest_cache",
    ".pytype",
    ".ruff_cache",
    ".svn",
    ".tox",
    ".venv",
    ".vscode",
    "__pypackages__",
    "_build",
    "buck-out",
    "build",
    "dist",
    "node_modules",
    "site-packages",
    "venv",
]

# Same as Black.
line-length = 88
indent-width = 4

[lint]
# Enable Pyflakes (`F`) and a subset of the pycodestyle (`E`)  codes by default.
# Unlike Flake8, Ruff doesn't enable pycodestyle warnings (`W`) or
# McCabe complexity (`C901`) by default.
# Enable flake8-bugbear (`B`) rules, in addition to the defaults.
select = ["E4", "E7", "E9", "F", "B"]

# Avoid enforcing line-length violations (`E501`)
ignore = ["E501"]

# Allow fix for all enabled rules (when `--fix`) is provided.
# Avoid trying to fix flake8-bugbear (`B`) violations.
fixable = ["ALL"]
unfixable = ["B"]

# Ignore `E402` (import violations) in all `__init__.py` files, and in select subdirectories.
[lint.per-file-ignores]
"__init__.py" = ["E402"]
"**/{tests,docs,tools}/*" = ["E402"]

[format]
# Like Black, use double quotes for strings.
quote-style = "double"

# Like Black, indent with spaces, rather than tabs.
indent-style = "space"

# Like Black, respect magic trailing commas.
skip-magic-trailing-comma = false

# Enable auto-formatting of code examples in docstrings. Markdown,
# reStructuredText code/literal blocks and doctests are all supported.
#
# This is currently disabled by default, but it is planned for this
# to be opt-out in the future.
docstring-code-format = false

# Set the line length limit used when formatting code snippets in
# docstrings.
#
# This only has an effect when the `docstring-code-format` setting is
# enabled.
docstring-code-line-length = "dynamic"
```

## How to use Ruff?
### A) Using Ruff outside the editor, via terminal
- Goto your project repo `cd my-python-project`
- Activate your project's venv `source /path-to-your-projects-env/bin/activate`
- To run Ruff as a linter, try any of the following:
```
ruff check                          # Lint all files in the current directory (and any subdirectories).
ruff check path/to/code/            # Lint all files in `/path/to/code` (and any subdirectories).
ruff check path/to/code/*.py        # Lint all `.py` files in `/path/to/code`.
ruff check path/to/code/to/file.py  # Lint `file.py`.
ruff check @arguments.txt           # Lint using an input file, treating its contents as newline-delimited command-line arguments.
```

- Or, to run Ruff as a formatter:

```
ruff format                          # Format all files in the current directory (and any subdirectories).
ruff format path/to/code/            # Format all files in `/path/to/code` (and any subdirectories).
ruff format path/to/code/*.py        # Format all `.py` files in `/path/to/code`.
ruff format path/to/code/to/file.py  # Format `file.py`.
ruff format @arguments.txt           # Format using an input file, treating its contents as newline-delimited command-line arguments.
```

### B) Using Ruff inside VSCode editor
#### 1) Install this VSCode extension for Ruff
- [Ruff VSCode Extension](https://marketplace.visualstudio.com/items?itemName=charliermarsh.ruff)

#### 2) VSCode Settings for Ruff
You can edit `settings.json` of VSCode as below
- To set Ruff as default formatter for Python files
- To auto format code file on Save
- To auto organize imports on Save

```json
{
   "[python]": {
       "editor.defaultFormatter": "charliermarsh.ruff",
       "editor.formatOnSave": true,
       "editor.codeActionsOnSave": {
           "source.organizeImports": "explicit"
       },
   },
}
``` 

#### 3) Open any python file in editor
- Open `Problems` tab in console, to see  linting errors if any

#### 4) References
- Read more here [Linting Python in Visual Studio Code
](https://code.visualstudio.com/docs/python/linting)