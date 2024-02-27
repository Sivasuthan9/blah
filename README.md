## `ir` Command

The `ir` command generates an Abstract Syntax Tree (AST) and SymbolTable tree for a .jac file, or a Python AST for a .py file.

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
