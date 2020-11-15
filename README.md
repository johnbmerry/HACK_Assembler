# Basic Assembler, Full Assembler, and Disassembler

## Language used: Python

This project is the sixth project of a sequence in a semester long course on Computer Organization.
These files were written as a component of and submitted to a HackerRank competitiion. As such, they use
the standard input and output files.
The full assembler and disassembler are, respectively, the assembler and disassembler components of
the 16-bit HACK Computer constructed in earlier projects.

The Basic Assembler processes simple assembly instructions whereas the Full Assembler also has label
and variable handling. Tangentially, the disassembler converts supplied machine code to assembly instructions.

### Run the project

To run any of these files locally, simply install them to your machine and open them in Python.
Standard inputs via .asm and .hack files must be provided for the assembler and disassembler respectively.

#### Code Analysis

##### Assembler (built from Basic Assembler)

* Create appropriate dictionaries for reference to machine code
  * symbol table stores memory address
	* Subsidiary function add_symbol() adds a symbol to the symbol table
* Subsidiary function int_to_binary() converts integer to a binary value
* Subsidiary function clean() removes any whitespace, '\n', or comments
* first pass (for loop 1) adds all symbols to symbol table with appropriate value
* second pass (for loop 2) determines 'type' of each line and calls appropriate function with
  proper parameters
  * A_instruction() selectively processes an integer value or uses key to access
    value(location) in symbol table and optionally adds unknown symbols to the symbol table
  * C_instruction() converts provided parameters to machine code

##### Disassembler
* Uses inverse dictionaries from Assembler
* detects A instruction or C_instruction and calls appropriate function
  * A_instruction() converts provided binary value to integer
  * C_instruction() breaks each line into component parts, converts them to correlating value in 
    dictionary (inverse of assembler dictionaries), returns appropriate assembly instruction
    * assembly instructions equivalent to basic instructions for basic assembler (no labels, variables, etc).

### ToDo
- [ ] Add more complete error handling Full Assembler
- [ ] Add more complete error handling Disassembler

### Resources
Background information on prior projects as well as documentation on original version of this project
can be found at [Nand2Tetris.](https://www.nand2tetris.org/project06)

