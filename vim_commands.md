# `vi`

`vi` or `vim` is a powerful, terminal-based editor.
Widely used among programmers, sys.admins and power-users, offers
the ability of realzing complex tasks all based on keyboard interations.

For begginners it may offer a bit of a step learning curve.
We compile here some of the most useful commands and some
worst-reading references at the bottom of this document.


## Modes
`vi` has a couple main modes of working (insert and command) and a few variations around them.

|	mode					|	action	|
|---------------------------|-----------|
| to enter insert/edit-mode | press `i` |
| to define a code-block/visual-mode | press `CTRL-V` |
| to enter command-mode		|	press `:`		|
| to exit insert mode		|	press `ESC` key |


## Basic commands
While being in command-mode, the following combination of key-strokes will generate the corresponding action.

The commands beggining with `:` needs to be finalized with hitting "Enter".


| keys combination	|	command/action			|
|---------------|-------------------|
| **File Manipulation**	|
|	`:w`		| write/save current file	|
|	`:q`		| quits/exists	|
|	`:w <filename.ext>` | saves file as "filename.ext"	|
|	`:q!`		| quits without saving the changes to the file	|
| **Movement**		|
|	`0`  		| goes to the beggining of the current line	|
|	`$`  		| goes to the end of the current line	|
|	`:$` 		| goes to end of the file	|
|	`:1` 		| goes to line #1	|
|	`:N` 		| goes to line #*N*	|
|	`$`  		| goes to the end of the current line	|
|	`w`		| goes to next word	|
|	`b`		| goes to the beggining of the word	|
|	`e`		| goes to the end of the word	|
| **Edition**		|
|	`x` 		| deletes the current character	|
|	`dw` 		| deletes all the text until the next word	|
|	`dNw`		|	deletes *N* words	|
|	`db`		| deletes the previous word	|
|	`d)`		| deletes until the end of the sentence	|
|	`d$`		| deletes all the text until the end of the line	|
|	`dd` --or-- `D`	| deletes the whole line	|
|	`Ndd`		| deletes *N* lines	|
|	`gq`		| wraps current line around 80 characters long	|
| **Search and Substitution** |
|	`/PATTERN` 	| search for first appearance of pattern from the current position onwards	|
|	`:%s/TARGET/CHANGE/` | search TARGET and substitute for CHANGE in next appearance of TARGET	|
|	`:%s/TARGET/CHANGE/g` | search TARGET and substitute for CHANGE globally	|
| `:[LOC]s/OLD/NEW/` | general case for search and replace |
| `:.s/OLD/NEW/` | replace OLD with NEW in current line  |
| `:Ns/OLD/NEW/` | replace OLD with NEW in line #*N*  |
| `:.+Ms/OLD/NEW/` | replace OLD with NEW from current line plus *M* more  |
| `:$s/OLD/NEW/` | replace OLD with NEW in last line  |
| `:%s/OLD/NEW/` | replace OLD with NEW in entire file  |
| `:[line1],[line2]s/OLD/NEW/` | replace OLD with NEW between lines *line1* and *line2*  |
| **Configuration & Parameters** |
| `:set number` 	| displays line numbers			|
| `:set nonumber` 	| removes line numbers			|
| `:set paste`		| activates "paste" mode		|
| `:set syntax`		| enables syntax highlighting		|
| `:set all`  		| shows all available parameters	|
| **Miscellaneous** 	|
|	`.`		| repeats last command	|
|	`ga`		| shows ascii/hex/octal values of the corresponding character		|
|	`:!<cmd>`	| executes the <*cmd*> command from the shell	|



## Advanced Features
`vi` has a large set of contributed *plugins* which allows
for a high cutomizable experience.



## Interesting Readings and Futher Resources:

  * https://www.redhat.com/sysadmin/introduction-vi-editor
  * https://www.redhat.com/sysadmin/vim-power-commands
  * https://www.redhat.com/sysadmin/3-text-editors-compared
  * https://www.redhat.com/sysadmin/use-vim-macros
  * https://www.redhat.com/sysadmin/five-vim-plugins

---
