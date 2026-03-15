# Validations

## Validation data models

This chapter contains validation data models

## Logical Validators

This property refers that the field contents one of the dictionaries value

| Validator         | Type | Check                                                                                       | Example | Comment                                  |
|-------------------|------|---------------------------------------------------------------------------------------------|---------|------------------------------------------|
| currency_a3       | bool | Field contents [Currency A3](/data_models/dictionaries/#currencies-list)                    | true    |                                          |
| currency_n3       | bool | Field contents [Currency N3](/data_models/dictionaries/#currencies-list)                    | true    |                                          |
| country_a3        | bool | Field contents [Country A3](/data_models/dictionaries/#countries-list)                      | true    |                                          |
| country_a2        | bool | Field contents [Country A2](/data_models/dictionaries/#countries-list)                      | true    |                                          |
| country_n3        | bool | Field contents [Country N3](/data_models/dictionaries/#countries-list)                      | true    |                                          |
| mcc               | bool | Field contents [Merchant Categoty Code](/data_models/dictionaries/#merchant-category-codes) | true    |                                          |
| date_format       | str  | Field date format for check time                                                            | %Y%m    | Python datetime style                    |
| past              | bool | Field contents past time                                                                    | true    | Works only when date_format is specified |
| present           | bool | Field contents present time                                                                 | true    | Works only when date_format is specified |
| future            | bool | Field contents future time                                                                  | true    | Works only when date_format is specified |
| check_luhn        | bool | Field content should pass Luhn alghorithm check                                             | true    |                                          |
| only_upper        | bool | Field contents uppercase only                                                               | true    |                                          |
| only_lower        | bool | Field contents lowercase only                                                               | true    |                                          |
| change_to_upper   | bool | Modify field data set uppercase value                                                       | true    |                                          |
| change_to_lower   | bool | Modify field data set lowercase value                                                       | true    |                                          |
| do_not_validate   | bool | Skip all validations and modifications                                                      | true    |                                          |


## Validators

Field properties set, which shows validations, applicable to the field and those validations parameters

| Validator              | Type                                                              | Check                                                    | Example                | Comment                           |
|------------------------|-------------------------------------------------------------------|----------------------------------------------------------|------------------------|-----------------------------------|
| field_type             | [FieldTypes](/data_models/dictionaries/#field-types)              | Field contains valid field type                          | MERCHANT CATEGORY CODE |                                   |
| date_format            | str                                                               | Field contains data in defined format                    | %Y%M%D                 | Python-datetime style             |
| min_value              | int                                                               | Mininun field value                                      | 100                    | Applicable for digit fields only  |
| max_value              | int                                                               | Maximum field value                                      | 100                    | Applicable for digit fields only  |
| must_not_contain       | list[str]                                                         | Field does not content value from list                   | ["some", "values"]     |                                   |
| possible_values        | list[str]                                                         | Field content one of the value from list                 | ["some", "values"]     |                                   |
| must_start_with        | list[str]                                                         | Field content starts with one of the value from list     | ["some", "values"]     |                                   |
| must_end_with          | list[str]                                                         | Field content ends with one of the value from list       | ["some", "values"]     |                                   |
| must_contain           | list[str]                                                         | Field content value from list                            | ["some", "values"]     |                                   |
| valid_values           | list[str]                                                         | Field content value from list only                       | ["some", "values"]     |                                   |
| invalid_values         | list[str]                                                         | Field content value not from list only                   | ["some", "values"]     |                                   |
| must_contain_only      | list[str]                                                         | Field content value from list                            | ["some", "values"]     |                                   |
| must_not_end_with      | list[str]                                                         | Field content not ends with one of the value from list   | ["some", "values"]     |                                   |
| must_not_start_with    | list[str]                                                         | Field content not starts with one of the value from list | ["some", "values"]     |                                   |
| must_not_contain_only  | list[str]                                                         | Field not content value not from list only               | ["some", "values"]     |                                   |
| justification          | [Justification](/data_models/validations/#justification)          | Fill field data side                                     | "RIGHT"                |                                   |
| justification_element  | str                                                               | Data fo fill field data side                             | "0"                    |                                   |
| justification_length   | int                                                               | Fill field data side up to length                        | 16                     |                                   |
| field_type_validators  | [LogicalValidators](/data_models/validations/#logical-validators) | Validate field on some dictionary includement            | ["some", "values"]     |                                   |


## Justification

| Justification | Description            |
|---------------|------------------------|
| LEFT          | Put data on left side  |
| RIGHT         | Put data on right side |
