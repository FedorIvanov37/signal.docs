# Data models

## Signal Data Models

!!! tip "Data models purpose"

    This chapter is a reference guide for advanced Signal users. In all existing Signal operating modes, data models are 
    handled automatically, without user intervention

    If you are a user of the GUI, CLI, or API, you can fully utilize them without learning the concept of data models

    Data models are required for [Python library](/lib) users and for modifying the default behavior of the Signal GUI, 
    CLI, and API    


Signal stores data in instances of data models. A data model is a structured representation of system data, such as 
transaction data, configuration, and other entities. The Signal has a few data models, containing the data for 
transaction processing

See more about data models concept on [pydantic website](https://docs.pydantic.dev/latest/concepts/models/)

Signal works with the following public datasets 

| Data Model                                  | What is it                                                                                             | Supported formats     | 
|---------------------------------------------|--------------------------------------------------------------------------------------------------------|-----------------------| 
| [Transaction](/data_models/transaction)     | Payment transaction data: MTI, transaction data fields<br/>Uses for incoming and outgoing transactions | `JSON`, `DUMP`, `INI` |
| [Specification](/data_models/specification) | Data fields formats, validation rules, fields descriptions, and hierarhy                               | `JSON`                | 
| [Config](/data_models/config)               | General configuration data. Base settings for all the run modes                                        | `JSON`                |


Incoming data can be loaded to the Signal by different ways

 | Data models                                 | GUI                                                                                           | CLI                             | API                     |
 |---------------------------------------------|-----------------------------------------------------------------------------------------------|---------------------------------|-------------------------|
 | [Transaction](/data_models/transaction)     | • Hotkey `Ctrl + O` <br/>• Button `Open File`<br/>• Drop file to the MainWindow on Signal GUI | `--file FILE` or `--dir DIR`    | `/api/transactions`     |
 | [Specification](/data_models/specification) | • Hotkey `Ctrl + O`,<br/>• Button `Open File`<br/>• Drop file to the SpecWindow on Signal GUI | `--specification SPECIFICATION` | `/api/specifications`   |
 | [Config](/data_models/config)               | Setup in `Tools → Settings` UI-tool                                                           | `--config-file CONFIG_FILE`     | `/api/config`           |
