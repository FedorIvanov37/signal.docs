# Combinations

## Command line keys combinations

It is possible to combine CLI keys together to run some CLI scenario. In this chapter you can find some combinations but 
this is not all the list

| Command                                                  | Meaning                                                              |
|----------------------------------------------------------|----------------------------------------------------------------------|
| `signal.exe --console --default`                         | Send default transaction to the host                                 |
| `signal.exe --console --echo-test`                       | Send echo-test to the host                                           |
| `signal.exe --console --echo-test --repeat --interval 2` | Begin transaction loop, sending new echo-test every 2 sec            |
| `signal.exe --console --dir /transactions --parallel`    | Immediate send all the transactions from the directory /transactions |
| `signal.exe --console --api-mode`                        | Run Signal in console API mode                                       |

!!! warning "Keys joining is not supported"
    Each key should be entered separately, with no joining them together
    
    ```text

    signal.exe -c -r -i 10 --default  # Correct, will send default message with repeat

    signal.exe -cri 10 --default`     # Incorrect, will not work as expected

    ```
