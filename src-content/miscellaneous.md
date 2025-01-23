# Miscellaneous

## ESCape Codes

| ESCape code     |   action                            |
|-----------------|-------------------------------------|
| `"\033[2J"`       | clean screen                        |
| `"\033[H"`        | position cursor in top-left corner  |
| `printf("\x1b[%d;%df", row, col);`    |    move to position `col,row`  |

* see also "ANSI-color-codes.h"
---
