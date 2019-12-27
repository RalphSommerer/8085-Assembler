# 8085-Assembler

A simple 8085 assembler.

## Usage
```
usage: assembler.py [-h] [-L] [-A] [-B] [-I] [-H] [-C] [-s] [-o OUT] source

A simple 8085 assembler.

positional arguments:
  source             source file

optional arguments:
  -h, --help         show this help message and exit
  -L, --lineNum      include the line number in output
  -A, --address      include the address in output
  -B, --label        include the labels in output
  -I, --instruction  include the instructions and arguments in output
  -H, --hex          include the hex code in output
  -C, --comment      include the comments in output
  -s, --standard     equivalent to -A -B -I -H -C
  -o OUT, --out OUT  output file name (stdout, if not specified)
  ```
## Source File Syntax
The assembler is case insensitive.

### Comments
Comments begin with semicolons.
```asm
MVI A, 0x5C   ; This is a comment
```

### Constants
8 and 16-bit constants are given in hex. 8-bit constants must have two digits, and 16-bit constants must have 4-digits.
```asm
MVI A, 0x0C
MVI A, 0C   ; The "0x" is optional
MVI A, 7    ; Illegal. 8-bit constants must have two digits

LXI 0x03B7
LXI 03B7    ; The "0x" is optional
LXI 3B7     ; Illegal. 16-bit constants must have four digits
```

### Label Definitions
Label definitions may be any string ending with a colon, where the string does not match the pattern of an 8 or 16-bit constant.
### Directives
