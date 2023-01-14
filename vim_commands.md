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
|	**Movement**	|
|	`0`  		| goes to the beggining of the current line	|
|	`$`  __ goes to the end of the current line
|	`:$` __ goes to end of the file
|	`:1` __ goes to line #1
	`:N` __ goes to line #N
	`$`  __ goes to the end of the current line
	`w`  __ goes to next word
	`b`  __ goes to the beggining of the word
	`e` __ goes to the end of the word
|	*Edition*	|
|	`x` 	| deletes the current character	|
|	`dw` 	| deletes all the text until the next word	|
|	`d$` 	| deletes all the text until the end of the line	|
|	`dd` 	| deletes a whole line	|
|	`Ndd`	| deletes N lines	|

	`gq` __ wrap lines around 80 characters long

	`/PATTERN` __ search for pattern in the file
	`:%s/TARGET/CHANGE/` __ search TARGET and substitute for CHANGE in next appearance of TARGET
	`:%s/TARGET/CHANGE/g` __ search TARGET and substitute for CHANGE globally

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
