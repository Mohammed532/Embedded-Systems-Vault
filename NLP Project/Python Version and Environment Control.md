For the [[LeFlow Mini Project]], Python 3.11 is need (for tensorflow) but 3.12 is installed. Took a sidetrack to learn about pyenv and venv. 

## Pyenv

Is used to control multiple python versions on one system. Need it for installing multiple versions on laptop.

- [Pyenv Github](https://github.com/pyenv/pyenv?tab=readme-ov-file#b-set-up-your-shell-environment-for-pyenv)

### Usage

- `cd` to local folder
- `pyenv local --python_version--`
- `source ~/.bashrc`
- `python3 --version` to  double check version
- Python version is now updated, setup venv 

### Other Commands
- `pyenv versions` provides all versions on system


## Venv

Venv creates a virtual environment for python projects, for managing python libraries

- [How to Use Venv](https://www.freecodecamp.org/news/how-to-setup-virtual-environments-in-python/)
### Usage

To create a virtual environment
- ``python<version> -m venv <virtual-environment-name>`
	- `python3 -m venv env`

To start the virtual environment
- `source <virtual-envrionment-name>/bin/activate`
	- `source env/bin/activate`
- Windows: `<virtual-environment-name>/Scripts/activate.bat`

## Note
 - Might need to follow additional steps to share virtual environment.

