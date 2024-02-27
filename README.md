# Jac Language Command Line Interface (CLI)

The Jac Language CLI offers a variety of commands to facilitate Jac programming tasks efficiently. This document provides an overview of each command along with its usage instructions.

## ir Command

The `ir` command generates an Abstract Syntax Tree (AST) and SymbolTable tree for a .jac file, or a Python AST for a .py file.

### Usage

```bash
$ jac tool ir <output_type> <file_path>
