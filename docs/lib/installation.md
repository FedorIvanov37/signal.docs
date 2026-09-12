# Installation 



## Quick installation 

Quick installation for those who do not want to read the full guide.

1. Install Python 3.12
2. Run the following commands in the Windows command line 

```cmd
python -m venv signal_env

signal_env\Scripts\activate

pip install PyQt6 pydantic fastapi uvicorn loguru python-box click
```

Installation is complete and the environment is ready to use the Signal library.

## Complete Installation

The process consists of three steps:

1. [Install Python](/lib/installation/#python-installation)
2. [Create and activate a virtual environment](/lib/installation/#create-virtual-environment)
3. [Install the required packages](/lib/installation/#install-the-dependencies)

After completing these steps, the environment will be ready and you can proceed to the library usage examples below.

### Python installation

Before installing Signal dependencies, make sure Python is installed on your system. Signal requires Python 3.12 or 
higher. You can download Python from the [official website](https://www.python.org/downloads/).

During installation on Windows, it is strongly recommended to enable the option `Add Python to PATH`.  This allows 
you to run Python and pip directly from the command line.


### Create Virtual Environment
It is highly recommended (but not required) to create and 
activate a [Python virtual environment](https://docs.python.org/3/library/venv.html) to keep package installations isolated.

Create an isolated environment 
```shell
python -m venv signal_env
```

Activate the virtual environment
```cmd
signal_env\Scripts\activate
```


### Install the dependencies

To install all required [dependencies](/lib/dependencies), run the following command.

```shell
pip install PyQt6 pydantic fastapi uvicorn loguru python-box click
```

Installation is complete and the environment is ready to use the Signal library.