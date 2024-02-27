# Jac Language Command Line Interface (CLI) Documentation

The Jac Language Command Line Interface (CLI) provides a comprehensive set of commands for working with Jac files and executing Jac programs efficiently. With a range of functionalities including formatting, running, building, checking types, testing, using AST tools, and cleaning up generated files, the CLI offers users a versatile toolkit for Jac programming tasks.

## Commands

### 1. Format

The `format` command enables users to format Jac files to ensure consistency and readability in codebases. Users can specify the path to a single .jac file or a directory containing multiple .jac files to be formatted. Optionally, users can provide an output file path and enable debug mode for additional insights into the formatting process.

#### Usage:
```bash
$ jac_cli format <path> [--outfile <outfile>] [--debug]
