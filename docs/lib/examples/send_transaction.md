# Send transaction

## Case

You already have a transaction file prepared in JSON format based on the [Transaction](/data_models/transaction) data model. If not, refer 
to the transaction [building guide](/lib/examples/create_transaction).

If needed, Signal also supports transaction conversion between all supported formats, including `DUMP`, `INI`, and `JSON`. 
The conversion workflow is described in the corresponding examples of this section.

??? example "JSON transaction example"  
    ```json linenums="1"
    --8<-- "files/data_examples/transaction.json"
    ```

## Solution

In this scenario, the goal is simple — load the prepared transaction, generate dynamic fields if required, and 
send it to the remote host.

Use the following code:

```python
# Your file with JSON transaction data
INCOMING_TRANSACTION_FILE_NAME = "transaction_request_example.json"  

# To process this case we need
#  • TermFilesPath constants set to get the config file info
#  • Config data model to load the configuration data from the file
#  • Transaction data model load the transaction data from the file
#  • Terminal as a transaction processing system
# 
# Let's import all of this components

from common.lib.enums.TermFilesPath import TermFilesPath  # System files path to read the configuration
from common.lib.data_models.Config import Config  # Configuration data container
from common.lib.data_models.transaction import Transaction  # Transaction data container
from common.lib.core.Terminal import Terminal  # General transactions processing interface

# Start the processing

# Load the data from transaction file to transaction data model
transaction: Transaction = Transaction(INCOMING_TRANSACTION_FILE_NAME)  

# Load the data from configuration file to config data model
config: Config = Config(TermFilesPath.CONFIG)  

# Create Terminal object
terminal: Terminal = Terminal(config)   

# Terminal reads the data using data models only, not from the files directly
# Now we have the transaction data, accessible using the data model and started Terminal as the processing tool
# Let's send transaction to the host

terminal.send(transaction)

# Done
```

