- **6 Hours**
- **8 Marks**
# 5.1 Communication Basics
## 5.1.A Interfacing Concepts
### 1.A.i Definition
- Interfacing refers to the process of connecting two or more distinct devices, components, or systems to enable them to communicate and exchange information with each other
- It involves both hardware (physical connections) and software (protocols) elements that work together to ensure successful data transfer between the connected entities.
### 1.A.ii Need
1. **Compatibility Bridge**
    - Connects devices operating at different voltage levels, speeds, or data formats
    - Translates signals between incompatible components
2. **Resource Sharing**
    - Allows multiple devices to share common resources like memory, processors, or I/O devices
    - Enables efficient utilization of system components
3. **System Expansion**
    - Facilitates addition of new peripherals and components to existing systems
    - Provides scalability and upgradeability
4. **Signal Conditioning**
    - Converts signals between different forms (analog to digital, voltage level shifting)
    - Ensures signal integrity during transmission
5. **Data Synchronization**
    - Coordinates timing between fast processors and slow peripherals
    - Manages data flow to prevent loss or corruption
6. **Protocol Conversion**
    - Translates between different communication protocols
    - Enables devices speaking different "languages" to communicate
## 5.1.B Terminology
1. Wires
	- Connecting lines between two terminals in a communication system
	- Can be *uni-directional* (data flows one way) or *bi-directional* (data flows both ways)
	- A single line in diagrams may represent multiple wires, indicated by a small angled line drawn through it
2. Bus
	- Refers to a set of wires serving a single function
	- Examples of single-function buses:
	    - Address bus: carries memory or peripheral addresses
	    - Data bus: carries actual data being transferred
	- Can be a collection of multiple wires
	- System bus: consists of data lines and control lines combined
	- figure: simple bus example
		- ![[Pasted image 20260310091253.png]]
3. Port
	- The actual conducting device on the periphery that connects a bus to a processor, memory, or other devices
	- The medium through which signals are input to or output from a process
	- Physical forms:
	    - Pin: extends from IC package and plugs into a socket on PCB
	    - Metallic ball: alternative to pins in some packages
	    - Metal pad: common in modern surface-mount technology
4. Timing Diagram
	- A diagrammatic representation used to describe hardware protocols
	- Characteristics
		- Time proceeds from left to right along the x-axis
		- Shows the state of control lines or data lines over time
		- Control lines: shown as either low (0) or high (1)
		- Data lines (address/data): shown as valid or not valid 
	- Key terms:
		- Active high: a '1' on the line makes it active
		- De-asserting: making a line inactive
		- Bus cycle/transaction: a sub-protocol within a larger protocol
		- Bus cycles may consist of several clock cycles
	- Example: timing diagram for read protocol
		- the processor must set the `rd'/wr` line low for a read operation
		- address of memory must be placed on `addr` line for atleast t_setup time before setting the enable line high
		- setting enable line high will cause memory to place the data on the data line after at time t_read
		- figure:
			- ![[Pasted image 20260310091321.png]]
## 5.1.C Basic Protocol Concepts
1. Actor
	- Any device (processor, memory, peripheral) participating in data transfer
	- Types:
	    - Master: initiates the data transfer
	    - Slave: responds to the master's initiation request
2. Data Direction
	- represents movement of data among actors.
	- the direction of data is independent of type of actor
	- either master/slave can send/receive data
3. Address
	- Special kind of data that specifies:
	    - A location in memory
	    - A peripheral device
	    - A register within a peripheral
	- Protocols typically include both address and data components 
	- In every memory access protocol, the address specifies where data should be read from or written to.
4. Time multiplexing
	- Technique where multiple sets of data are sent one at a time over a shared line
	- Advantage: reduces the number of wires required (at the cost of time)
	- the following figure show the example of multiplexing
		- both cases: single bus is used to send multiple data at different time instant.
		- ![[Pasted image 20260310091713.png]]
## 5.1.D Control methods
- Schemes for initiating and ending data transfer between devices.
1. Strobe Protocol
	- Working
		1. Master activates a control line to initiate transfer
		2. Slave has a specified time (`t_access`) to place data on the bus
		3. Master assumes data is valid and reads it
		4. Master deactivates control line
		5. Both actors ready for next transfer
	- Adv: Simple and fast
	- Disadv: No confirmation that slave actually received/sent data
	- Best for: Systems with predictable response times
	- Figure:
		- ![[Pasted image 20260310092410.png]]
	- Explanation:
		1. Master asserts `req` to receive data
		2. servant puts on `data` line within time `t_access`
		3. master receives data and deasserts `req`
		4. servant ready for next request
2. Handshake Protocol
	- Working
		1. Master asserts request line
		2. Slave prepares data and asserts acknowledge line when ready
		3. Master reads data and deasserts request
		4. Slave deasserts acknowledge
		5. Transfer complete
	- Adv: more reliable, data availability is confirmed
	- Disadv: more complex, potentially slower
	- Best for: systems with variable response times or where reliability is critical
	- figure:
		- ![[Pasted image 20260310092835.png]]
	- Explanation:
		1. Master asserts `req` line to receive dataa
		2. servant puts data on `data` line and asserts `ack`
		3. master receives data from data bus and deasserts `req`
		4. servant ready for next transfer
3. Strobe/Handshake Compromise
	- Combines speed of strobe with reliability of handshake
	- Uses an additional `wait` line for slow responses
	- Adv: best of both worlds - fast when possible, reliable when needed
	- Best for: systems with mostly predictable but occasionally slow responses
	- figure:
		- ![[Pasted image 20260310093100.png]]
	- Explanation of fast response
		- Master asserts `req` line to receive data
		- servant puts data on data bus within time t_access, wait line remains unused
		- Master receives data and deasserts `req`
		- servant ready for next request
	- For slow response
		- master asserts `req` to receive data
		- servant can't put data within t_access asserts `wait` line
		- servant puts data on bus and deasserts `wait`
		- master receives data and deasserts `req`
		- servant ready for next request
4. Example: The ISA Bus Protocol - Memory Access
	- Industry Standard Architecture (ISA) bus protocol used with 80x86 microprocessors, featuring:
		- 20-bit memory addressing
		- Compromise strobe/handshake protocol
		- 4-cycle default operation
		- wait cycles inserted when memory is not ready
	- the timing diagram for memory read operation and memory write operation is shown in the figure below.
		- ![[Pasted image 20260310093759.png]] ![[Pasted image 20260310093809.png]]
	- Explanation
		- Write Operation:
			- in C1, processor puts 20 bit address memory address on the address line and asserts ALE signal
			- during C2 and C3 clock cycles, the processor puts the data on the data line and asserts MEMWW signal to enable write operation
			- however if the memory when not ready deasserts CHRDY signal in C2 then processor inserts wait cycles until CHRDY is reasserted
			- in cycle C4, all signals are deasserted
---
# 5.2 Microprocessor Interfacing
## 5.2.A I/O Addressing
- Refers to the methods by which a processor communicates with peripheral devices.
### 2.A.i Port Based I/O
- **Concept**:
	- A method where ports can be directly read from or written into using processor instructions.
- **Key Characteristics**:
	- aka Parallel IO
	- devices typically have one or more N-bit ports
	- each port is bit addressable (individual pins can be controlled)
	- no separate address bus required.
- **Examples**:
	- 8051 and AVR microcontrollers have 8-bit I/O ports
	- in 8051: P1 = `0xF7` writes to entire Port 1
	- bit addressing: `P2.4 = 1` sets pin 4 of Port 2 high
- **Extension**:
	- Port based I/O can be expanded using peripheral chips
	- Each extended port has an associated register that the processor can read/write
	- typical expansion: from 4 ports to 6 or more
- **Adv**:
	- Simple and direct
	- fast for small systems
	- individual bit control
- **Disadv**:
	- limited number of ports
	- not scalable for large systems
- **Figure**:
	- Port Based I/O and extended Parallel I/O
	- ![[Pasted image 20260310100639.png]]
### 2.A.ii Bus Based I/O
- **Concept**:
	- A method where the processor has dedicated address, data, and control lines for I/O operations, with built-in communication protocols.
- **Key Characteristics**:
	- Communication protocol is built into the processor.
	- single instruction causes hardware to read/write data
	- parallel i/o peripherals can be connected to the system bus when needed.
- **Operation**:
	- Processor uses address bus to select device
	- Data bus carries the actual data
	- Control lines determine operation type (r/w)
- **Adv**:
	- standardized communication
	- supports many devices
	- well-defined protocols
- **Disadv**:
	- more complex than port-based I/O
	- requires bus arbitration for multiple devices.
- if a system with bus based I/O requires parallel I/O then parallel I/O peripheral can be connected to the system bus.
	- bus based i/o and extended bus based i/o with paralel i/o peripheral
	- figure:
		- ![[Pasted image 20260310141017.png]]
### 2.A.iii Memory-Mapped I/O
- **Concept**:
	- A type of bus-based I/O where peripherals are addressed using existing memory address space.
- **Key Characteristics**
	- total address space is divided between memory and peripherals
	- peripherals appear as memory locations to the processor.
	- same instructions work for both memory and i/o (e.g., MOV)
- Address space division example:
	- 16-bit bus = 65k total addresses
	- lower 32k address -> memory
	- higher -> i/o devices
- **Adv**:
	- no special i/o instructions needed
	- all memory access instructions can be used with peripherals
	- simpler programming model
- **Disadv**:
	- loss of memory addresses to peripherals
	- address decoding is mroe complex
	- can reduce available memory space
### 2.A.iv Standard I/O
- **Concept**:
	- type of bus based I/O that uses extra control line (M/IO) to distinguish between memory and I/O addresses.
	- aka isolated I/O
- **Key Characteristics**
	- separate address space for memory and I/O
	- both use full address range simultaneously.
	- M/IO line determines which space is being accessed
	- Requires special instructions for I/O operations
- **Address space examples**
	- 16-bit bus = 65k addresses
	- all 65k can be used for memory
	- and for I/O, selected by M/IOI
- **Instruction Set**
	- Memory: MOV, LOAD, STORE
	- I/O: IN, OUT (special instructions)
- **M/IO line operation**
	- M/IO = 0: address on bus corresponds to memory location
	- M/IO = 1: address on bus corresponds to I/O device
- **Adv**:
	- No loss of memory addresses
	- Simple address decoding (high-order bits can be ignored when few peripherals)
	- separate instruction sets prevent confusion
- **Disadv**:
	- Requires special I/O instructions
	- More complex processor design
- Example: figure of timing diagram for ISA Bus Protocol - Standard I/O
	- ![[Pasted image 20260310141731.png]]
- Example: basic memory protocol figure:
	- ![[Pasted image 20260310141754.png]]
### 2.A.v Example: 8051 Microcontroller Memory Interface
- **Address Placement:**
	- **Port 2 (P2):** Holds the 8 most significant address bits (retained throughout operation)
	- **Port 0 (P0):** Holds the 8 least significant address bits
- **Read Operation Sequence:**
	1. Microcontroller places source address on P2 and P0
	2. **ALE (Address Latch Enable)** signal triggers latching of P0 address in external latch
	3. Controller places P0 in **high-impedance state** to allow memory to drive data lines
	4. **RD** signal is asserted
	5. Memory outputs valid data as long as RD is active
	6. Microcontroller reads data
	7. Control and port signals are deasserted
### 2.A.vi Comparison
| Feature           | Port Based I/O     | Bus Based I/O     | Memory-Mapped I/O   | Standard I/O             |
| ----------------- | ------------------ | ----------------- | ------------------- | ------------------------ |
| **Address Space** | None (ports only)  | Separate bus      | Shared with memory  | Separate (M/IO line)     |
| **Instructions**  | Direct port access | Built-in protocol | Memory instructions | Special I/O instructions |
| **Memory Loss**   | N/A                | No                | Yes                 | No                       |
| **Complexity**    | Low                | Medium            | Medium              | High                     |
| **Scalability**   | Low                | High              | High                | High                     |
| **Typical Use**   | Microcontrollers   | General purpose   | Embedded systems    | x86 processors           |
## 5.2.B Interrupts
- Peripherals may require processor service at unpredictable times. 
- Two approaches address this:
### 2.B.i Polling
- **Concept**: 
	- The processor continuously checks each peripheral's service requirement status.
- **Operation**:
	- Processor regularly examines each device's status register
	- If service needed, it executes appropriate routine
	- Then continues checking cycle
- **Advantages**:
	- Simple to implement
	- Predictable behavior
	- No special hardware required
- **Disadvantages**:
	- **Wastes clock cycles** on repeated checking
	- Inefficient for rare events
	- Response time depends on polling frequency
### 2.B.ii Interrupts
- **Concept**:
	- A processor feature that allows peripherals to request service even when the processor is busy with its own tasks.
- **Key Concept:**
	- Interrupts are actually a form of polling, but:
	- The interrupt pin is checked after **every instruction execution**
	- No extra clock cycles wasted on polling loops
	- Response is immediate when needed
- **External Interrupt Implementation:**
	- Dedicated pin available for interrupt feature
	- When interrupt pin asserted, processor:
	    1. Completes current instruction
	    2. Saves current context (at least PC)
	    3. Jumps to predetermined address (Interrupt Service Routine)
	    4. Executes ISR
	    5. Returns to main program
#### B.ii.a Interrupt Address Vector
- The address where the ISR resides.
##### ii.a.1 Fixed Interrupt
- **Characteristics**:
	- ISR address is built into the microprocessor
	- remains fixed for specific interrupt types
	- programmer must store ISR at that exact location
- **Implementation Options**:
	- Place entire ISR at the fixed address
	- Place a jump instruction at fixed address pointing to actual ISR location
- **Adv**:
	- simple hardware design
	- fast vector determination
	- predictable
- **Disadv**:
	- inflexible
	- may require jump instructions
- **Example**:
	1. P1 has data; processor executes main program
	2. P1 asserts INT to request service
	3. Processor checks INT after each instruction -> detects request
	4. Processor saves context, sets PC to fixed ISR location
	5. ISR executes: reads P1 data, processes it, sends to P2
	6. P1 deasserts INT after data read
	7. processor restores context. resumes main program
##### ii.a.2 Vectored Interrupt
- **Characteristics**:
	- Peripheral provides the ISR address to the processor
	- requires additional INTA (interrupt acknowledge) pin
- **Hardware Requirements**
	- INT pin: peripheral requests interrupt
	- INTA pin: processor acknowledges and requests vector
- **Operation**:
	1. Peripheral places interrupt vector on data bus when INTA received
	2. Processor reads vector and jumps to thaht address
- **Adv**:
	- Flexible ISR placement
	- multiple devices can share interrupt lines
	- dynamic input handling
- **Disadv**:
	- more complex hardware
	- requires additional pin
	- slower response (additional bus cycle)
- **Example**:
	1. P1 has data; processor executes main program
	2. P1 asserts INT
	3. Processor detects INT, asserts INTA
	4. P1 places interrupt vector on data bus
	5. Processor jumps to vector address, executes ISR
	6. ISR reads P1 data, processes, sends to P2
	7. P1 deasserts INT
	8. Processor resumes main program
##### ii.a.3 Interrupt Address Table
- Compromise Method
- **Characteristics**:
	- hybrid approach between fixed and vectored interrupts
	- table of isr addresses stored in memory
	- peripheral provides table index number, not full address
- **Operation**:
	1. Peripheral provides n-bit number (e.g., 8 bit = 256 possible entries)
	2. Processor uses number as index into interrupt table
	3. Table contains an actual ISR addresses
	4. Processor jumps to address from table
- **Adv**:
	- fewer bits needed from peripheral (saves hardware)
	- flexibility to change ISR locations
	- faster than full vectoring
	- supports many interrupt sources
- **Disadv**:
	- requires table memory
	- slightly slower than fixed interrupts
#### B.ii.b Additional Interrupt Concepts
##### ii.b.1 Maskable vs. Non-Maskable Interrupts
- **Maskable Interrupts:**
	- Can be **enabled/disabled** by programmer
	- Controlled via interrupt register bits
	- Important for prioritizing critical tasks
	- Example: `DI` (Disable Interrupts) instruction
- **Non-Maskable Interrupts (NMI):**
	- **Cannot be disabled** by programmer
	- Requires dedicated pin
	- Used for **drastic situations**
	- Example: Power failure detection
	    - NMI triggers routine to save critical data to non-volatile memory
	    - Executes before power completely fails
##### ii.b.2 Context Saving
| Processor Type      | What is Saved                   | Characteristics                         |
| ------------------- | ------------------------------- | --------------------------------------- |
| **Full context**    | PC, all registers, status flags | Slower, but ISR can use any register    |
| **Partial context** | PC only                         | Faster, but ISR must preserve registers |
**Implications:**
- Full context saving: more cycles consumed
- Partial context: ISR must not modify unsaved registers
- Some processors use **banked registers** (switch to alternate register set)
## 5.2.C Direct Memory Access
### 2.C.i Concept
- When the communication between memory and peripherals involves microprocessor then there will, somehow, always be waste of processor's time.
- since the speed of the processor and peripherals may not match, data must be stored temporarily before processing which is referred as buffering.
- buffering will impact on system performance.
- also while using interrupt feature, the storing and restoring of state of processor is an inefficient process, since this process requires many clock cycles.
- and the regular program stalls during transfer of data causing more problems in the performance of the system.
- so, a separate single-purpose processor called a DMA controller is required which relieves processor from all data transfers involving memory and peripherals.
- DMA controller is specifically used to transfer data between memories and peripherals.
- the peripherals request the service from DMA controller which then requests control of the system bus from processor.
- after that, processor relinquishes the system bus.
- finally, the data transfer between memory and peripheral is initiated by DMA controller without the involvement of processor.
- hence, the overhead required for storing and restoring the state is eliminated. 
- also, the processor can continue its regular task unless it requires the system bus or the particular data being transferred.
### 2.C.ii Block Diagram
![[Pasted image 20260224174155.png]]
### 2.C.iii Operation
1. processor is busy executing its main program
2. after peripheral has data within its register it asserts request line for service from DMA
3. DMA asserts request to request the system bus from processor.
4. processor releases the system bus after seeing the request form DMA, and acknowledges about it to DMA
5. DMA asserts acknowledge signal to peripheral, and starts transfer of data as requested
6. after the completion of transfer, all control lines are deasserted and processor retakes the control of teh system bus.
---
# 5.3 Arbitration
- mechanism through which a service or shared resource is provided to particular requesting device, out of many contenting devices for service.
## 5.3.A Priority Arbiter
### 3.A.i Introduction
- single purpose processor which is used to arbitrate among various requests from peripherals.
- each of the peripherals, which are connected to the arbiter can make request for the service
- using certain priority mechanism, arbiter selects a peripheral to permit the required service.
- the main advantage of this arbitration is that it can support advanced priority schemes.
- also failure of a single peripheral doesn't have any impact on the operation of whole system.
- the system must be redesigned if new peripherals are to be added.
- so this method is less flexible if new perpherals are required to be added or removed.
- arbiter is connected to system bus for configuration only
- the configuration may include setting priorities of the peripherals.
### 3.A.ii Block Diagram
![[Pasted image 20260224175540.png]]
### 3.A.iii Operation
1. microprocessor is busy in its own operation
2. both peripherals can assert request to priority arbiter which interrupts processor when atleast one request is available from peripherals
3. processor stops its current operation, stores its state and asserts interrupt acknowledgement signal
4. after acknowledged by processor, priority arbiter asserts acknowledge signal to any one peripheral based on priority.
5. the selected peripheral puts its interrupt address vector on the system bus.
6. microprocessor reads ISR address from data bus and jumps into it, executes the ISR
7. after execution of requested ISR, processor retrieves its state and resumes its operation.
### 3.A.iv Types of Arbiter
#### A.iv.a Fixed Priority
- each priority is assigned a unique rank
- if two peripherals simultaneously rquest for service then the arbiter chooses the one with the higher rank.
- such method is efficient when there is a clear distinction in priority in priority among peripherals. But it can cause high-ranked peripherals to get much more servicing than other peripherals.
#### A.v.a Rotating Priority
- aka round robin
- each peripheral gets almost equal time for service from the arbiter.
- this priority method is efficient when there is not much difference in priority among peripherals.
- the priority of peripherals change based on the history of servicing of those peripherals, so the arbiter can get more complex in rotating activity
---
## 5.3.B Daisy Chain Arbitration
### 3.B.i Introduction
- peripherals are connected to each other in daisy-chain manner.
- the arbitration is built within the peripherals with each having acknowledge signals.
- the request signal and acknowledge signals flow through the peripherals:
	- peripheral's request signal flows downstream to processor
	- and processor's acknowledge signal flows upstream to requesting peripheral.
- the peripheral connected first to the processor has the highest priority while the peripheral at the end of chain has lowest priority.
- the main advantage of this arbitration method is that one can easily add or remove peripherals from the system without requirement of system redesign.
- this method does not support rotating priority.
- also, if one peripheral is damaged in the chain, other peripherals beyond that broken point will remain inaccessible as signal cannot pass through the chain.
### 3.B.ii Block Diagram
![[Pasted image 20260224183933.png]]
### 3.B.iii Operation
1. Microprocessor is busy in executing its own program.
2. the request signal from peripheral 2 is send to processor through the peripheral 1 and interrupt pin is asserted
3. processor stops its current work, stores its state, and assert acknowledgement signal.
4. the acknowledgement signal reaches to peripheral 2 through peripheral 1.
	1. since the request is not generated by peripheral 1, it passes the acknowledge signal to peripheral 2
5. peripheral 2 puts its interrupt address vector on the system bus.
6. microprocessor reads ISR address vector on the system bus.
7. after execution of requested ISR, processor retrieves its state and resumes its operation.
### 3.B.iv Daisy Chain aware peripherals
- generally peripherals have acknowledge input and request out lines but daisy chain aware peripherals must have additional acknowledge output and request input lines.
- however, if the peripherals do not contain acknowledge output and request input lines then they will not be daisy chain aware peripherals.
- but they can be made daisy chain aware by certain logic whose complexity may increase based on complexity of system.
- one simple example for making a peripheral daisy chain aware is shown in the figure below.
#### # Diagram
![[Pasted image 20260224184444.png]]
#### Explanation
Case 1: When request is from downstream peripherals
- peripheral (P) does not paricipate in the flow of signal
Case 2: When request is from upstream peripherals beyond P
- `REQ_IN` = 1, but `REQ` = 0, resulting in `REQ_OUT` = 1
- `ACK_IN` = 1 and `REQ` = 0, resulting in `ACK_OUT` = 1
Case 3: When request is from P
- `REQ` = 1, `REQ_IN` = X (don't care), resulting in `REQ_OUT` = 1
- `ACK_IN` = 1, and `REQ` = 1 resulting in `ACK` = 1 and `ACK_OUT` = 0
---
## 5.3.C Network-Oriented Arbitration
- arbitration is done for multiple microprocessors sharing a common to form a network.
- arbitration is build into the bus protocol, as bus is the only the medium that connects multiple processors
- however, multiple processors may try to access the bus simultaneously resulting in data collision.
- the protocol must be designed in such a way that the contending processors don't start sending the data at the same time.
- also some statistical methods can be used so as to make chances of data collision very rare, if not eliminate it.
- some protocols use efficient address encoding schemes in which higher priority address will override the lower-priority one.
---
# 5.4 Multilevel Bus Architectures
- Multilevel bus architectures are implemented in computer systems to improve overall system performance by using multiple buses at different speed levels rather than a single high-speed bus.
## 5.4.A Drawbacks of Single Bus
### 4.A.i Inefficient Interface
- When using a single high-speed bus, every peripheral must have a high-speed interface, regardless of its actual requirements.
- **Consequences:**
	- **Extra power consumption** - High-speed interfaces consume more power even when not needed
	- **Increased gate count** - More complex interface logic requires more transistors
	- **Higher cost** - More expensive components and design
	- **Non-portable interfaces** - High-speed buses are often processor-specific, making peripherals incompatible across different systems
### 4.A.ii Slower Bus
- When many peripherals share a single bus, they compete for access, creating bottlenecks.
- **Consequences:**
	- **Bus contention** - Multiple devices trying to use the bus simultaneously
	- **Access delays** - Peripherals must wait their turn for bus access
	- **Performance lag** - Overall system throughput decreases
	- **Unpredictable response times** - Critical devices may experience delays
## 5.4.B Two level Bus Systems
### 4.B.i Architecture Overview
- A two-level bus system divides communication into two distinct layers:
	1. **Processor Local Bus** (High-speed)
	2. **Peripheral Bus** (Low-speed)
	3. **Bridge** (Connects the two)
- Figure: Two level bus architecture:
	- ![[Pasted image 20260310153900.png]]
### 4.B.ii Processor Local Bus
-  The high-speed bus that connects the processor to critical, high-performance components.
- **Connected Devices:**
	- Microprocessor(s)
	- Cache memory (L1, L2)
	- Memory controllers
	- High-speed coprocessors (FPU, GPU, DSP)
	- High-bandwidth devices
- Characteristics:
	- **Speed**: Very high - matches processor clock speeds
	- **Width**: Wide - often matches memory word size (32, 64, or 128 bits)
	- **Frequency**: Frequent communication - every clock cycle
	- **Protocol**: Processor-specific, optimized for speed
	- **Purpose**: Maximum performance for critical components
### 4.B.iii Peripheral Bus
- **Definition:** The lower-speed bus that connects peripherals that don't require direct access to the processor local bus.
- **Connected Devices:**
	- I/O controllers
	- Storage devices (HDDs, SSDs through controllers)
	- Network interfaces
	- USB controllers
	- Legacy devices
	- Slow peripherals (keyboard, mouse, sensors)
### 4.B.iv Bridge
- A specialized processor or controller that connects the two buses and manages communication between them.
- Functions:
	- **Protocol Conversion**: Translates between different bus protocols
	- **Speed Synchronization**: Matches different operating speeds
	- **Data Format Conversion**: Adapts data widths and formats
	- **Buffering**: Stores data temporarily during transfers
	- **Management**: Directs and prioritizes bus traffic
- Operation details:
	1. **Protocol Translation:**
	    - Converts processor-local bus commands to peripheral bus commands
	    - Translates addressing schemes
	    - Handles different signaling methods
	2. **Speed Matching:**
	    - Buffers high-speed data from processor bus
	    - Releases data at peripheral bus speed
	    - Prevents fast devices from overwhelming slow ones
	3. **Data Width Adaptation:**
	    - Splits wide processor bus transactions (e.g., 64-bit) into multiple narrower peripheral bus transactions (e.g., 4 × 16-bit)
	    - Combines multiple peripheral bus transactions for processor bus
	4. **Electrical Isolation:**
	    - Provides electrical buffering between different bus domains
	    - Prevents peripheral issues from affecting the processor bus
### 4.B.v Characteristics
| Feature        | Description                                |
| -------------- | ------------------------------------------ |
| **Speed**      | Lower - matched to peripheral capabilities |
| **Width**      | Narrower - often 8, 16, or 32 bits         |
| **Frequency**  | Less frequent - burst transfers            |
| **Protocol**   | Standardized, emphasis on portability      |
| **Power**      | Optimized for low power consumption        |
| **Gate Count** | Lower - simpler interface logic            |
| **Cost**       | Lower - economical for peripherals         |

## 5.4.C Three level bus hierarchy
### 4.C.i Architecture Overview
The three-level system adds an intermediate layer for better traffic management:
1. **Processor Local Bus** (Highest speed, processor-specific)
2. **System Bus** (High-speed, standardized)
3. **Peripheral Bus** (Lower speed, peripheral-focused)
### 4.C.ii Processor Local Bus
- **Role:** 
	- Connects processor to the most time-critical components.
- **Components:**
	- CPU core(s)
	- L1/L2 cache
	- Local memory controller
- **Characteristics:**
	- Highest speed in the system
	- Minimal latency
	- Processor-specific design
	- Limited devices
### 5.4.C.iii System Bus
- **Role:** 
	- High-speed backbone that offloads traffic from the processor local bus.
- **Components:**
	- Main memory
	- High-speed I/O controllers
	- Graphics controllers
	- Bridge to peripheral bus
- **Advantages:**
	- **Offloads traffic** - Reduces burden on processor local bus
	- **Standardized interface** - More portable than processor-specific buses
	- **High bandwidth** - Supports multiple high-speed devices
	- **Parallel operation** - Can operate concurrently with processor local bus
### 5.4.C.iv Peripheral Bus
- **Role:**
	- Connects slower peripherals and legacy devices.
- **Components:**
	- USB controllers
	- SATA controllers
	- Audio devices
	- Network interfaces
	- Legacy I/O
- **Characteristics:**
	- Slowest in hierarchy
	- Low power
	- Simple interface
	- Often backward compatible
# 5.5 Advanced Communication Principles
## 5.5.A Parallel Communication
**Definition:** Multiple bits of data transmitted simultaneously over multiple wires.
**Characteristics:**
- Bus consists of multiple data wires + control and power lines
- Each wire carries one bit
**Advantages:**
- **High throughput** - Multiple bits transferred per cycle
- **Simple hardware** - Only requires latches to copy data onto bus
**Disadvantages:**
- **Ferranti Effect** - Voltage buildup due to capacitance can make receiving end voltage exceed sending end
- **Data misalignment** - Slight wire length variations cause bits to arrive at different times (skew)
- **Costly construction** - More wires = bulkier, expensive cabling
- **Interference issues** - Requires insulation between parallel wires
**Usage:** Devices on same circuit board or IC (short distances)

## 5.5.B Serial Communication
**Definition:** One bit of data transmitted at a time over a single wire.
**Characteristics:**
- Single data wire + control and power lines
- Bits travel sequentially
**Advantages:**
- **Reduced cost/size** - Fewer wires, simpler connectors
- **Better for long distances** - Outperforms parallel for distant devices
- **No Ferranti Effect** - No voltage buildup issues
- **No data misalignment** - Single path eliminates skew
**Disadvantages:**
- **Complex logic required** - Must decompose data at sender and reassemble at receiver
- **Lower throughput** over short distances compared to parallel
**Usage:** Distant devices (though can be used for short distances, less efficient)

## 5.5.C Wireless Communication
**Definition:** No physical connection required; uses electromagnetic waves.
### 5.C.i Infrared Communication
**How it works:**
- Uses frequencies below visible light spectrum
- IR diode generates waves; IR transistor detects them (conducts when exposed)
**Advantages:**
- **Low cost** - Cheap transmitters and receivers
**Disadvantages:**
- **Line of sight required** - Obstacles block communication
- **Short range** - Inefficient for distant devices
### 5.C.ii Radio Frequency Communication
**How it works:**
- Uses EM waves in radio spectrum
- Requires antenna + analog circuitry
**Advantages:**
- **No line of sight needed** - Penetrates obstacles
- **Long distance possible** - Range depends on transmission power
**Disadvantages:**
- **Complex design** - Analog circuitry increases complexity
- **Higher cost** - More expensive than infrared

## 5.5.D Layering
**Definition:** Breaking down communication into smaller, interdependent categories, each handling a distinct aspect of data exchange.
**Key Concepts:**
- **Hierarchical organization** - Lower levels provide services to higher levels
- **Objective:** Reduce complexity through simplified, manageable levels
**Example:**
- **Physical layer** - Lowest level: sending/receiving bits or words
- **Application layer** - Highest level: services visible to user

## 5.5.E Error Detection and Correction
### 5.E.i Error Detection
**Definition:** Process of identifying transmission errors.
**Types of Errors:**

| Type            | Description                         |
| --------------- | ----------------------------------- |
| **Bit error**   | Single bit corrupted                |
| **Burst error** | Multiple consecutive bits corrupted |
### 5.E.ii Error Correction
**Definition:** Process of correcting detected errors.
### 5.E.iiiParity Check Method
**How it works:**
- Extra bit (parity bit) sent with data
- Provides additional information about the data
**Parity Types:**

| Type            | Definition                                 |
| --------------- | ------------------------------------------ |
| **Odd parity**  | Total number of 1s (data + parity) is odd  |
| **Even parity** | Total number of 1s (data + parity) is even |
**Process:**
1. Calculate parity at sender
2. Send data + parity bit
3. Recalculate parity at receiver
4. Compare - must match for error-free transmission
**Limitations:**
- Works for **single bit errors**
- Fails for **burst errors** with even number of bit flips
- Cannot detect which bit is corrupted, only that error occurred

