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


<table>
  <thead>
    <tr>
      <th>Field</th>
      <th>Type</th>
      <th>Required</th>
      <th>Default value</th>
      <th>Contains</th>
      <th>Validation</th>
      <th>Valid example</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>message_type</td>
      <td>str[int]</td>
      <td>Yes</td>
      <td>-</td>
      <td>Transaction Message Type Identifier</td>
      <td>Length is exact 4<br>Digits only<br>Field exists in Specification</td>
      <td><code>0200</code></td>
    </tr>
    <tr>
     <td>max_amount</td>
     <td>str[int]</td>
     <td>No</td>
     <td>100</td>
     <td>Maximum generated transaction amount</td>
     <td>Digits only</td>
     <td><code>100</code></td>
    </tr>
    <tr>
     <td>generate_fields</td>
     <td>list[str[int]]</td>
     <td>No</td>
     <td>[ ]</td>
     <td>Field numbers to generate</td>
     <td>Digits only</td>
     <td><code>["4", "11", "37"]</code></td>
    </tr>
    <tr>
     <td>data_fields</td>
     <td>dict[str, str | dict]</td>
     <td>Yes</td>
     <td>-</td>
     <td>JSON-like transaction data fields representation</td>
     <td>According to the field specification</td>
     <td><pre><code class="language-json">{
 "3": "000000", 
 "11": "145787",
 "47": {
   "227": {
    "01": "Limassol", 
    "03": "CYP", 
    "04": "3101"
   }
 }
}</code></pre></td>
</tr>
</tbody>
</table>


??? example "JSON transaction example"  
    ```json linenums="1"
    --8<-- "files/data_examples/transaction.json"
    ```

### INI

INI transaction fields representation. See more about INI format [here](https://en.wikipedia.org/wiki/INI_file)

INI format contains the following parts: sections, options, and options values

```ini linenums="1"
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

```ini linenums="1"
[MESSAGE]
F002 = [4000000000000000]  ; Correct
F003 = 000000              ; Incorrect
```

All the fields numbers in the section [MESSAGE] must start from F. E.g. F002

```ini linenums="1"
[MESSAGE]
F002 = [4000000000000000]  ; Correct
3    = [000000]            ; Incorrect
```

INI transaction data contains up to three sections

| Section    | Required | Contains                                                                 |
|------------|----------|--------------------------------------------------------------------------|
| [MTI]      | Yes      | Transaction Message Type Identifier                                      |
| [CONFIG]   | No       | Transaction configuration params such as MAX_AMOUNT and GENERATE_FIELDS  |
| [MESSAGE]  | Yes      | Message body, contains data fields values                                |


The sections should be filled according to the data model 

| Section     | Option                         | Type      | Required   | Default value | Contains                                          | Validation                                        | Valid example                                                        | 
|-------------|--------------------------------|-----------|------------|---------------|---------------------------------------------------|---------------------------------------------------|----------------------------------------------------------------------|
| [MTI]       | MTI                            | str[int]  | Yes        | -             | Transaction Message Type Identifier               | lenght is 4, digits only, exists in Specification | `[0200]`                                                             |
| [CONFIG]    | MAX_AMOUNT                     | str[int]  | No         | 100           | Maximum generated transaction amoun               | Digits only                                       | `[100]`                                                              |
| [CONFIG]    | GENERATE_FIELDS                | list[int] | No         | [ ]           | Field numbers to generate before send transaction | Digits only                                       | `[4, 11, 37]`                                                        |
| [MESSAGE]   | FNNN where NNN is field number | str       | yes        | -             | Transaction data fields                           | According to the field specification              | `F002 = [4000000000000000]`<br>`F003 = [000000]`<br>`;...`<br>`;...` |


!!! danger "% Substitution"
    Due to ConfigParser library restrictions the sign `%` in options values must be written as double percent, `%%` only

    Refer to the [ConfigParser docs](https://docs.python.org/3/library/configparser.html) for details 
    
    ```ini linenums="1"
    [MESSSAGE]
    F002 = [415481%%0001]  ; Correct, will display "415481%0001"
    F002 = [415481%0001]   ; Incorrect, will lead to parsing error
    ```

??? example "INI transaction example"
    ```ini linenums="1"
    --8<-- "files/data_examples/transaction.ini"
    ```

### DUMP

Dump is hex-encoded transaction message, ready to send to remote host by TCP/IP. It can be set as a single string or 
multi string value. The right side in ascii representation is optional and the Signal never reads it 

The transaction data in dump representation can be used in GUI or CLI mode. You can also generate the dump using GUI or 
API tools

The dump is raw transaction data, so, there is no any configuration or other additional field. MTI, Bitmap and all the 
fields value should be pre-calculated

??? example "DUMP transaction example"
    ```text linenums="1"
    --8<-- "files/data_examples/transaction.dump"
    ```
