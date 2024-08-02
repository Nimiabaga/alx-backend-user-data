# 0x00. Personal Data Management

## Description

This project focuses on handling and managing Personally Identifiable Information (PII) in a secure and responsible manner. The key objectives are to understand what constitutes PII, how to implement a log filter to obfuscate sensitive data, encrypt passwords, and authenticate to a database securely.

## Learning Objectives

By the end of this project, you will be able to:

1. Identify examples of Personally Identifiable Information (PII).
2. Implement a log filter that obfuscates PII fields.
3. Encrypt a password and check the validity of an input password.
4. Authenticate to a database using environment variables.

## Requirements

- All files will be interpreted/compiled on Ubuntu 18.04 LTS using Python 3.7.
- All files should end with a new line.
- The first line of all files should be exactly `#!/usr/bin/env python3`.
- A `README.md` file at the root of the project folder is mandatory.
- Your code should follow the `pycodestyle` style (version 2.5).
- All files must be executable.
- The length of your files will be tested using `wc`.
- All modules should have documentation (`python3 -c 'print(__import__("my_module").__doc__)'`).
- All classes should have documentation (`python3 -c 'print(__import__("my_module").MyClass.__doc__)'`).
- All functions (inside and outside a class) should have documentation (`python3 -c 'print(__import__("my_module").my_function.__doc__)'` and `python3 -c 'print(__import__("my_module").MyClass.my_function.__doc__)'`).
- All functions should be type-annotated.

## Tasks

### Task 0: Regex-ing

Write a function called `filter_datum` that returns the log message obfuscated.

#### Arguments:
- `fields`: A list of strings representing all fields to obfuscate.
- `redaction`: A string representing what the field will be obfuscated with.
- `message`: A string representing the log line.
- `separator`: A string representing the character that separates all fields in the log line.

The function should use a regex to replace occurrences of certain field values.

Example usage:
```python
fields = ["password", "date_of_birth"]
messages = ["name=egg;email=eggmin@eggsample.com;password=eggcellent;date_of_birth=12/12/1986;", "name=bob;email=bob@dylan.com;password=bobbycool;date_of_birth=03/04/1993;"]

for message in messages:
    print(filter_datum(fields, 'xxx', message, ';'))

