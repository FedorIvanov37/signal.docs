## Signal general overview


![image](/images/main_window.png)

Signal provides graphical and programmatic interfaces for sending e-commerce card transactions to card processing 
systems. It sends transactions using the ISO 8583 E-pay protocol.

Signal can be used for payment system certification testing, system checks and configuration in test environments, 
and application development.

!!! danger "Restrictions" 
    * For use in test environments only. Signal implements only basic security checks
    * Signal does not currently support byte fields
    * The graphical user interface has been tested only on Windows 10/11 x64
    * The application and this documentation are under development

## Interfaces

Signal has three interfaces that share a single core.

* [Graphical User Interface](/gui)
* [Command-Line Interface](/cli)
* [HTTP Application Programming Interface](/api) 

The interfaces provide the same core functionality, each with its own interaction model and features.

## Python library

Signal is built from loosely coupled modules, such as Parser, Connector, and Queue. You can reuse or extend these 
modules to build emulators, loaders, parsers, converters, application interfaces, and other tools with the 
[Signal library](/lib).

If you have any questions about Signal, [contact the author](/general/author). Your feedback and suggestions 
help shape its development.
