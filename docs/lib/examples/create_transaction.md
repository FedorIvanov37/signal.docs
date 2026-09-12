# Create Transaction

## Case

You have only the business data required for the operation, such as the card number, expiration date, amount, terminal 
parameters, and other transaction fields.

The final result should be a transaction file in `JSON` format based on the unified `Transaction` data model. This file 
can be used everywhere in Signal: loaded into the GUI, sent through the API, processed in CLI mode, or used directly by the 
Python library.

Because all interfaces work with the same `Transaction` model, the created file remains fully compatible across the 
entire system.

The goal is to create a valid transaction file that can be used for processing, as shown in the example below.

??? example "JSON transaction example"  
    ```json linenums="1"
    --8<-- "files/data_examples/transaction.json"
    ```

## Solution

There are three main ways to create such a transaction file.

### 1. Create through GUI

Open the Main Window, manually fill in the required fields, then press `Ctrl + S` or use the `Save File` button, choose 
an output folder and `JSON` format.

This is the most convenient method for manual work, testing, and preparing new transactions during certification or 
debugging.

### 2. Create manually

You can manually prepare the transaction file using any text editor such as Notepad.

Signal supports `JSON`, `INI`, and `DUMP` formats. In most cases, JSON is recommended because it is readable, 
structured, and fully compatible with all system interfaces.

Manual creation is not recommended. Signal provides many tools to work with transaction data.

### 3. Convert from existing transaction data

If you already have a transaction in `INI` or `DUMP` format or an SV dump, it can be converted into a JSON 
representation.

This is often used when working with raw host dumps, legacy files, or imported certification examples.

Transaction conversion between supported formats is described in a separate chapter of this section.
