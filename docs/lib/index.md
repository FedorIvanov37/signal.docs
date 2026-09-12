# Python library

## Introduction

Signal is not only a standalone application with GUI, API, and CLI interfaces — it is also a reusable Python library 
built around a set of independent modules. The same internal components used by the application can be imported and 
used directly in your own projects.

This approach allows Signal to be used not only as a transaction sender, but also as a toolkit for building custom 
ISO 8583 automation solutions: transaction generators, parsers, validators, loaders, converters, test utilities, and 
integration services.

The library is designed around loosely coupled modules such as Terminal, Parser, Connector, Queue, FieldsGenerator, 
and Pydantic-based data models. These modules can work together as a complete transaction processing chain or be used 
separately to solve individual tasks.

For example, you may use Signal for:

* Generating dynamic transaction fields such as STAN, transmission date, or transaction IDs
* Parsing raw host dumps into a structured JSON representation
* Validating transaction files against specification rules
* Building custom test runners for certification scenarios
* Creating lightweight ISO 8583 service emulators
* Integrating transaction sending into CI/CD pipelines or automated test environments

Signal follows a practical engineering approach: simple things should remain simple. Instead of requiring a full 
processing simulator or a heavy certification environment, the library gives direct access to the core transaction 
workflow with minimal overhead.

Since Signal internally uses both PyQt6 and Pydantic, basic familiarity with these libraries is recommended before integrating them extensively. However, even without using the GUI, the library can be used in lightweight console scripts and backend 
services with minimal setup.

In the following sections, we will cover installation requirements, module structure, configuration basics, and minimal 
working examples of how to use the library.
