# Data models

## Signal Data Models

!!! tip "Data models purpose"

    This chapter is a reference guide for advanced Signal users. In all Signal operating modes, data models are 
    handled automatically, without user intervention.

    You can use the GUI, CLI, or API without learning how the data models work.

    Understanding the data models is necessary when using the [Python library](/lib) or modifying the default behavior of the GUI, 
    CLI, and API.


Signal stores data in instances of data models. A data model is a structured representation of system data, such as 
transaction data, configuration, and other entities. Signal uses several data models to hold the information needed for 
transaction processing.

Learn more about data models on the [Pydantic website](https://docs.pydantic.dev/latest/concepts/models/).

Signal uses the following public data models.

| Data Model                                  | Description                                                                                             | Supported formats     | 
|---------------------------------------------|--------------------------------------------------------------------------------------------------------|-----------------------| 
| [Transaction](/data_models/transaction)     | Payment transaction data: MTI, transaction data fields<br/>Used for incoming and outgoing transactions | `JSON`, `DUMP`, `INI` |
| [Specification](/data_models/specification) | Field formats, validation rules, descriptions, and hierarchy                               | `JSON`                | 
| [Config](/data_models/config)               | General configuration data and base settings for all operating modes                                        | `JSON`                |


Data can be loaded into Signal in several ways.

 | Data models                                 | GUI                                                                                           | CLI                             | API                     |
 |---------------------------------------------|-----------------------------------------------------------------------------------------------|---------------------------------|-------------------------|
 | [Transaction](/data_models/transaction)     | • Hotkey `Ctrl + O` <br/>• Button `Open File`<br/>• Drop a file into the Signal GUI main window | `--file FILE` or `--dir DIR`    | `/api/transactions`     |
 | [Specification](/data_models/specification) | • Hotkey `Ctrl + O`,<br/>• Button `Open File`<br/>• Drop a file into the Signal GUI specification window | `--specification SPECIFICATION` | `/api/specifications`   |
 | [Config](/data_models/config)               | Configure in `Tools → Settings` interface                                                           | `--config-file CONFIG_FILE`     | `/api/config`           |
