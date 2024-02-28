# Jac Language Command Line Interface (CLI)

Jac Language CLI is with a variety of commands to facilitate users. Additionally, Jac language offers users the ability to define custom CLI commands through plugins. This document aims to provide an overview of each command along with clear usage instructions.

### Below are avilable Commands
- [tool](#tool), [format](#installation), [run](#getting-started), [build](#syntax), [check](#examples), [enter](#contributing), [test](#license), [clean](#license)
  
## Command `tool`:
## tool
The `tool` command is utilized to execute specific AST tools along with any optional arguments as needed. This command enables users to interact with language-specific command line tools designed to manage the language effectively.
### Usage:
```bash
$ jac tool <jac_tool> <args>
```
  Parameters to execute the tool command:
  - `jac_tool`: The name of the AST tool to execute.
  - `args`: Optional arguments for the specific AST tool.

  ## 1. tool `ir`:
   `ir` tool generates an Abstract Syntax Tree (AST) and SymbolTable tree for a .jac file, or a Python AST for a .py file. `ir` tool is used with `tool` cli command.
  ### Usage
  ```bash
  $ jac tool ir <output> <file_path>
  ```
  Parameters to use the ir tool:
  - `output`: Choose one of the following options:
    - `sym`: Displays the symbol table of the specified .jac file.
    - `sym.`: Generates a dot graph representation of the symbol table for the specified .jac file.
    - `ast` : Displays the Abstract Syntax Tree (AST) of the specified .jac file.
    - `ast.`: Generates a dot graph representation of the AST for the specified .jac file.
    - `pyast`: Generates the Python AST for a .py file or  Generates equivalent Python AST for a .jac file.
    - `py`: Generates the relevant Python code for the respective Jac code for a .jac file.
  - `file_path`: Path to the .jac or .py file.

  ### Examples
  To get the symbol table tree of a Jac file:
  ```bash
  $ jac tool ir sym <file_path>
  ```
  To generate a dot graph of the symbol table tree for a Jac file:
  ```bash
  $ jac tool ir sym. <file_path>
  ```
  To view the AST tree of a Jac file:
  ```bash
  $ jac tool ir ast <file_path>
  ```

