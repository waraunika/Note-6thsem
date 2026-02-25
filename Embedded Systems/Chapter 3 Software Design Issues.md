b- **6 Hours**
- **8 Marks**
# For Assessment
1. Explain with diagram about pipelining. Explain 5 stage pipelining. [[#Pipelining]]
2. Explain the sub-operation of control unit with necessary illustration. [[#Instruction Execution]]
3. Differentiate between application specific instruction set-processor and general-purpose processor. [[#ASIP vs GPP]]
4. Also discuss on issues related to selection of a particular processor. [[#3.6 Selecting a Microprocessor]]
5. Define Debugger, Simulator, testing and Emulator [[#Technical Terms]]
# 3.1 Basic Architecture
# 3.2 Operation
## Instruction Execution
- **Instructions** are the fundamental sets of binary codes that tell the processor what operation to perform.
- For each instruction, the **controller** sequences the processor through several stages. 
- Each stage typically consists of one or more clock cycles.
### The Five Stages of Instruction Execution
#### 1. Fetch Instruction
- **Action:** The next instruction to be executed is loaded from system memory into the **Instruction Register (IR)** .
- **Mechanism:** The **Program Counter (PC)** holds the memory address of the instruction to be fetched. This address is sent to the memory unit, which returns the instruction data.
- **Result:** The instruction is now stored inside the processor, ready to be interpreted.
```
[Program Counter] ---Address---> [Memory] ---Instruction---> [Instruction Register]
```
#### 2. Decode Instruction
- **Action:** The instruction in the Instruction Register is interpreted.
- **Mechanism:** The processor's control unit examines the **opcode** (operation code) field of the instruction to determine what operation needs to be performed (e.g., add, load, branch). It also identifies the operands, where the input data is located (registers or memory addresses) and where the result should be stored.
- **Result:** The control unit generates the necessary signals for the next stages.
```
[Instruction Register] 
        |
        v
[Control Unit] ---> "Operation = ADD" 
                 ---> "Operand1 = Register R1"
                 ---> "Operand2 = Register R2"
                 ---> "Destination = Register R3"
```
#### 3. Fetch Operand
- **Action:** The actual data required for the operation is retrieved.
- **Mechanism:** If the operands are in **registers**, the register file is accessed, and the data is loaded into temporary registers (often called A and B). If an operand is in **memory**, a memory read cycle is initiated.
- **Result:** The data to be processed is now available at the inputs of the Arithmetic Logic Unit (ALU).
```
[Register File] ---Data from R1---> [Temp Register A]
                ---Data from R2---> [Temp Register B]

```
#### 4. Execute Operation
- **Action:** The desired operation is carried out by the **Arithmetic Logic Unit (ALU)** .
- **Mechanism:** The data from the temporary registers is fed into the ALU. The control unit tells the ALU which specific function to perform (e.g., addition, subtraction, AND, OR).
- **Result:** The result of the computation is produced at the output of the ALU.
```[Temp Register A] ---\
                      >---[ALU] ---> [Result]
[Temp Register B] ---/
      ^
      |
[Control Unit] (Tells ALU to "ADD")
```
#### 5. Store Result
- **Action:** The result from the ALU is written back to its destination.
- **Mechanism:** The result is sent to the location specified by the instruction, which could be a **register** (writing back to the register file) or a **memory location** (initiating a memory write cycle).
- **Result:** The instruction's effect is now visible in the processor's state. The processor is now ready to fetch the next instruction.

```[ALU Result] ---\
                 >--- [Register File] (Write to R3)
                OR
                 >--- [Memory] (Write to specified address)

```
---
## Pipelining
-  key technique used in processor design to increase **throughput**
- throughput
	- the number of instructions completed per unit of time.
- It does not make an individual instruction execute faster (latency)
- but it allows multiple instructions to be processed simultaneously, significantly improving overall system performance.
### Concept
- The idea is similar to an assembly line in a factory.
- The execution of a task (an instruction) is divided into a sequence of smaller, independent stages. While one stage is working on one instruction, other stages can work on different instructions.
- **Without Pipelining:** An instruction must complete all its stages before the next instruction can begin.
- **With Pipelining:** As soon as the first instruction moves from Stage 1 to Stage 2, Stage 1 is freed up to start working on the second instruction.
### Conditions for an Efficient Pipeline
For a pipeline to work at peak efficiency, two main conditions should ideally be met:
1. **Balanced Stages:** All pipeline stages should take approximately the same amount of time to complete. This prevents faster stages from having to wait for a slower stage, which would create a bottleneck.   
2. **Uniform Instructions:** Each instruction should ideally require the same number of cycles to complete its execution.
### Challenge: The Branch Hazard
- **Branching instructions** (like `if-else` or `goto`) pose a major problem for pipelining. 
- The processor needs to fetch the next instruction before the current one is finished.
- However, for a branch instruction, the address of the _next_ instruction to be executed is only known after the branch instruction has reached its **Execute stage**.
- This creates a hazard, as the pipeline may have already fetched and started processing the wrong instructions.
- This problem can be addressed using several techniques:
1. **Stalling (Flushing):**
	- The simplest method.
    - When a branch instruction is detected, the pipeline is **stalled**. No new instructions are fetched until the branch's Execute stage completes and the correct next address is known.
    - **Drawback:** This introduces "bubbles" (idle cycles) in the pipeline, reducing performance.
2. **Branch Prediction:**
    - A more advanced and popular method.
    - The processor **guesses** the outcome of the branch (e.g., "branch taken" or "branch not taken") and fetches the next instruction based on that guess.
    - **If the guess is correct:** The pipeline continues smoothly without any interruption (full efficiency).
    - **If the guess is incorrect:** All the incorrectly pre-fetched instructions must be **flushed** (ignored) from the pipeline, and the correct instruction is fetched. This incurs a small performance penalty but is generally better than stalling every time.
### Example: A 5-Stage Instruction Pipeline
A classic example is a RISC processor pipeline with five stages. Let's visualize how it improves throughput.
**The Five Stages are typically:**
1. **IF:** Instruction Fetch
2. **ID:** Instruction Decode / Register Fetch
3. **EX:** Execute / Address Calculation
4. **MEM:** Memory Access (for load/store instructions)
5. **WB:** Write Back (results to registers)
**The Diagram:**
```Clock Cycle:     1   2   3   4   5   6   7   8   9   10  11  12
                + - + - + - + - + - + - + - + - + - + - + - + - +
Instruction 1   |IF |ID |EX |MEM|WB |   |   |   |   |   |   |   |
                + - + - + - + - + - + - + - + - + - + - + - + - +
Instruction 2   |   |IF |ID |EX |MEM|WB |   |   |   |   |   |   |
                + - + - + - + - + - + - + - + - + - + - + - + - +
Instruction 3   |   |   |IF |ID |EX |MEM|WB |   |   |   |   |   |
                + - + - + - + - + - + - + - + - + - + - + - + - +
Instruction 4   |   |   |   |IF |ID |EX |MEM|WB |   |   |   |   |
                + - + - + - + - + - + - + - + - + - + - + - + - +
Instruction 5   |   |   |   |   |IF |ID |EX |MEM|WB |   |   |   |
                + - + - + - + - + - + - + - + - + - + - + - + - +
Instruction 6   |   |   |   |   |   |IF |ID |EX |MEM|WB |   |   |
                + - + - + - + - + - + - + - + - + - + - + - + - +
Instruction 7   |   |   |   |   |   |   |IF |ID |EX |MEM|WB |   |
                + - + - + - + - + - + - + - + - + - + - + - + - +
Instruction 8   |   |   |   |   |   |   |   |IF |ID |EX |MEM|WB |
                + - + - + - + - + - + - + - + - + - + - + - + - +
```
### Performance Comparison
Let's analyze the diagram above, assuming each stage takes one clock cycle.
- **Scenario 1: No Pipelining (Sequential Execution)**
    - Each instruction takes 5 cycles to complete.
    - To complete 8 instructions, the total time would be: `8 instructions × 5 cycles/instruction = 40 clock cycles`.
- **Scenario 2: With Pipelining (as shown in the diagram)**
    - The first instruction (I1) completes at the end of cycle 5.
    - The second instruction (I2) completes one cycle later, at the end of cycle 6.
    - The eighth instruction (I8) completes at the end of cycle 12.
- **Result:**  
	- With pipelining, **all 8 instructions are completed in just 12 clock cycles**, 
	- compared to 40 cycles without it. 
	- This is a significant improvement in **throughput**.
	- Once the pipeline is full (after cycle 5), one instruction is completed on every subsequent clock cycle.
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
## Technical Terms
### Debugger
- A software tool used to control the execution of a program (run, stop, step) and examine the internal state (variables, registers, memory) of a processor to find and fix errors (bugs).
-  It allows developers to see what is happening inside a program while it runs, making it the primary tool for diagnosing logical and runtime errors.
### Simulator
- A software program that mimics the behavior of a processor or entire system on a host computer, allowing code to be run and tested without the physical hardware.
- It enables early software development and debugging before the actual hardware is built, but it cannot perfectly replicate real-time electrical behavior.
### Testing
- The systematic process of executing a system or component under controlled conditions to verify that it meets its specified requirements and to detect defects.
- While debugging finds the cause of a known problem, testing is a proactive process aimed at finding unknown problems and ensuring overall quality and correctness.
### Emulator
- A hardware device or software program that exactly replicates the functions of one system on a different system, often used to replace the target processor during development for in-depth debugging.
- A hardware emulator (like an in-circuit emulator) physically connects to the target system, providing a real-time debugging environment that a simulator cannot.
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
## ASIP vs GPP
| Feature              | Application-Specific Instruction-Set Processor (ASIP)                                                                                                                                                   | General-Purpose Processor (GPP)                                                                                                                           |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Definition**       | A processor whose instruction set is optimized for a specific domain or class of applications (e.g., digital signal processing, networking).                                                            | A processor designed for a wide range of applications. It is a "jack-of-all-trades."                                                                      |
| **Instruction Set**  | **Specialized and tailored.** Includes custom instructions that accelerate common operations within a specific application domain (e.g., a single instruction for a complex filter operation in a DSP). | **General and broad.** Includes a wide variety of instructions to handle different types of tasks (e.g., arithmetic, logic, control flow, memory access). |
| **Design Goal**      | Maximize **efficiency** (performance per watt, performance per unit area) for a specific set of tasks.                                                                                                  | Maximize **flexibility** and performance across many different software applications.                                                                     |
| **Flexibility**      | **Limited to its Domain.** Highly flexible _within_ its target application area but not suitable for general-purpose computing tasks.                                                                   | **Very High.** Can run virtually any software, from operating systems to word processors and games.                                                       |
| **Performance**      | **Very High for its Target Applications.** Custom instructions can perform complex operations in a single cycle that might take dozens of cycles on a GPP.                                              | Good average performance for a wide variety of tasks. May be inefficient for specialized, repetitive tasks (like signal processing).                      |
| **Power Efficiency** | **Higher.** Optimized datapaths and specialized instructions mean the task is completed in fewer cycles, saving power. Ideal for battery-powered embedded devices.                                      | **Lower.** The overhead of fetching and decoding a large, general instruction set consumes more power.                                                    |
| **Cost (NRE)**       | **Higher NRE cost.** Requires significant design effort to create the specialized instruction set and microarchitecture.                                                                                | **Lower NRE cost.** Designed as a high-volume, off-the-shelf component. The development cost is amortized over millions of units.                         |
| **Unit Cost**        | Can be lower than a high-end GPP for a specific task, as it doesn't need unnecessary hardware.                                                                                                          | Low to medium, depending on the performance tier.                                                                                                         |
| **Time to Market**   | **Slower.** Requires a longer design and verification phase for the processor itself.                                                                                                                   | **Faster.** You can buy a GPP off the shelf, write software, and deploy.                                                                                  |
| **Programmability**  | More complex to program. It may require specialized compilers or even assembly coding to fully utilize the custom instructions.                                                                         | Easy to program using standard high-level languages (C, C++) and familiar development tools.                                                              |
| **Examples**         | TI OMAP (for mobile multimedia), CEVA-XC (for DSP and communications), network processors.                                                                                                              | Intel Core i7, AMD Ryzen, ARM Cortex-A series (found in smartphones).                                                                                     |

---
# 3.6 Selecting a Microprocessor
### Key Factors in Processor Selection
#### A. Technical Aspects
These are the hardware and performance-related constraints that the processor must meet.
- **Performance (Speed):** Does the processor have enough computational power to execute the tasks within their required time frames (real-time constraints)?
- **Power Consumption:** Can the processor operate within the system's power budget? This is crucial for battery-powered devices, where it determines battery life, and for high-performance systems, where it dictates cooling requirements.
- **Size (Footprint):** Does the physical size of the processor package fit within the product's space constraints?
- **Cost:** Does the per-unit cost of the processor fit within the product's bill of materials (BOM) budget?
- **Architecture:**
    - **Bit Width:** Is a low-power 8-bit controller sufficient, or is a high-performance 32-bit or 64-bit processor required?
    - **Instruction Set Architecture (ISA):** Will it be a complex instruction set computer (CISC) or a reduced instruction set computer (RISC)? The choice affects code density and performance.
    - **Cores:** Is a single-core processor enough, or is a multi-core processor needed to handle parallel tasks?
#### B. Non-Technical Aspects
These factors significantly influence the development process, cost, and long-term viability of the product.
- **Familiarity and Expertise:** Does the design team have prior experience with a particular processor family or architecture? Using a familiar processor can drastically reduce development time and risk.
- **Development Environment (Toolchain):** What is the quality and cost of the software development tools?
    - **Compiler Support:** Is there a robust C/C++ compiler that generates efficient code?
    - **Debuggers:** Are there good hardware and software debuggers available (e.g., JTAG debuggers, IDEs)?
    - **Simulators:** Are there accurate simulators for early software development before hardware is ready?
- **Operating System (OS) Support:** If the project requires an embedded OS or RTOS, does the processor have good support for the chosen OS (e.g., Linux, FreeRTOS, QNX)? Are the necessary drivers and Board Support Packages (BSPs) available?
- **Licensing and Royalties:** Some processor cores (like those from ARM) require licensing fees. This can be a significant non-recurring engineering (NRE) cost.
- **Roadmap and Longevity:** Is the processor likely to be available for the entire lifespan of the product? Is there a clear upgrade path to future generations?
- **Second Sourcing:** Are there multiple manufacturers for the same processor or pin-compatible alternatives? This mitigates the risk of supply chain disruptions.
- **Community and Support:** Is there a large user community and good technical support from the manufacturer? This can be invaluable for troubleshooting.
---
### Comparing Processor Speed
Comparing the speed of different processors is not as straightforward as comparing their clock frequencies. Several metrics are used, each with its own advantages and limitations.
#### 1. Clock Speed
- **Metric:** The frequency of the processor's clock (e.g., 100 MHz, 2 GHz).
- **Issue:** This is a poor metric for cross-architecture comparison. Different processors can execute a different number of instructions per clock cycle (IPC). A processor with a lower clock speed but a higher IPC can outperform a processor with a higher clock speed but a lower IPC.
#### 2. Instructions Per Second (IPS)
- **Metric:** The number of instructions executed in one second (e.g., Million Instructions Per Second or MIPS).
- **Issue:** While better than raw clock speed, it can be misleading. The "complexity" of an instruction varies greatly between architectures. A single instruction on a CISC processor might do the work of several instructions on a RISC processor. To perform the same high-level operation (e.g., a complex math function), Processor A might need 200 simple instructions, while Processor B might need 300. Comparing raw MIPS in this case would incorrectly suggest Processor A is faster.
#### 3. Dhrystone Benchmark
- **Metric:** A synthetic benchmark program written in C that measures a processor's performance on integer arithmetic and string operations. The result is given in **Dhrystones per second** (the number of times the benchmark loop can be executed in one second).
- **Advantage:** It provides a more realistic, application-oriented measure of performance than MIPS. It is widely used and understood in the industry.
- **Origin and MIPS Relationship:** The benchmark was originally run on a VAX 11/780 minicomputer, which scored 1757 Dhrystones per second. This machine was defined as a **1 MIPS** machine. Therefore, a common (though aging) conversion factor is:
    - **1 MIPS ≈ 1757 Dhrystones/second**
- Using this, the performance of other processors can be compared to the classic VAX 11/780.
# 3.7 General-Purpose Processor Design
