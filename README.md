BTE
===
Usage
-----
```
USAGE: bte [-o, --output-file <FILE>] <DEFINITIONS> <TEMPLATE>
       -h, --help               output this message
       -o, --output-file <FILE> sets output file to FILE
```
Synax (Within definitions file)
-------------------------------
Definitions files are simply bash scripts. They define a 'DEFINITIONS' associative array, and the elements within the array are the constants which will be injected into the input (template) file.
E.g.
```
#!/usr/bin/env bash

declare -A DEFINITIONS=(
       ...
       ["DGRY"]="#111111"
       ...
)
```
Syntax (Within template file)
-----------------------------
`$X` maps to the value of X, and `$$X` simply removes the first $ (`$$X -> $X`).
E.g.
```
...
bspc config active_border_color "$DGRY"
...
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
