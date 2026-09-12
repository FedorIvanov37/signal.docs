# Validations

## Validation data models

This chapter describes the validation data models.

## Validators

These field properties define the applicable validation rules and their parameters.

| Validator              | Type                                                              | Check                                                             | Example                | Comment                           |
|------------------------|-------------------------------------------------------------------|-------------------------------------------------------------------|------------------------|-----------------------------------|
| field_type             | [FieldTypes](/data_models/dictionaries/#field-types)              | Field contains a value of the specified type                                   | MERCHANT CATEGORY CODE |                                   |
| date_format            | str                                                               | Field must contain data in the specified format                         | %y%M                   | Python datetime format             |
| min_value              | int                                                               | Minimum field value                                               | 100                    | Applies only to numeric fields  |
| max_value              | int                                                               | Maximum field value                                               | 100                    | Applies only to numeric fields  |
| must_not_contain       | list[str]                                                         | Field must not contain values from the list                           | ["some", "values"]     |                                   |
| possible_values        | list[str]                                                         | Field value must be in the list                                       | ["some", "values"]     |                                   |
| must_start_with        | list[str]                                                         | Field value must start with one of the listed values          | ["some", "values"]     |                                   |
| must_end_with          | list[str]                                                         | Field value must end with one of the listed values            | ["some", "values"]     |                                   |
| must_contain           | list[str]                                                         | Field must contain at least one listed value              | ["some", "values"]     |                                   |
| valid_values           | list[str]                                                         | Field value must be in the list                               | ["some", "values"]     |                                   |
| invalid_values         | list[str]                                                         | Field value must not be in the list                           | ["some", "values"]     |                                   |
| must_contain_only      | list[str]                                                         | Field value must be in the list                               | ["some", "values"]     |                                   |
| must_not_end_with      | list[str]                                                         | Field value must not end with any listed value | ["some", "values"]     |                                   |
| must_not_start_with    | list[str]                                                         | Field value must not start with any listed value      | ["some", "values"]     |                                   |
| must_not_contain_only  | list[str]                                                         | Field must contain a value that is not in the list                       | ["some", "values"]     |                                   |
| justification          | [Justification](/data_models/dictionaries/#justification)         | Field alignment                                              | "RIGHT"                |                                   |
| justification_element  | str                                                               | Padding data for field alignment                                     | "0"                    |                                   |
| justification_length   | int                                                               | Target length for field padding                                 | 16                     |                                   |
| field_type_validators  | [LogicalValidators](/data_models/validations/#logical-validators) | Check the field value against a dictionary                     | ["some", "values"]     |                                   |



## Logical validators



These validation rules check properties such as a Luhn checksum, whether a date is in the past or present, 
and whether a field value is listed in a dictionary.

| Validator         | Type | Check                                                                                                 | Example | Comment                                  |
|-------------------|------|-------------------------------------------------------------------------------------------------------|---------|------------------------------------------|
| currency_a3       | bool | Field value must be listed in [Currency A3](/data_models/dictionaries/#currencies-list)                    | true    |                                          |
| currency_n3       | bool | Field value must be listed in [Currency N3](/data_models/dictionaries/#currencies-list)                    | true    |                                          |
| country_a3        | bool | Field value must be listed in [Country A3](/data_models/dictionaries/#countries-list)                      | true    |                                          |
| country_a2        | bool | Field value must be listed in [Country A2](/data_models/dictionaries/#countries-list)                      | true    |                                          |
| country_n3        | bool | Field value must be listed in [Country N3](/data_models/dictionaries/#countries-list)                      | true    |                                          |
| mcc               | bool | Field value must be listed in [Merchant Category Code](/data_models/dictionaries/#merchant-category-codes) | true    |                                          |
| date_format       | str  | Field value must match the date format                                                                  | %Y%m    | Python datetime style                    |
| past              | bool | Allow dates in the past                                                                               | true    | Applies only when date_format is specified |
| present           | bool | Allow the current date/time                                                                            | true    | Applies only when date_format is specified |
| future            | bool | Allow dates in the future                                                                             | true    | Applies only when date_format is specified |
| check_luhn        | bool | Field value must pass the Luhn check                                                         | true    |                                          |
| only_upper        | bool | Field must contain uppercase characters only                                                                     | true    |                                          |
| only_lower        | bool | Field must contain lowercase characters only                                                                     | true    |                                          |
| change_to_upper   | bool | Convert the field value to uppercase                                                                 | false   |                                          |
| change_to_lower   | bool | Convert the field value to lowercase                                                                 | false   |                                          |
| do_not_validate   | bool | Skip all validations and modifications                                                                | true    |                                          |


## Validators example

??? example "Validators example"
    ```json linenums="1"
    --8<-- "files/data_examples/validators.json"
    ```
