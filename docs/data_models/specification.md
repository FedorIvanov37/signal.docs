# Specification

## Signal fields Specification

Signal has an internal set of constants known as the Specification. It defines each field's properties, 
including its data type, length, and validation rules.

The Specification data fields are listed below.

| Part   | Type                                                                                 | Required | Default value                | Description                           |
|--------|--------------------------------------------------------------------------------------|----------|------------------------------|---------------------------------------|
| name   | str                                                                                  | No       | ISO-8583 E-pay Specification | Specification name; any string        |
| mti    | list[[Message Type Indicators](/data_models/specification/#message-type-indicators)] | No       | [ ]                          | List of known message type indicators |
| fields | dics[str, [IsoField](/data_models/specification/#isofield)]                          | No       | { }                          | IsoField set                          | 

## IsoField

IsoField defines a set of field properties. Provide these properties for each known field.

| Property            | Type                                                        | Description                                           | Example             |
|---------------------|-------------------------------------------------------------|-------------------------------------------------------|---------------------|
| Validators          | [Validators](/data_models/validations/#validators)          | Field validation rules                            |                     |
| field_number        | str[int]                                                    | Field number                                          | "4"                 |
| field_path          | list[str[int]]                                              | Field path in the hierarchy                                   | ["47", "227", "01"] |
| min_length          | int                                                         | Minimum field length                                  | 16                  |
| max_length          | int                                                         | Maximum field length                                  | 19                  |
| var_length          | int                                                         | Field's own variable-length prefix                             | 2                   |
| tag_length          | int                                                         | Subtag length                                   | 3                   |
| generate            | bool                                                        | Whether the field value can be generated                         | true                |
| reversal            | bool                                                        | Copy the field value from the original transaction when processing a reversal | false               |
| matching            | bool                                                        | Whether the field is used for transaction matching            | true                |
| alpha               | bool                                                        | Field can contain letters                             | true                |
| numeric             | bool                                                        | Field can contain numbers                             | true                |
| special             | bool                                                        | Field can contain special characters such as % and ^     | true                |
| reserved_for_future | bool                                                        | Field is reserved for future use                             | true                |
| description         | str                                                         | Field name or description                             | true                |
| is_secret           | bool                                                        | Field contains sensitive data                          | true                |
| is_utrnno           | bool                                                        | Field contains the transaction ID                          | true                |
| fields              | dict[str, [IsoField](/data_models/specification/#isofield)] | Set of subfields                                         |                     |


## Message Type Indicator

A message type indicator object defines an allowed request/response MTI pair and its properties.

| Field         | Type      | Description                        |
|---------------|-----------|------------------------------------|
| request       | str[int]  | Message type indicator             |
| response      | str[int]  | Message type indicator             |
| description   | str       | Message type indicator description |
| is_reversible | bool      | Transaction type can be reversed   |
| reversal_mti  | str[int]  | Message type indicator             |


# Specification example

??? example "Specification data example"
    ```json linenums="1"
    --8<-- "files/data_examples/specification.json"
    ```
