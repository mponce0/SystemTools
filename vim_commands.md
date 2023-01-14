# `vi`

## Modes
`vi` has a couple main modes of working (insert and command) and a few variations around them.

|	mode					|	action	|
|---------------------------|-----------|
| to enter insert/edit-mode | press `i` |
| to define a code-block/visual-mode | press `CTRL-V` |
| to enter command-mode		|	press `:`		|
| to exit insert mode		|	press `ESC` key |


## Basic commands
File Manipulation
| command		|	action			|
|---------------|-------------------|
|	`:w`		| write/save current file	|
|	`:q`		| quits/exists	|
|	`:w <filename.ext>` | saves file as "filename.ext"	|
|	`:q!`		| quits without saving the changes to the file	|
| **Movement**	|
|	`0`  		| goes to the beggining of the current line	|
|	`$`  		| goes to the end of the current line	|
|	`:$` 		| goes to end of the file	|
|	`:1` 		| goes to line #1	|
|	`:N` 		| goes to line #N	|
|	`$`  	| goes to the end of the current line	|
|	`w`		| goes to next word	|
|	`b`		| goes to the beggining of the word	|
|	`e`		| goes to the end of the word	|
| **Edition**	|
|	`x` 	| deletes the current character	|
|	`dw` 	| deletes all the text until the next word	|
|	`d$` 	| deletes all the text until the end of the line	|
|	`dd` 	| deletes a whole line	|
|	`Ndd`	| deletes N lines	|
|	`gq`	| wrap lines around 80 characters long	|
| **Search and Replacement** |
|	`/PATTERN` | search for pattern in the file	|
|	`:%s/TARGET/CHANGE/` | search TARGET and substitute for CHANGE in next appearance of TARGET	|
|	`:%s/TARGET/CHANGE/g` | search TARGET and substitute for CHANGE globally	|

	`.`  _ repeats last command


## Misc.
	`ga` __ shows ascii/hex/octal values of the corresponding character	



## Interesting Readings and Futher Resources:

	* https://www.redhat.com/sysadmin/introduction-vi-editor
	* https://www.redhat.com/sysadmin/vim-power-commands
	* https://www.redhat.com/sysadmin/3-text-editors-compared
	* https://www.redhat.com/sysadmin/use-vim-macros
	* https://www.redhat.com/sysadmin/five-vim-plugins

---
