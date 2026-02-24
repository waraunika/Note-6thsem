- **6 Hours**
- **8 Marks**
# 5.1 Communication Basics
# 5.2 Microprocessor Interfacing
## 5.2.A I/O Addressing
## 5.2.B Interrupts
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
- also, the processor can continue its regulr task unless it requires the system bus or the particular data being transferred.
### 2.C.ii Block Diagram
![[Pasted image 20260224174155.png]]
### 2.C.iii Operation
1. processor is busy executing its main program
2. after peripheral has data within its register it asserts request line for service from DMA
3. DMA asserts request to request the system bus from processor.
4. processor releases the system bus after seeing the request form DMA, and acknowledges about it to DMA
5. DMA asserts acknowledge signal to peripheral, and starts transfer of data as requested
6. after the completion of transfer, all control lines are deasserted and processor retakes the control of teh system bus.
# 5.3 Arbitration
- mechanism through which a service or shared resource is provided to particular requesting device, out of many contenting devices for service.
## 5.3.A Priority Arbiter
### 3.A.i Introduction
- single purpose processor which is used to arbitrate among various requests from peripherals.
- each of the peripherals, which are connected to the arbiter can make request for the service
- using certain priority mechanism, arbiter selects a peripheral to permit the required service.
- the main advantage of this arbitration is that it can support advanced priority schemes.
- also failure of a single peripheral does nt have any impact on the operation of whole system.
- the system must be redesigned if new peripherals are to be added.
- so this method is less flexible if new perpherasls are required to be added or removed.
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
- REQ_IN = 1, but REQ = 0, resulting in REQ_OUT = 1
- ACK_IN = 1 and REQ = 0, resulting in ACK_OUT = 1
Case 3: When request is from P
- REQ = 1, REQ_IN = X (don't care), resulting in REQ_OUT = 1
- ACK_IN = 1, and REQ = 1 resulting in ACK = 1 and ACK_OUT = 0
## 5.3.C Network-Oriented Arbitration
- arbitration is done for multiple microprocessors sharing a common to form a network.
- arbitration is build into the bus protocol, as bus is the only the medium that connects multiple processors
- however, multiple processors may try to access the bus simultaneously resulting in data collision.
- the protocol must be designed in such a way that the contending processors don't start sending the data at the same time.
- also some statistical methods can be used so as to make chances of data collision very rare, if not eliminate it.
- some protocols use efficient address encoding schemes in which higher prioritiy address will override the lower-priority one.
# 5.4 Multilevel Bus Architectures
# 5.5 Advanced Communication Principles
# 5.6 Serial, Parallel and Wireless Protocols.
