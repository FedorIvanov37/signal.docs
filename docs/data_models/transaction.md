# Transaction

## Transaction data

The Transaction data model is the central dataset used by Signal to represent payment transactions. Each request and 
response is represented as a separate Transaction object.

Signal receives transactions from multiple sources (files, API, TCP sockets, GUI), converts them into the internal 
Transaction model, processes them in the Signal Core, and routes them to the appropriate destination.

After processing, the Transaction can be converted to a target format and returned via various interfaces, such as a 
GUI, an API response, CLI output, or a TCP connection.

See [Data models](/data_models) for how to load transaction data in each Signal operating mode.

## Transaction format

Signal supports three transaction data formats.

| Data format | File extension    | Supported in  | Comment                             |
|-------------|-------------------|---------------|-------------------------------------|
| JSON        | `.json`           | GUI, CLI, API | Recommended transaction data format |
| DUMP        | `.dump` or `.txt` | GUI, CLI      |                                     |
| INI         | `.ini`            | GUI, CLI      |                                     |

If the Signal GUI cannot identify a transaction file by its extension, it tries each supported format. 
See the [data exchange](/gui/features/data_exchange) chapter for details.

## Transaction data model

### JSON

The table below describes the Transaction data fields. Transaction is the internal data model, so other formats, 
such as DUMP and INI, are converted to it for further processing.

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
      <td>Length is exactly 4<br>Digits only<br>Field exists in the specification</td>
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
     <td>Numbers of fields to generate</td>
     <td>Digits only</td>
     <td><code>["4", "11", "37"]</code></td>
    </tr>
    <tr>
     <td>data_fields</td>
     <td>dict[str, str | dict]</td>
     <td>Yes</td>
     <td>-</td>
     <td>JSON-like representation of transaction fields</td>
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

Transaction fields can also be represented in INI format. Learn more about INI [here](https://en.wikipedia.org/wiki/INI_file).

INI files contain sections, options, and option values.

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

Enclose all option values in square brackets, like [this].

```ini linenums="1"
[MESSAGE]
F002 = [4000000000000000]  ; Correct
F003 = 000000              ; Incorrect
```

All field numbers in the [MESSAGE] section must start with F, for example F002.

```ini linenums="1"
[MESSAGE]
F002 = [4000000000000000]  ; Correct
3    = [000000]            ; Incorrect
```

An INI transaction contains up to three sections.

| Section    | Required | Contains                                                                 |
|------------|----------|--------------------------------------------------------------------------|
| [MTI]      | Yes      | Transaction Message Type Identifier                                      |
| [CONFIG]   | No       | Transaction configuration parameters, such as MAX_AMOUNT and GENERATE_FIELDS  |
| [MESSAGE]  | Yes      | Message body containing field values                                |


Fill in the sections according to the data model below.

| Section     | Option                         | Type      | Required   | Default value | Contains                                          | Validation                                        | Valid example                                                        | 
|-------------|--------------------------------|-----------|------------|---------------|---------------------------------------------------|---------------------------------------------------|----------------------------------------------------------------------|
| [MTI]       | MTI                            | str[int]  | Yes        | -             | Transaction Message Type Identifier               | Length is 4, digits only, exists in the specification | `[0200]`                                                             |
| [CONFIG]    | MAX_AMOUNT                     | str[int]  | No         | 100           | Maximum generated transaction amount               | Digits only                                       | `[100]`                                                              |
| [CONFIG]    | GENERATE_FIELDS                | list[int] | No         | [ ]           | Numbers of fields to generate before sending the transaction | Digits only                                       | `[4, 11, 37]`                                                        |
| [MESSAGE]   | FNNN where NNN is field number | str       | yes        | -             | Transaction data fields                           | According to the field specification              | `F002 = [4000000000000000]`<br>`F003 = [000000]`<br>`;...`<br>`;...` |


!!! danger "% Substitution"
    The ConfigParser library requires percent signs in option values to be escaped: write `%%` instead of `%`.

    Refer to the [ConfigParser docs](https://docs.python.org/3/library/configparser.html) for details.
    
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

A dump is a hex-encoded transaction message, ready to be sent to a remote host over TCP/IP. It can occupy a single 
line or multiple lines. The ASCII representation on the right is optional; Signal does not read it.

Transaction dumps can be used in GUI or CLI mode. You can also generate a dump using the GUI 
or API tools.

A dump contains raw transaction data, with no configuration or other additional fields. The MTI, bitmap, and all 
field values must be calculated in advance.

??? example "DUMP transaction example"
    ```text linenums="1"
    --8<-- "files/data_examples/transaction.dump"
    ```
