## Turing machine
   Refers to a *mathematical model* of computation describing an abstract machine.
   The model can be considered a generic example of a CPU.


## von Neumann architecture
   Refers to a computer architecture designed with a stored-program computer concept, where instruction data and program data are stored in the same memory.
   This design is still used in most of the modern computers nowadays and includes the following elements:
  - **CPU**:
  	the *Central Processing Unit*, which ultimately is the heart of the computer, where instructions and commands are executed, data processed and logic followed.

	The CPU also contains:
	   - ALU: the *Arithmetic Logic Unit*, responsible for mathematical and logical operations.
	   - CU: *Control Unit*, manages data communication between the ALU and memory, as well as, instructions execution.
	   - Registers (RX): are memory space limited in size but very fast and sitting directly on the CPU.

  - Main Memory:
  	usually known as *RAM*, are larger spaces of volatile memory which can be expanded by adding new hardware.

  - Peripherials:
	  - I/O devices: keyboard, screen, HDD, SDD

---
   - _cache_, aka "cache memory" or "cache lines" are an intermediate memory space between main RAM registers on the microprocessor
   - _core_, another term for CPU, multi-core architectures consist of multiple cores or CPUs
   - _die_,
   - _microprocessor_, integrated circuit containing multiple components, eg. chip with CPU+cache+...
   - _chips_, generic way to refer to integrated circuits with different components, architectures, etc.
---

```
										--[motherboard schematics]--
	microproccessor				clock
+---------------------------------------+	+------+
|	 +~~~~~~~~~~~~~~~~~~~~~~~~+	|	| X GHz|     __    __    __
|	:|  (RX)(RX). . .(RX)(RX) |:	|	+------+  __/: \__/: \__/  \_...
|	:| +--------------------+ |:	|	  ^	     /-----/
|	:| | CPU = (CU) + (ALU) | |:	|	  :		1/X nanosec = 1/X 10^-9 sec
|	:| +--------------------+ |<....|.........:	5 GHz --> 20e-9 sec = 20 nanosec ~ 20,000,000,000 ops/sec
|	:|  (RX)(RX). . .(RX)(RX) |:	|
|	 +~~~~~~~~~~~~~~~~~~~~~~~~+	|
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
