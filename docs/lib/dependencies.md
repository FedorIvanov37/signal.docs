# Dependencies

Unlike the standalone GUI build, the Signal library requires manual installation of the runtime environment and external 
Python packages.

The table below lists the minimum required dependencies for stable library operation. These modules are used by the 
Signal core for transaction processing, validation, API support, logging, configuration management, and internal event 
handling.

Using a Python virtual environment is strongly recommended to keep the installation isolated and avoid version conflicts 
with other projects.

Later versions are generally allowed unless your internal environment requires strict version control or compatibility 
with existing infrastructure.

| Dependency                                             | Minimum Version | Higher Version Allowed | Comment                                 |                                 
|--------------------------------------------------------|-----------------|------------------------|-----------------------------------------|
| [Python](https://www.python.org/)                      | 3.12.2          | Yes                    | -                                       | 
| [PyQt6](https://pypi.org/project/PyQt6/)               | 6.6.1           | Yes                    | Not compatible with PyQt5               | 
| [pydantic](https://pydantic.dev/docs/)                 | 2.6.3           | Yes                    | -                                       | 
| [fastapi](https://fastapi.tiangolo.com/)               | 0.136.1         | Yes                    | -                                       | 
| [uvicorn](https://uvicorn.dev/)                        | 0.46.0          | Yes                    | -                                       | 
| [loguru](https://loguru.org/)                          | 0.7.3           | Yes                    | -                                       | 
| [python-box](https://pypi.org/project/python-box/)     | 7.4.1           | Yes                    | Highly recommended for everyday use  |
| [click](https://click.palletsprojects.com/en/stable/)  | 8.3.3           | Yes                    | Required for FastAPI                    |
