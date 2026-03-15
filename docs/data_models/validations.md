# Validations

## Validation data models

This chapter contains validation data models

## Validators

Field properties, showing validations applicable to the field and their parameters

| Validator              | Type                                                              | Check                                                             | Example                | Comment                           |
|------------------------|-------------------------------------------------------------------|-------------------------------------------------------------------|------------------------|-----------------------------------|
| field_type             | [FieldTypes](/data_models/dictionaries/#field-types)              | Field contains valid field type                                   | MERCHANT CATEGORY CODE |                                   |
| date_format            | str                                                               | Field must contain data in defined format                         | %y%M                   | Python-datetime style             |
| min_value              | int                                                               | Mininun field value                                               | 100                    | Applicable for digit fields only  |
| max_value              | int                                                               | Maximum field value                                               | 100                    | Applicable for digit fields only  |
| must_not_contain       | list[str]                                                         | Field must not content values from list                           | ["some", "values"]     |                                   |
| possible_values        | list[str]                                                         | Field value must be in list                                       | ["some", "values"]     |                                   |
| must_start_with        | list[str]                                                         | Field content must start with one of the value from list          | ["some", "values"]     |                                   |
| must_end_with          | list[str]                                                         | Field content must end with one of the value from list            | ["some", "values"]     |                                   |
| must_contain           | list[str]                                                         | Field content must have at least one value from list              | ["some", "values"]     |                                   |
| valid_values           | list[str]                                                         | Field content value must be in list                               | ["some", "values"]     |                                   |
| invalid_values         | list[str]                                                         | Field content value must be not in list                           | ["some", "values"]     |                                   |
| must_contain_only      | list[str]                                                         | Field content value must be in list                               | ["some", "values"]     |                                   |
| must_not_end_with      | list[str]                                                         | Field content value must not ends with one of the value from list | ["some", "values"]     |                                   |
| must_not_start_with    | list[str]                                                         | Field content must not start with one of the value from list      | ["some", "values"]     |                                   |
| must_not_contain_only  | list[str]                                                         | Field content must have value not from list                       | ["some", "values"]     |                                   |
| justification          | [Justification](/data_models/dictionaries/#justification)         | Fill field data side                                              | "RIGHT"                |                                   |
| justification_element  | str                                                               | Data for fill field data side                                     | "0"                    |                                   |
| justification_length   | int                                                               | Fill field data side up to length                                 | 16                     |                                   |
| field_type_validators  | [LogicalValidators](/data_models/validations/#logical-validators) | Validate field on some dictionary includement                     | ["some", "values"]     |                                   |



## Logical validators



This group of complex validations checks calculated, logical values, such as the Luhn algorithm, present/past tense, 
inclusion of a field value in a dictionary, etc

| Validator         | Type | Check                                                                                                 | Example | Comment                                  |
|-------------------|------|-------------------------------------------------------------------------------------------------------|---------|------------------------------------------|
| currency_a3       | bool | Field content must be in [Currency A3](/data_models/dictionaries/#currencies-list)                    | true    |                                          |
| currency_n3       | bool | Field content must be in [Currency N3](/data_models/dictionaries/#currencies-list)                    | true    |                                          |
| country_a3        | bool | Field content must be in [Country A3](/data_models/dictionaries/#countries-list)                      | true    |                                          |
| country_a2        | bool | Field content must be in [Country A2](/data_models/dictionaries/#countries-list)                      | true    |                                          |
| country_n3        | bool | Field content must be in [Country N3](/data_models/dictionaries/#countries-list)                      | true    |                                          |
| mcc               | bool | Field content must be in [Merchant Categoty Code](/data_models/dictionaries/#merchant-category-codes) | true    |                                          |
| date_format       | str  | Field content must be in date format                                                                  | %Y%m    | Python datetime style                    |
| past              | bool | Field past time allowed                                                                               | true    | Works only when date_format is specified |
| present           | bool | Field present time allowed                                                                            | true    | Works only when date_format is specified |
| future            | bool | Field future time allowed                                                                             | true    | Works only when date_format is specified |
| check_luhn        | bool | Field content must pass Luhn alghorithm check                                                         | true    |                                          |
| only_upper        | bool | Field must content uppercase only                                                                     | true    |                                          |
| only_lower        | bool | Field must content lowercase only                                                                     | true    |                                          |
| change_to_upper   | bool | Modify field data set uppercase value                                                                 | false   |                                          |
| change_to_lower   | bool | Modify field data set lowercase value                                                                 | false   |                                          |
| do_not_validate   | bool | Skip all validations and modifications                                                                | true    |                                          |


## Validators example

??? example "Validators example"
    ```json linenums="1"
    --8<-- "files/data_examples/validators.json"
    ```
