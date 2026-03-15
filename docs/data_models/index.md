# Data models

## Signal Data Models

This chapter contains Signal data models - the description of data element, which can be processed by the Signal

Incoming data can be put to the terminal by different ways

| Data type     | Supported formats     | GUI                                                                                | CLI                                      | API                            | 
|---------------|-----------------------|------------------------------------------------------------------------------------|------------------------------------------|--------------------------------| 
| Transaction   | `JSON`, `DUMP`, `INI` | Hotkey `Ctrl + O`, button `Open File` or drop file to the MainWindow on Signal GUI | Argument `--file FILE` or `--dir DIR`    | Endpoint `/api/transactions`   |
| Specification | `JSON`                | Hotkey `Ctrl + O`, button `Open File` or drop file to the SpecWindow on Signal GUI | Argument `--specification SPECIFICATION` | Endpoint `/api/specifications` |
| Config        | `JSON`                | Setup in `Tools → Settings` UI-tool                                                | Argument `--config-file CONFIG_FILE`     | Endpoint `/api/config`         |


