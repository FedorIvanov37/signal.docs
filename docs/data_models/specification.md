# Specification

## Signal fields Specification

Signal has internal set of constants also known as a Specification. The Specification is JSON set of every field 
properties such as field data type, field length, fields validators and so os

The Specification has the following parts

| Part   | Type                                                                                 | Required | Default value                | Description                           |
|--------|--------------------------------------------------------------------------------------|----------|------------------------------|---------------------------------------|
| name   | str                                                                                  | No       | ISO-8583 E-pay Specification | Speficication name, any string        |
| mti    | list[[Message Type Indicators](/data_models/specification/#message-type-indicators)] | No       | [ ]                          | List of known message type indicators |
| fields | dics[str, [IsoField](/data_models/specification/#isofield)]                          | No       | { }                          | IsoField set                          | 

## IsoField
| Property            | Type                                                        | Description                                           | Example             |
|---------------------|-------------------------------------------------------------|-------------------------------------------------------|---------------------|
| Validators          | [Validators](/data_models/validations/#validators)          | Field validation rules set                            |                     |
| field_number        | str[int]                                                    | Field number                                          | "4"                 |
| field_path          | list[str[int]]                                              | Field hierarhy path                                   | ["47", "227", "01"] |
| min_length          | int                                                         | Minimal field length                                  | 16                  |
| max_length          | int                                                         | Maximum field length                                  | 19                  |
| var_length          | int                                                         | Field onw variable length                             | 2                   |
| tag_length          | int                                                         | Field subtag length                                   | 3                   |
| generate            | bool                                                        | Generate field value possible                         | true                |
| reversal            | bool                                                        | Take field value from orginal when process a reversal | false               |
| matching            | bool                                                        | Field is transactions matching participant            | true                |
| alpha               | bool                                                        | Field can content letters                             | true                |
| numeric             | bool                                                        | Field can content numbers                             | true                |
| special             | bool                                                        | Field can content special symbols %, ^, and so on     | true                |
| reserved_for_future | bool                                                        | Field reserver for future                             | true                |
| description         | str                                                         | Field name or description                             | true                |
| is_secret           | bool                                                        | Field content sensetive data                          | true                |
| is_utrnno           | bool                                                        | Field content transaction ID                          | true                |
| fields              | dict[str, [IsoField](/data_models/specification/#isofield)] | Subfields set                                         |                     |


## Message Type Indicators

| Field         | Type      | Description                        |
|---------------|-----------|------------------------------------|
| request       | str[int]  | Message type indicator             |
| response      | str[int]  | Message type indicator             |
| description   | str       | Message type indicator Description |
| is_reversible | bool      | Transaction type can be reversed   |
| reversal_mti  | str[int]  | Message type indicator             |


# Specification example

??? example "Specification data example"
    ```json linenums="1"
    --8<-- "files/data_examples/specification.json"
    ```
