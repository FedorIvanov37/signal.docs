# Combinations

## Command line keys combinations

You can combine CLI options to perform different tasks. This chapter shows some common combinations; 
it is not an exhaustive list.

| Command                                                  | Meaning                                                              |
|----------------------------------------------------------|----------------------------------------------------------------------|
| `signal.exe --console --default`                         | Send the default transaction to the host                                 |
| `signal.exe --console --echo-test`                       | Send echo-test to the host                                           |
| `signal.exe --console --echo-test --repeat --interval 2` | Start a loop that sends a new echo-test every 2 seconds            |
| `signal.exe --console --dir /transactions --parallel`    | Immediately send all transactions from the /transactions directory |
| `signal.exe --console --api-mode`                        | Run Signal in console API mode                                       |

!!! warning "Combined short options are not supported"
    Enter each option separately; do not combine short options.
    
    ```text

    signal.exe -c -r -i 10 --default  # Correct, will send default message with repeat

    signal.exe -cri 10 --default`     # Incorrect, will not work as expected

    ```
