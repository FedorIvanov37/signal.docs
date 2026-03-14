# Transaction

## Transaction data

Transaction data is an incoming Signal dataset, containing payment transaction data

In GUI mode you can put this data to some file, e.g. `transaction.json` and parse this file. Use hotkey `Ctrl + O`, 
button `Open File` or drop file to the MainWindow on Signal GUI to open the incoming transaction file

See [here](/data_models) how to read the transaction data in any Signal run mode

## Transaction format

The signal supports three transaction data formats

| Data format | File extension    | Supported in  | Comment                             |
|-------------|-------------------|---------------|-------------------------------------|
| JSON        | `.json`           | GUI, CLI, API | Recommended transaction data format |
| DUMP        | `.dump` or `.txt` | GUI, CLI      |                                     |
| INI         | `.ini`            | GUI, CLI      |                                     |

In case when the Signal GUI incoming transaction file cannot be recognized by the incoming file extension the Signal 
will try to parse the transaction as every known format. See details in [data exchange](/gui/features/data_exchange) 
chapter


## Transaction data model

### JSON

JSON-like transaction data fields representation  

| Field           | Type                   | Required | Default value | Contains                                         | Validation                                                        | Valid example                   | 
|-----------------|------------------------|----------|---------------|--------------------------------------------------|-------------------------------------------------------------------|---------------------------------|
| message_type    | str[int]               | Yes      | -             | Transaction Message Type Identifier              | Lenght is exact 4<br>Digits only<br>Field exists in Specification | 0200                            |
| max_amount      | str[int]               | No       | 100           | Maximum generated transaction amoun              | Digits only                                                       | 100                             |
| generate_fields | list[str[int]]         | No       | [ ]           | Field numbers to generate                        | Digits only                                                       | ["4", "11", "37"]               |
| data_fields     | dict[str, str \| dict] | yes      | -             | JSON-like transaction data fields representation | According to the field specification                              | {"3": "000000", "11" :"145787"} |

??? example "JSON transaction example"  
    ```json
    --8<-- "files/data_examples/transaction.json"
    ```

### INI

INI transaction fields representation. See more about INI format [here](https://en.wikipedia.org/wiki/INI_file)

INI format contains the following parts: sections, options, and option values. 

```ini
[SECTION]
OPTION = [VALUE]
ANOTHER_OPTION = [ANOTHER_VALUE]

[ANOTHER_SECTION]
OPTION = [VALUE]
ANOTHER_OPTION = [ANOTHER_VALUE]
;...
;...
```

All the options values should be put in square brackets like [this]

```ini
[MESSAGE]
F002 = [4000000000000000]  ; Correct
F003 = 000000              ; Incorrect
```

All the fields numbers in the section [MESSAGE] must start from F. E.g. F002

```ini
[MESSAGE]
F002 = [4000000000000000]  ; Correct
3    = [000000]            ; Incorrect
```


| Section     | Option                         | Type      | Required   | Default value | Contains                            | Validation                                        | Valid example                                                     | 
|-------------|--------------------------------|-----------|------------|---------------|-------------------------------------|---------------------------------------------------|-------------------------------------------------------------------|
| [MTI]       | MTI                            | str[int]  | Yes        | -             | Transaction Message Type Identifier | lenght is 4, digits only, exists in Specification | [0200]                                                            |
| [CONFIG]    | MAX_AMOUNT                     | str[int]  | No         | 100           | Maximum generated transaction amoun | Digits only                                       | 100                                                               |
| [CONFIG]    | GENERATE_FIELDS                | list[int] | No         | [ ]           | Field numbers to generate           | Digits only                                       | [4, 11, 37]                                                       |
| [MESSAGE]   | FNNN where NNN is field number | str       | yes        | -             | Transaction data fields             | According to the field specification              | F002 = [4000000000000000] <br> F003 = [000000] <br>;...<br>;...   |


!!! danger "% Substitution"
    Due to ConfigParser library restrictions the sign `%` in options values must be written as double percent, `%%` only

    Refer to the [ConfigParser](https://docs.python.org/3/library/configparser.html) for details 
    
    ```ini
    [MESSSAGE]
    VALUE = [100%% Complete]  ; Correct, will desplay "100% Complete"
    VALUE = [100% Complete]   ; Incorrect, will lead to parsing error
    ```

??? example "INI transaction example"
    ```ini
    --8<-- "files/data_examples/transaction.ini"
    ```

### DUMP

??? example "DUMP transaction example"
    ```text
    --8<-- "files/data_examples/transaction.dump"
    ```

