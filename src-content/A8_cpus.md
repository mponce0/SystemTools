

* Turing machine
	Refers to a *mathematical model* of computation describing an abstract machine.
	The model can be considered a generic example of a CPU.


# von Neumann architecture
	Refers to a computer architecture designed with a stored-program computer concept, where instruction data and program data are stored in the same memory.
	This design is still used in most of the modern computers nowadays and include the following elements:
	- CPU: a central processing unit, 
	- ALU
	- main Memory: RAM
	- Peripherials:
		- I/O devices: keyboard, screen, HDD, SDD




```
	microproccessor				clock
+---------------------------------------+	+------+
|	+--------------------+		|	| X GHz|     __    __    __
|	| RX RX . . . RX RX  |		|	+------+  __/  \__/  \__/  \_...
|	+ +----------------+ |		|	  ^
|	| |	CPU	   | |		|	  :
|	| +----------------+ |<.........|.........:
|	| RX RX . . . RX RX  |		|
|	+--------------------+		|
|	   ^   ^   ^			|
|	   |   |   |			|
|	   v   v   v			|
|	+------------+			|
|	|  L1 cache  |			|
|	+------------+--+		|
|	|  L2 cache	|		|
|	+---------------+-------+	|
|	|  L3 cache		|	|
|	+-----------------------+	|
|	  ^   ^   ^   ^   ^   ^		|
+---------|---|---|---|---|---|---------+
	  |   |   |   |   |   |
	  |   |   |   |   |   | data bus lines
	  :   :   :   :   :   :
	  |   |   |   |   |   |
	  |   |   |   |   |   |
	  V   V   V   V   V   V
	+=======================+
	||			||
	||	R A M		|| main memory
	||			||
	+=======================+
```
