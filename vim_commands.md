
# vi list of shortcuts

## modes
	- insert/edit (press i)
	- visual (CTRL-V)
	- commands (press :)
	- exit insert mode, press ESC key

## some basic commands
	:w __ write/save.
	:q __ quit.
	:w <filename.ext> __ saves file as "filename.ext"
	:q! __ quits without saving the changes to the file

	:$ __ goes to end of the file
	:1 __ goes to line #1
	:N __ goes to line #N
	$  __ goes to the end of the current line
	w  __ goes to next word
	b  __ goes to the beggining of the word
	e __ goes to the end of the word

	x _ deletes the current character
	dw __ deletes all the text until the next word
	d$ __ deletes all the text until the end of the line
	dd __ deletes a whole line
	Ndd __ deletes N lines

	gq __ wrap lines around 80 characters long


	.  _ repeats last command

## misc.
	ga __ shows ascii/hex/octal values of the corresponding character	



## Interesting Readings:

	* https://www.redhat.com/sysadmin/introduction-vi-editor
	* https://www.redhat.com/sysadmin/vim-power-commands
	* https://www.redhat.com/sysadmin/3-text-editors-compared
	* https://www.redhat.com/sysadmin/use-vim-macros
	* https://www.redhat.com/sysadmin/five-vim-plugins

---