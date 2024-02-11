# `vi`

`vi` or `vim` is a powerful, terminal-based editor.
Widely used among programmers, sys.admins and power-users, offers
the ability of achieving complex tasks all based on keyboard interactions.

For beginners it may offer a bit of a steep learning curve.
We compile here some of the most useful commands, as well as,
some worth-reading references at the bottom of this document.


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

The commands beginning with `:` needs to be finalized with hitting "Enter".


| keys combination	|	command/action			|
|---------------|-------------------|
| **File Manipulation**	|
|	`:w`		| write/save current file	|
|	`:w <filename.ext>` | saves file as "filename.ext"	|
|	`:q`		| quits/exists	|
| `:wq` / `ZZ` / `:x`  | saves changes to current file and exists  |
|	`:q!`		| quits without saving the changes to the file	|
| **Movement**		|
|	`0`  		| goes to the beginning of the current line	|
|	`$`  		| goes to the end of the current line	|
|	`:$` 		| goes to end of the file	|
|	`:1` 		| goes to line #1	|
|	`:N` 		| goes to line #*N*	|
|	`$`  		| goes to the end of the current line	|
|	`w`		| goes to next word	|
|	`b`		| goes to the beginning of the word	|
|	`e`		| goes to the end of the word	|
| **Edition**		|
|	`i` 		| inserts before cursor |
|	`I` 		| inserts before line |
|	`a` 		| appends after cursor  |
|	`A` 		| appends after line  |
|	`o` 		| opens blank line below the cursor |
|	`O` 		| opens blank line above the cursor |
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
| **Visual Mode** |
| `v` | enters visual mode and start to highlight characters  |
| `V` | enters visual mode and start to highlight lines  |
| `ESC` | exits visual mode |
| **Configuration & Parameters** |
| `:set number` / `:set nonumber` 	| displays/removes line numbers			|
| `:set list` / `:set nolist`	| displays/hides special characters			|
| `:set autoindent`		| activates auto-indent   |
| `:set smartindent`		| activates smart-indent contextualized with the code |
| `:set tabstop=x`    | sets *x* spaces to be used as <tab>   |
| `:set showmatch`    | highlights matching opening-closing parenthesis when cursor passes over   |
| `:set hlsearch` | highlights matches in a search   |
| `:set paste`		| activates "paste" mode, e.g. deactivates autoindent		|
| `:set ignorecase` / `:set ic` | ignores case-sentive in searches  |
| `:set syntax`		| enables syntax highlighting		|
| `:set all`  		| shows all available parameters	|
| **Miscellaneous** 	|
| `~`   | toggles uppercase <-> lowercase   |
|	`.`		| repeats last command	|
|	`ga`		| shows ascii/hex/octal values of the corresponding character		|
|	`:!<cmd>`	| executes the <*cmd*> command from the shell	|



## Advanced Features
### Configuration
All the seteable parameters of `vi` can be set in a configuration file,
usually located in the user's homedir named `.vimrc`.


### Plugins
`vi` has a large set of contributed *plugins* which allows for a highly customizable experience.
Plugins will be installed in a `.vim` sub-directory within the user's home-dir.
Installation is usually done via a "package manager" and there are a few different ones.

Personally, I don't use a lot of plugins, but here are some of the ones I'm currently using:
[NERDTree](https://github.com/preservim/nerdtree),
[airliner](https://github.com/vim-airline/),
[gitgutter](https://github.com/airblade/vim-gitgutter).

See more plugins at, https://vimawesome.com

#### VIM Plugins Tree Structure
### VIM directory structure

```
/Users/marcelo/.vim/pack/
├── dist
│   └── start
│       ├── vim-airline
│       │   ├── autoload
│       │   │   └── airline
│       │   │       ├── extensions
│       │   │       │   ├── tabline
│       │   │       │   │   └── formatters
│       │   │       │   └── wordcount
│       │   │       │       └── formatters
│       │   │       ├── formatter
│       │   │       └── themes
│       │   ├── doc
│       │   ├── plugin
│       │   └── test
│       └── vim-airline-themes
│           ├── autoload
│           │   └── airline
│           │       └── themes
│           ├── doc
│           ├── plugin
│           └── test
├── plugins
│   └── start
│       └── lightline
│           ├── autoload
│           │   └── lightline
│           │       └── colorscheme
│           ├── doc
│           ├── plugin
│           └── test
└── vendor
    └── start
        └── nerdtree
            ├── autoload
            │   └── nerdtree
            ├── doc
            ├── lib
            │   └── nerdtree
            ├── nerdtree_plugin
            ├── plugin
            └── syntax
```



## Examples
### Search and Replace
   - replace only the first occurrence of "oldTEXT" with "NewText" in each of the following 11 lines starting with the current line (`.`) and continuing for the 10 that follow (`.+10`)

     `:.,.+10s/oldTEXT/NewText`

   - replace every occurrence (caused by the `g` at the end of the command) of "oldTEXT" with "NewText"
   
     `:%s/oldTEXT/NewText/g`

   -  remove the last character from every line in the file. Use it if every line in the file ends with ^M as the result of a file being transferred among different OSes. Execute it when the cursor is on the first line of the file

      `:%s/.$//`

   - remove ^M can be also achieve more precisely by searching for the "^M" sequence, however it ^M should be written as the combination of `CTRL-V` __and__ `CTRL-M`, i.e. pressing `CTRL-V-M` simultaneously

       `:%s/^M//g`


  - comment out all the lines in a file using `#`

     `:%s/^/#/`


### Visual Mode
  - remove characters vertically, e.g. remove comments given by multiples lines of `#`s or `//`s.
     - enter in visual mode by pressing `CTRL-V`
     - select the column of characters to remove using the cursor keys
     - press `x`

  - add comments in multiple lines
    - enter in visual mode by pressing `CTRL-V`
    - select the lines to comment, move up/down with arrow keys
    - press `Shift+I`
    - insert the text you want, e.g. `%` or `//` or `#`
    - press `Esc` `Esc`





## Interesting Readings and Further Resources:
### Articles:
  * https://www.redhat.com/sysadmin/introduction-vi-editor
  * https://www.redhat.com/sysadmin/vim-power-commands
  * https://www.redhat.com/sysadmin/3-text-editors-compared
  * https://www.redhat.com/sysadmin/use-vim-macros
  * https://www.redhat.com/sysadmin/five-vim-plugins


### Cheat sheets and QuickRefs:
  * http://www.linux-admins.net/2011/01/vi-cheat-sheet.html
  * https://ss64.com/vi.html

#### Visual cheat sheets
  * https://people.csail.mit.edu/vgod/vim/vim-cheat-sheet-en.pdf
  * https://victorhck.gitlab.io/comandos_vim/
  * https://hamwaves.com/vim.tutorial/doc/vim.cheat_sheet_tutorial.pdf
  * https://osslab.tw/uploads/images/gallery/2022-10/vim-cheatsheet.png
  * 


---
