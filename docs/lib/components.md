# Library Components

The Signal library is built around three main types of components. Each group has its own purpose, and together they 
form the complete internal architecture of the project.

- [Constants](/lib/constants) — immutable read-only values used for stable application settings and internal rules

- [Data models](/lib/data_modules) — Pydantic structures used to store, validate, and transfer business data inside the application

- [Program modules](/lib/program_modules) — functional components that process data, execute logic, and perform transaction operations


Understanding these components makes the library easier to use and helps when building custom integrations or extending 
existing functionality.

Program modules exchange data using Pydantic models and process that data using rules defined by constants.

In simple terms:

-  Constants define the rules
-  Data models store the data
-  Program modules perform the work

This separation makes the library predictable, reusable, and much easier to maintain.
