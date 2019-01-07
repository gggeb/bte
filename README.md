BTE
===
Usage
-----
```
USAGE: bte [-o, --output-file <FILE>] <DEFINITIONS> <TEMPLATE>
       -h, --help               output this message
       -o, --output-file <FILE> sets output file to FILE
```
Syntax
------
```
$$X = %X
$X  = VALUE
```
Notes
-----
The name of the default output file is simply the input file, with the last extension removed.
```
Input   || Output
INPUT.d -> INPUT
```
Therefore, it is important to add the `.d` extension to input files so as to prevent output files overwriting input files, and to prevent unintended removal of extensions.
E.g.
```
Input    || Output
xinitrc  -> xinitrc (the original xinitrc is now gone.)
       or
config.h -> config
```
