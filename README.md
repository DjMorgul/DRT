# DRT

DAAD Reborn Tokenizer

Finds good abbreviations (tokens) for text compression in DAAD databases, for their usage in DRC (DAAD Reborn Compiler) backend.

It does so by looking for each combination of substrings within the compressible text messages in the database, between a minimum and a maximum substring length, counting the number of occurrences of those substrings within all of those text messages, and picking the ones that seem to provide the biggest savings of disk space as the abbreviations/tokens to use, based on some heuristics (as it's not possible to find the optimum combination of tokens unless using an even more time-consuming brute-force approach).


## Requirements

- Python interpreter version 2.7 or higher. Version 3 is supported as well.
- Optionally, Python's _progressbar_ module.


## Command-line parameters

```
[OPTIONS] <input.json> [output.tok] [OPTIONS]
```

### Positional parameters

- `input.json` (mandatory): the input file, JSON output for the database generated by DRC frontend.
- `output.json` (optional): the output file, abbreviation/token file that DRC backend can use. If this parameter is omitted, the output will be written to standard output.

### Optional parameters

- `-c`, `--no-compatibility`: disable compatibility with original interpreters.
- `-l`, `--min-length`: minimum length in characters for the substrings search. By default, their shortest length will be 3 characters long.
- `-L`, `--max-length`: maximum length in characters for the substrings search. By default, their longest length will be 30 characters long.
- `-h`, `--help`: show program usage information and quit.
- `-v`, `--verbose`: activate verbose mode, showing additional information.
- `-V`, `--version`: show program version and quit.
