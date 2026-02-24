- **6 Hours**
- **8 Marks**
# 3.1 Basic Architecture
# 3.2 Operation
## Instruction Execution
- Instructions are the sets of code that carry out particular function for each instruction, the controller sequences through several stage.
- each stage may consist of one or more clock cycles.
- The various stages or sub-operations can be explained as:
	1. Fetch Instruction
		- The next instruction to be executed is loaded into instruction register from memory.
		- the address of the memory where instruction resides is given by program counter.
	2. Decode Instruction
		- Instruction in the instruction register may represent various operations based on op-code and may include register or memory as operands.
		- in this stage the operation to be done by the instruction is determined
	3. Fetch Operand
		- For a given operation, operand can be a register or memory.
		- in operations including registers, the required data are loaded into registers as specified by the instruction
	4. Execute Operation
		- the ALU handles the arithmetic and logical operations defined by the instructions.
		- the loaded registers are fed to the inputs of ALU to carry out the operation.
	5. Store results
		- the destination to store results may be either register or memory.
		- after the execution of operation, the final data is loaded into register or memory as defined by the instruction.
## Pipelining
- implemented to increase the throughput of the system
- the given task is divided into various stages and multiple stages
	- which are independent of each other are executed simultaneously.
- for efficient instruction pipeline, different stages must be of almost same length and each instruction must require same number of cycles to complete its execution
- branching instructions can be an obstacle for efficient pipeline as next instruction to be executed will only be known after execution stage of branch instruction.
- this problem, however, can be addressed using various techniques.
- one simple method is to stall the pipeline when there is an occurence of branching instruction.
- the pre-fetch of next instructions is not done in this method rather waited for execute stage to complete first.
- another popular method is to use branch prediction.
	- branch is guessed and the next instruction is fetched correspondingly.
	- if the guess is correct, then it results in efficient pipeline.
	- but if the prediction is not correct then all pre-fetched instructions in the pipeline must be ignored.
- the following diagram shows an example of an instruction pipeline having five stages.
	- ![[Pasted image 20260224084417.png]]
- here, there are 8 instructions in the pipeline with each instruction divided into 5 stages
- and each requiring equal time to complete.
- in absence of pipeline, the total time required to complete eight instructions would be 8 x 5 = 40 clock cycles, assuming each stage to complete in one cycle.
- however with pipeline implementation, the total completion time required is 12 clock cycles.
- this way, pipeline helps to improve the performance of teh system.
## Superscalar and Very Long Instruction Architectures
- Multiple ALU architecture is implemented in superscalar architectures to improve the performance of the system.
- such systems can execute two or more scalar operations in parallel, which increase the requirement of ALU in the processor.
- it may require extensive hardware to detect mutliple indepndent instructions that can be executed simultaneously.
- instructions in such architectural systems are ordered statically (at compile time) or dynamically (during runtime).
- VLIW architecture is a type of static superscalar architecture.
- it contains multiple independent instructions in a single word.
- several operations are encoded in a single machine instruction.
- the compiler detects and schedules the instructions.
# 3.3 Programmer's View
# 3.4 Development Environment
- Processors along with the different development tools are used for the development of software or an embedded system.
- processor that is used to write and debug the program is commonly referred to as Development Process
- desktop computer can be taken as an example of development processor.
- such processors may not be a part of embedded system's implementations.
- but the processor in which our program is loaded is referred as target processor.
- AVR, 8051, PIC microcontrollers or 8085, 8086 microprocessor can be few examples of target processor.
- such processors are always a part of system implementations.
- various tools for the software development as well as embedded systems development are described in the following paragraphs.
## Tool for Implementation Phase
1. Assembler
	- convert assembly instructions to binary machine instructions
	- replaces op-code and operand mnemonics by binary equivalent.
	- translates symbolic labels into actual addresses.
	- it generates an equivalent binary code for a single machine instruction, so it follows one to one mapping principle.
2. Compilers
	- convert high level programs to machine programs.
	- each high-level constructs may be translated to several machine instructions.
	- hence, it may not follow one to one mapping principle.
	- cross compilers are those compilers which run on one processor but generate the code for a different processors.
3. Linker
	- combines object files into a single executabel file, or another object file.
	- allows creation of a program in separately assembled or compiled files.
	- it combines machine instructions of user code and instructions from standard library.
## Tools for Verification Phase
1. Debuggers
	- programs that are used to test and debug the targeted program.
	- these are programs that run on development processor but execute code designed for target processors.
	- simulates the function of the target processors and allows evaluation and correction of programs in development processor.
	- Stepping, breakpoints, watch values are few debugging techniques supported by various debuggers.
	- these debuggers are also nkown as instruction set simulators (ISS) or virtual machines (VM).
	- design cycle for debuggers is fast as compared to other tools, since the program is tested in development processor.
	- but these tools can lead to inaccuracy it does not interact with the actual system.
2. Emulator
	- can be a hardware or software that enables one system to behave like another system
	- consists of debugger coupled with a board connected to development processor.
	- the board consists of target processor or device similar to target processor and support circuitry.
	- it control and monitor the program's executio in actual embedded system circuit..
	- since the code must be downloaded into emulator hardware in each test, the design cycle is a little bit longer than compared to debugger.
	- but it leads to accurate testing as it interacts with the rest of teh system components as well
3. Device Programmers
	- the devices with the help of which binary machine programs are loaded into target processor's memory. 
	- using this tool, the program can be tested in its realistic form which results in high accuracy as program runs on actual system.
	- the design cycle, however, is longest since the target processor is removed from the system
		- programmed using programmer and returned to the system
	- if the device programmer can be made in-build within the system
		- the design cycle will be reduced.
## Design Flow
- For a software development, the development processor as well as the target processor may be common
- and the development tools are available in a single package which is referred as IDE.
- figure for software development process
	- ![[Pasted image 20260224090012.png]]
- Implementation Phase:
	- Source code is written using an editor, and the code is compiled/assembled using compiler/assembler.
	- Finally with the help of linker all of required files are combined into a final executable file.
- Verification Phase:
	- The executable file is run under the command of a debugger.
	- All possible inputs, especially boundary cases, are used to check the behavior of program.
	- Profiles can be used for performance analysis of the program.
	- Time and space complexity can be analyzed.
	- Time complexity includes duration of execution of program whereas space complexity includes memory usage.
## Embedded System Development Process
- In case of embedded system design, the target and development processors are different in all systems.
- IDE tools for various processors are available for implementation phase.
- Though the implementation phase for embedded system is similar to that of software implementation phase, the verification phase differs drastically.
- figure:
	- ![[Pasted image 20260224120651.png]]
- Implementation Phase:
	- The process of editing, compiling/assembling and linking the program is same as that of software development process.
	- however, development processors use cross compilers or cross assembler.
	- as those compilers run on development processor, for example PC, and generate the file for target processor, for example hex file for microcontrollers.
- Verification Phase:
	- Embedded system works in conjunction with other components as well as with real time environment, so debugging a program requires control time and environment.
	- Based on requirement and availability, debuggers, emulators or device programmers can be used for verification.
	- Code may be simulated on development processor using debuggers or code may be checked by loading into emulator hardware.
	- Also, programmer can be used to load the code directly into the target processor.
# 3.5 Application-Specific Instruction Set Processors
- ASIC processors are specific to the particular application domain.
- they can be programmed based on requirement of particular arena, which makes it more flexible.
- also other constraints such as performance, power, cost and size are efficient enough to develop a system.
- however, instruction set processor and its associated software tools are expensive to develop.
- it can be categorized as microcontrollers, digital signal processors and less general application specific instruction set processors.
## Microcontrollers
- specific to applications that perform a large amount of control oriented tasks.
- The following are few general features of microcontrollers
	- it includes several peripheral devices such as timers, analog to digital converters, serial communication devices, and so on
	- it generally contains program and data memory to the same IC. various peripherals along with memory incorporated within the same IC result in compact and low-power implementation
	- it provides the programmer direct access to number of pins of the IC. Access to pins enable programmer to interface with other devices such as sensor, actuators, LCDs and other different devices that may be used in the system.
	- Some specialized instructions may be available. Such facility improves the performance of the system.
## DSP
- processors which are specific to applications that process large amounts of data.
- the source of large amounts of data includes image captured by a camera, voice packet through a network router, audio clip played by an instrument. Few features, out of many, are listed below
	- it may contain numerous register files, memory blocks, multipliers and other arithmetic units.
	- it facilitates with instructions that are applicable uniquely to digital signal processing
	- filtering and transforming vectors can be two examples.
	- frequently used arithmetic functions are implemented using hardware.
		- it results in faster execution of arithmetic functions compared to software implementation
	- some special digital signal processors allow concurrent execution of functions which boost the performance of the system
	- it incorporates many peripherals specific to signal processing.
		- it may include ADC, DAC, PWN, DMA controllers, timers and counters.
## Less-General ASIP
- These are developed to perform some very domain specific processing while allowing some degree of programmability.
- processors designed for networking hardware can be taken as an example of less-general ASIP.
# 3.6 Selecting a Microprocessor
- In any embedded system, a designer must select the microprocessor based on technical and non technical aspects.
	- Technical aspects: Selection of processor must be done based on required speed within limited power, size, and cost.
	- Non technical aspect: Before selecting microprocessor, one must be aware of development environment, prior expertise of processor, licensing arrangements and so on.
## Comparing Speed
- Speed of processors can be measured and compared using various methods.
1. Clock Speed of processor
	- speed can be compared based on clock speeds of processors, but the number of instructions per clock cycle may differ.
	- SO, it may not be an efficient method unless processors to be compared have same number of instructions per cycle.
2. Instruction per second
	- speed can be evaluated using number of instructions executed per second.
	- but the complexity of available instruction sets may differ creating some hindrance in speed comparison. For example, to perform same operation, one processor may require 200 instructions while another may require 300 instructions.
3. Dhrystone benchmar
	- it is a program that runs on different processors and evaluates their performance based on execution of certain operations.
	- Dhrystone benchmark performs no useful work rather checks the integer arithmetic and string-handling capabilities of the processor on which the benchmark runs on.
	- Since processors can execute such operations thousand of times in a second, speed of processor may be expressed in terms of Dhrystones per seconds.
4. MIPS
- general measure of computing performance and the amount of work a processor can do.
- MIPS can be useful when comparing performance of processors having similar architecture.
- origin of MIPS is based on VAX 11/78- which could execute one million instructions per second or could execute 1757 Dhrystones per second.
- Hence 1 MIPS = 1757 Dhrystones/sec.
- Also performance of other computers were measured based on VAX 11/780.
# 3.7 General-Purpose Processor Design
