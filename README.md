# Jac Language Command Line Interface (CLI)

The Jac Language CLI offers a variety of commands to facilitate Jac programming tasks efficiently. Additionally, Jac language offers users the ability to define custom CLI commands through plugins. This document aims to provide an overview of each command along with clear usage instructions.

### Usage

## 1. `tool` Command:

The `tool` command is utilized to execute specific AST tools along with any optional arguments as needed. This command enables users to interact with language-specific command line tools designed to manage the language effectively.

### Parameters:
- `tool`: The name of the AST tool to run.
- `args`: Optional arguments for the AST tool.

### Arguments:
- `tool`: str
- `args`: Optional

### Usage:
```bash
CLI tool [-h] tool ...
```
The `ir` command generates an Abstract Syntax Tree (AST) and SymbolTable tree for a .jac file, or a Python AST for a .py file.
### Usage

```bash
$ jac tool ir <output_type> <file_path>
```
### Parameters

- `output_type`: Choose one of the following options:
  - `sym`: Provides the symbol table of the specified .jac file.
  - `sym.`: Generates a dot graph representation of the symbol table for the specified .jac file.
  - `ast`: Displays the Abstract Syntax Tree (AST) of the specified .jac file.
  - `ast.`: Generates a dot graph representation of the AST for the specified .jac file.
  - `pyast`: Generates the Python AST for a .py file or the relevant Python AST for the generated Python code from a .jac file.
  - `py`: Displays the relevant generated Python code for the respective Jac code in a .jac file.
- `file_path`: Path to the .jac or .py file.

### Examples

To get the symbol table of a Jac file:
```bash
$ jac tool ir sym <file_path>
```

To generate a dot graph of the symbol table for a Jac file:
```bash
$ jac tool ir sym. <file_path>
```

To view the AST of a Jac file:
```bash
$ jac tool ir ast <file_path>
```

To generate a dot graph of the AST for a Jac file:
```bash
$ jac tool ir ast. <file_path>
```

To generate the Python AST for a .py file or the relevant Python AST for the generated Python code from a .jac file:
```bash
$ jac tool ir pyast <file_path>
```


