# furoku-data
EB4J  appendix/furoku data source with unicode extension

## What this?

This is a hint extension for EPWING dictionary look-ups.

It defines `stop-code` which notify viewer where is an end of article of each entry.
Because EPWING standard don't have a `end-of-entry` mark, it is *mandatory* for some
use cases.

It also defines `GAIJI` alternative unicode codepoints.

Some viewer such as `EBVIEW` and `GoldenDict` can handle GAIJI image feature
properly, so it can display GAIJI as bitmap images.

It will bring better experience when viewers show such GAIJIs as ordinal
unicode character.

You can try `eb4j/ebviewer` simple epwing viewer application that support
appendix/furoku definitions with unicode extension, how appendix/furoku make
changes to behavior.


## Specifications

The appendix is EB library (in C/C++) original extension of the EPWING standard specification.
EB4J can handle EB library's appendix features.

Original definitions of appendix uses EUC-JP or ISO-8859-1 character encoding
and character sets.
It limits application its usable Unicode characters to display. 

EB4J extends it to allow '\uXXXX' and '\UXXXXXXXX' form of unicode escape sequence.
It does not break the original library. EB library( in C/C++) will pass it as is.

EB4J provide an API to escape/unescape these strings, and EB4J automatically unescape
these sequence into proper unicode (include surrogate-pair one) characters.

EB4J-tools handle input format as in YAML. It will escape characters.

## How to use

1. Install [EB4J-tools](https://github.com/eb4j/eb4j-tools)
2. Compile data from source(YAML) to furoku binary, such as    ``` eb appendix -o /tmp genius.yml```
3. You will see furoku data, such as ```/tmp/GENIUS/data/furoku```
4. Install furoku data to proper directory where original data placed such as `/usr/share/dict/GENIUS/data/furoku,  honmon` 

## Status

Target                    |  Source       | Stop-code | Status  
------------------------- | ------------- | --------- | ------
大修館ジーニアス英和大辞典    | genius.yml    | yes       | Beta
大修館ジーニアス英和辞典第5版 | genius.yml    | yes       | Beta
大修館ジーニアス英和辞典第4版 | genius43.yml  | yes       | Alpha
岩波広辞苑第4版 第5版       | kojien.yml     | yes      | Alpha
研究社英和中辞典            | chujiten.yml  | yes       | Pre-Alpha
クラウン仏和辞典            | crown.yml     | yes       | Pre-Alpha


## Copyright and License

Copyright (C) 1997  Toshiyuki Miyamoto

Copyright (C) 2007  hishida

Copyright (C) 2021  Hiroshi Miura

This program is free software; you can redistribute it and/or modify
it under# This program is free software; you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation; either version 2, or (at your option)
any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details. the terms of the GNU General Public License as published by
the Free Software Foundation; either version 2, or (at your option)
any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.
