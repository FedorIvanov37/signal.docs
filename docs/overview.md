## Signal general overview

The Signal simplifies the sending of banking card e-commerce transactions to banking card processing systems using a 
useful visual and program interface. It uses the ISO-8583 E-pay protocol for transaction sending rather than the PSP. 
It can be used during the Payment Systems certification test, for checking and setting up the system on the test 
environment, during the application development process, and so on

The Signal has three interfaces that lead to the single core: Graphic User Interface, HTTP Application Programming 
Interface (API), and Command-line interface (CLI). Generally speaking, they do the same things but use different points 
of interaction with their own specific features

Also, the Signal builds like a kit of weakly connected modules, like a Parser, Connector, Queue, etc. It allows to 
reuse or extend the Signal's functionality, making emulators, loaders, parsers, converters, application interfaces, 
and many other things based on [Signal modules](#library-re-usage) 

In case of any questions about the Signal [contact the author](#author). Your feedback and suggestions are general 
drivers of the Signal evolution

## Restriction

* Allowed usage on test environment only. Signal only implements basic security checks
* At the moment Signal doesn't support byte-fields
* Graphic User Interface mode tests were made on Windows 10/11 x64 only
* The application and the document are currently under construction
