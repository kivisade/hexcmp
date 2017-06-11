# hexcmp

A simple utility intended to be used in pipeline with unix `cmp -l` command.
Converts all three columns of `cmp -l` output (offset, byte value from left file,
byte value from right file) to hexadecimal numbers. 

## Motivation

Original `cmp -l` output is formatted as "decimal octal octal", which is
very inconvinient. `Cmp` does not support any commandline switches to change this
output format.

`hexcmp` covers for this drawback.

## Usage

```
cmp -l file1 file2 | hexcmp
```

## Sample output

```
0045fd e8 eb
0045fe 37 3a
0045ff cf 90
004600 01 32
004601 00 c0
```

## Pretty print

`hexcmp` supports one commandline switch: `-p`. It allows to print a slightly "nicer looking" output:

```
0045fd: e8 -> eb
0045fe: 37 -> 3a
0045ff: cf -> 90
004600: 01 -> 32
004601: 00 -> c0
```
