## Poetry
- poetry installation ```pip install poetry```
- initialization ```poetry init``` creates .toml file with basic packages your system needs
- create virtualenv and installing dependencies from .toml ```poetry install```
- get info ```poenty env info```
- get path where this venv is located ```poenty env info -p``` (dy default it's in folder /User/...)
- before changing the path DELETE created venv if it was created
- change by default path to project folder path ```poetry config virtualenvs.in-project true```
- now ```poetry install``` creates .venv folder right in folder with our project
- run venv ```poetry shell```
- add package to venv ```poetry add package_name``` (after that command you'll see this package in .toml file)
- remove package ```poetry remove package_name```
- exit venv ```exit```
- get list of active venvs ```poetry env list```
- let's go back into the shell again ```poetry shell```
- deactivate venv ```deactivate``` (now you out of the shell and the venv is also deactivated)
- remove venv is simple, because everything is in single folder ```Choose folder .venv and just delete it```

#### Poetry gives you opportunity to publish your package to pypi.org:
- ```poetry config repositories.test-pypi https://test.pypi.org/legacy```
Then you can go to test.pypi repository and get token that allows you to publish packages to the repository
- ```poetry config pypi-token.test.pypi pypi-...token_that_you_got_on_test.pypi.org```
Then you can say poetry to build package for you
- ```poetry build```
Then you can publish your package
- ```poetry publish -r test-pypi```

References:
* https://python-poetry.org/docs/
* https://habr.com/ru/articles/593529/


## Venv
The most basic virtual environment

creating venv:
``` python -m venv /path/to/new/virtual/environment ```

Running this command creates the target directory (creating any parent directories that don’t exist already) and places a pyvenv.cfg file in it with a home key pointing to the Python installation from which the command was run (a common name for the target directory is .venv). It also creates a bin (or Scripts on Windows) subdirectory containing a copy/symlink of the Python binary/binaries (as appropriate for the platform or arguments used at environment creation time). It also creates an (initially empty) lib/pythonX.Y/site-packages subdirectory (on Windows, this is Lib\site-packages). If an existing directory is specified, it will be re-used.

References:
* https://docs.python.org/3/library/venv.html

## Virtualenv
virtualenv is a tool to create isolated Python environments. Since Python 3.3, a subset of it has been integrated into the standard library under the venv module.

If you already have a Python 3.7+ interpreter the best is to use pipx to install virtualenv into an isolated environment. This has the added benefit that later you’ll be able to upgrade virtualenv without affecting other parts of the system.
```
pipx install virtualenv
virtualenv --help
```

References:
* https://virtualenv.pypa.io/en/latest/index.html
  
## Pyenv
Pyenv is a Python version management tool. It is ideal for managing different Python installations. This tool allows you to work with multiple Python versions effortlessly. Pyenv provides many functionalities for users, including the ability to switch between versions, globally or per-project basis, compilation error diagnostic, and plugin support.

This command will install pyenv on your windows operating system.
```
pip install pyenv-win --target %USERPROFILE%\\.pyenv
```

References:
* https://blog.enterprisedna.co/pyenv/

## Pipenv
#### The problems that Pipenv seeks to solve are multi-faceted:

- You no longer need to use ```pip``` and ```virtualenv``` separately: they work together.
- Managing a ```requirements.txt``` file with package hashes can be problematic. Pipenv uses ```Pipfile``` and ```Pipfile.lock``` to separate abstract dependency declarations from the last tested combination.
- Hashes are documented in the lock file which are verified during install. Security considerations are put first.
- Strongly encourage the use of the latest versions of dependencies to minimize security risks arising from outdated components.
- Gives you insight into your dependency graph (e.g. $ ```pipenv graph```).
- Streamline development workflow by supporting local customizations with ```.env``` files.

The recommended way to install pipenv on most platforms is to install from pypi using pip:
```pip install --user pipenv```

References:
* https://pipenv.pypa.io/en/latest/

## Conda
Conda is an open-source, cross-platform, language-agnostic package manager and environment management system. It was originally developed to solve package management challenges faced by Python ```DATA SCIENTIST```, and today is a popular package manager for Python and R.

References:
* https://docs.conda.io/projects/conda/en/stable/index.html#
