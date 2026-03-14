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

## Data examples

Incoming transaction data examples

In UI mode you can put this data to some file, e.g. `transaction.json` and parse this file. Use hotkey `Ctrl + O`, 
button `Open File` or drop file to the MainWindow on Signal GUI to open the incoming transaction file

See [here](/data_models) how to read the transaction data in any Signal run mode

??? example "JSON"
    ```json
    --8<-- "files/data_examples/transaction.json"
    ```

??? example "INI"
    ```ini
    --8<-- "files/data_examples/transaction.ini"
    ```

??? example "DUMP"
    ```text
    --8<-- "files/data_examples/transaction.dump"
    ```

All the examples are ready to use

## Transaction data model

### JSON
