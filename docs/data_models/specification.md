# Specification

## Signal fields Specification

Signal has internal set of constants also known as a Specification. The Specification is JSON set of every field 
properties such as field data type, field length, fields validators and so os

The Specification has the following parts

| Part   | Type                | Required | Default value                | Description                           |
|--------|---------------------|----------|------------------------------|---------------------------------------|
| name   | str                 | No       | ISO-8583 E-pay Specification | Speficication name, any string        |
| mti    | list[str[int]]      | No       | [ ]                          | List of known message type indicators |
| fields | dics[str, IsoField] | No       | { }                          | IsoField set                          | 

## Validators

Field properties set, which shows validations, applicable to the field and those validations parameters

| Validator              | Type              | Check                                                    | Example                | Comment                           |
|------------------------|-------------------|----------------------------------------------------------|------------------------|-----------------------------------|
| field_type             | FieldTypes        | Field contains valid field type                          | MERCHANT CATEGORY CODE |                                   |
| date_format            | str               | Field contains data in defined format                    | %Y%M%D                 | Python-datetime style             |
| min_value              | int               | Mininun field value                                      | 100                    | Applicable for digit fields only  |
| max_value              | int               | Maximum field value                                      | 100                    | Applicable for digit fields only  |
| must_not_contain       | list[str]         | Field does not content value from list                   | ["some", "values"]     |                                   |
| possible_values        | list[str]         | Field can content one of the value from list             | ["some", "values"]     |                                   |
| must_start_with        | list[str]         | Field content starts with one of the value from list     | ["some", "values"]     |                                   |
| must_end_with          | list[str]         | Field content ends with one of the value from list       | ["some", "values"]     |                                   |
| must_contain           | list[str]         | Field content value from list                            | ["some", "values"]     |                                   |
| valid_values           | list[str]         | Field content value from list only                       | ["some", "values"]     |                                   |
| invalid_values         | list[str]         | Field content value not from list only                   | ["some", "values"]     |                                   |
| must_contain_only      | list[str]         | Field content value from list                            | ["some", "values"]     |                                   |
| must_not_end_with      | list[str]         | Field content not ends with one of the value from list   | ["some", "values"]     |                                   |
| must_not_start_with    | list[str]         | Field content not starts with one of the value from list | ["some", "values"]     |                                   |
| must_not_contain_only  | list[str]         | Field not content value not from list only               | ["some", "values"]     |                                   |
| justification          | Justification     | Fill field data side                                     | "RIGHT"                |                                   |
| justification_element  | str               | Data fo fill field data side                             | "0"                    |                                   |
| justification_length   | int               | Fill field data side up to length                        | 16                     |                                   |
| field_type_validators  | LogicalValidators | Validate field on some dictionary includement            | ["some", "values"]     |                                   |
|                        |                   |                                                          | ["some", "values"]     |                                   |


## Logical Validators
....



## Justification

| Justification | Description            |
|---------------|------------------------|
| LEFT          | Put data on left side  |
| RIGHT         | Put data on right side |


## IsoField
The IsoField is fields properties 