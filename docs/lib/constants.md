## Constants

Constants store stable application values that must remain unchanged during runtime.

In most cases, Signal uses Python `StrEnum` for this purpose. Typical examples include file paths, default directories, 
status names, validation modes, protocol values, UI colors, service messages, welcome texts, and many other important 
operational parameters.

Constants work as a lightweight internal project database. Unlike a real database, these values are available only for 
reading and cannot be modified while the program is running. They ensure consistency and predictability while eliminating 
hardcoded values across the project.

Constants are an essential part of the library and are used by almost every module.

## Using Constants

All Signal constants are stored in modules located at `common.lib.enums`.

To use a constant, first import the required group of constants from the list below, then access the required attribute 
directly from the imported object.

The example below shows how to get the current library version.

```python
from common.lib.enums.ReleaseDefinition import ReleaseDefinition  # Import constants group ReleaseDefinition from common.lib.enums

print(ReleaseDefinition.VERSION)  # Get the current library version
```

The second example shows how to get the default configuration file path to create a Config object.

```python
from common.lib.data_models.Config import Config
from common.lib.enums.TermFilesPath import TermFilesPath


config: Config = Config(TermFilesPath.CONFIG)  # Config tool will read the path, stored in the constant TermFilesPath.CONFIG
```


This approach keeps the code predictable, removes hardcoded values, and provides a single source of truth for important 
application parameters.


## Constants Reference

### TermFilesPath

`TermFilesPath` contains the paths of all system files used by Signal

These constants define the default locations of configuration files, specification files, default transaction templates, 
dictionaries, logs, backups, and other internal resources required for normal library operation.

Using these constants helps avoid hardcoded paths and provides a single reliable source for locating internal project 
files.

??? example "TermFilesPath Reference"
    | Name                | Description                                                                                           | Example                                                     | Comment                                                                                                          |
    |---------------------|----------------------------------------------------------------------------------------------------|-------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
    | CONFIG              | Main application configuration file path                                                           | `common/data/settings/config.json`                          |                                                                                                                  |
    | DEFAULT_CONFIG      | Path to the default reference configuration file                                                   | `common/data/settings/default_config.json`                  | Mostly used to restore basic settings                                                                            |
    | SPECIFICATION       | Path to the specification file, containing the structure and processing rules for transaction messages | `common/data/settings/specification.json`                   | Detailed specification settings are described on the Specification Data Model [page](/data_models/specification) |
    | ECHO_TEST           | Path to the file containing the default fields and structure of the echo-test request              | `common/data/default/default_message.json`                  | Will be parsed on startup                                                                                        |
    | KEEP_ALIVE          | Path to the file containing the default fields and structure of the keep-alive request             | `common/data/default/keep-alive.json`                       |                                                                                                                  |
    | DEFAULT_FILE        | Path to the file containing the default fields and structure of the keep-alive request             | `common/data/default/echo-test.json`                        |                                                                                                                  |
    | LICENSE_INFO        | Path to the file containing information about the user's license acceptance                        | `common/data/license/license_info.json`                     |                                                                                                                  |
    | LOG_FILE_NAME       | Path to the main log file                                                                          | `common/log/signal.log`                                     |                                                                                                                  |
    | CURRENCY_DICT       | Path to the file containing the list of available currencies                                       | `common/data/dictionary/currencies.json`                    |                                                                                                                  |
    | COUNTRY_DICT        | Path to the file containing the list of available countries                                        | `common/data/dictionary/countries.json`                     |                                                                                                                  |
    | MCC_DICT            | Path to the file containing the list of available Merchant Category Codes (MCC)                    | `common/data/dictionary/merch_categories.json`              |                                                                                                                  |
    | LICENSE_AGREEMENT   | Path to the file containing the text of the user license agreement                                 | `common/data/license/license.agreement.txt`                 |                                                                                                                  |
    | POSTMAN_COLLECTION  | Path to the archive with the Postman collection                                                    | `common/data/postman/Signal_v0.19.1_postman_collection.zip` | Used for downloading through the API                                                                             |

### TextConstants

`TextConstants` contains all meaningful user-facing text messages and their templates used by Signal

These constants include service messages, system notifications, warnings, validation results, startup texts, license 
messages, API responses, and other text values shown to the user during program execution.

Using centralized text constants helps keep messages consistent across the application, simplifies maintenance, and 
avoids duplicated hardcoded strings in program modules.

??? example "TextConstants Reference"
    | Name                   | Description                                                                                | Example  |
    |------------------------|-----------------------------------------------------------------------------------------|----------|
    | SYSTEM_NAME            | Application name used across the system                                                 | `Signal` | 
    | HELLO_MESSAGE          | Welcome message shown to the user in console output, terminal screen, and API responses |          | 
    | LICENSE_AGREEMENT      | Text of the user license agreement displayed during application usage                   |          | 
    | CLI_DESCRIPTION        | Self-description of Signal shown to command-line interface users                        |          | 
    | API_EXPLANATION        | Message informing the user that the system provides API functionality                   |          | 
    | API_EXPLANATION_URL    | URL leading to the API reference documentation                                          |          | 
    | USER_REFERENCE_GUIDE   | URL leading to the User Reference Guide                                                 |          | 
    | ECHO_TEST_RESPONSE     | Text of the echo-test message used for display in documentation                         |          | 
    | OPENAPI_HELLO_MESSAGE  | Welcome message shown to users on the OpenAPI documentation page                        |          | 


### ReleaseDefinition

`ReleaseDefinition` contains complete release information about the current Signal version

These constants include the application name, current version, release date, author information, contact details, 
product description, and other metadata related to the project release.

This group is used for version display, startup information, CLI output, About sections, documentation generation, and 
general project identification.

??? example "ReleaseDefinition Reference"
    | Name           | Description                   | Example                  |
    |----------------|----------------------------|--------------------------|
    | NAME           | Application name           | `Signal`                 |
    | VERSION        | Application version        | `v0.21`                  |
    | VERSION_NUMBER | Application version number | `21`                     |
    | RELEASE        | Release date               | `March 2026`             |
    | AUTHOR         | Author's name                | `Fedor Ivanov`           |
    | EMAIL          | Contact email              | `fedornivanov@gmail.com` |
    | CONTACT        | Contact email link       |                          |


### MessageLength

`MessageLength` contains the length definitions for different parts of transaction messages

These constants define the expected sizes of message headers, MTI, bitmap sections, field length markers, tags, and 
other protocol elements used during message construction, parsing, and validation.

Using centralized length definitions helps keep message processing consistent and prevents errors caused by hardcoded 
protocol values.

??? example "MessageLength Reference"
    | Name                     | Description                                                           | Example | Comment                                     |
    |--------------------------|--------------------------------------------------------------------|---------|---------------------------------------------|
    | BITMAP_LENGTH            | Length of a single bitmap section in the transaction message       | 8       |                                             |
    | MESSAGE_TYPE_LENGTH      | Length of the Message Type Identifier (MTI) in ASCII format        | 4       |                                             | 
    | MESSAGE_TYPE_LENGTH_HEX  | Length of the Message Type Identifier (MTI) in hexadecimal format  | 8       | Calculated as `MESSAGE_TYPE_LENGTH * 2`     | 
    | FIRST_BITMAP_CAPACITY    | Maximum field number that fits into a single 8-byte bitmap section | 64      | Always 64                                   | 
    | SECOND_BITMAP_CAPACITY   | Maximum field number that fits into two bitmap sections            | 128     | Calculated as `FIRST_BITMAP_CAPACITY * 2`   | 
    | FIRST_BITMAP_LENGTH_HEX  | Length of the first bitmap section in hexadecimal format             | 16      |                                             | 
    | SECOND_BITMAP_CAPACITY   | Length of the first bitmap section in hexadecimal format             | 32      | Calculated as `FIRST_BITMAP_LENGTH_HEX * 2` | 


### LicenseAgreement

`LicenseAgreement` contains the full text of the user license agreement used by Signal

These constants store the license terms, acceptance messages, and related legal text shown to the user during 
application startup and usage.

??? example "LicenseAgreement Reference"
    | Name      | Description                                |
    |-----------|-----------------------------------------|
    | AGREEMENT | Full text of the user license agreement |

### DumpLength

`DumpLength` contains the length definitions used for transaction messages represented as hexadecimal dumps

These constants define the sizes of message parts when working with raw dump format, including headers, MTI, bitmap 
sections, field length markers, and other low-level protocol elements in hexadecimal representation.

This group is used during dump parsing, dump generation, low-level validation, and conversion between raw host dumps and 
structured transaction models.

??? example "DumpLength Reference"
    | Name              | Description                                                                     | Example | 
    |-------------------|------------------------------------------------------------------------------|---------|
    | LINE_LENGTH       | Length of each dump line, used for line wrapping during dump generation      | 32      |
    | HEX_LINE_LENGTH   | Length of each dump line in hexadecimal representation, including separators | 51      |
    | ASCII_LINE_LENGTH | Length of each dump line in ASCII representation                             | 16      |
    | BYTE_LENGTH       | Length of a single hexadecimal character                                     | 2       |

