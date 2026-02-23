- **3 Hours**
- **4 Marks**
# 1.1 Embedded Systems Overview
## 1.1.A Introduction
- Embedded System (**E.S.**) is a combination of computer hardware and software and may have additional mechanical or other parts designed to perform a specific function.
- is a kind of computer system that performs a dedicated function and/or is intended for use with a specific embedded software application. Embedded systems are devices which are used to control monitor or assist the operation of an equipment, machinery or plant.
- may be defined as a computer system designed for specific control functions within a larger system, often with real time computing constraints.
- It may be embedded as a part of a complete device often including hardware and mechanical parts.
## 1.1.B Characteristics
### 1.B.i Single Functioned
- as ES are designed for specific control functions, it usually executes a specific program to carry out specific function repeatedly.
- In some cases, exceptions may occur but in general, all embedded systems are supposed to carry out single specified function.
- One case is where an embedded system program is updated with a newer version.
- A second case is when several programs are swapped in and out of a system due to some constraint
### 1.B.ii Tightly Constrained
- Feasibility and utility of the embedded system are measured in terms of cost, size, performance, power and other parameters.
- These all parameters are referred as design metric.
- All computing systems are constraint with design metric but it is more tightly constraint in embedded systems.
- Embedded systems in general must be economic, small possible size, fast enough to process data in real time and must consume minimum power to extend battery life or prevent the necessity of a cooling fan.
### 1.B.iii Reactive and Real Time
- in general embedded systems must continually react to changes in the system's environment and must compute certain results in real time without delay.
- A delay in computation and slow response may result in a failure in the operation of the system.
## 1.1.C Components
- An embedded system has mainly three components hardware, application software and real time operating system (small scale embedded system may not require RTOS).
### 1.C.i Hardware
- It represents the physical component
	- which interacts with each other to perform the specific task.
- Processor, RAM, ROM, ADC, DAC, Timers, Ports etc. are some of the hardware components of the embedded system.
### 1.C.i Application Software
- The application software may perform concurrently the series of tasks or multiple tasks.
- Generally they are written in Assembly, C, C++, Java, etc.
### 1.C.i RTOS
- It supervises the application software and provides a mechanism to let the processor run a process as per scheduling and do the context-switch between various tasks.
- RTOS defines the way the system works and sets the rules during the execution of the application software.
- Win CE, VxWorks, Embedded Linux, etc.
## 1.1.D Design Metrics
- A design metric is a measurable feature of a system's implementation.
- Some of the commonly used metrics include:
	- NRE cost
		- non-recurring engineering cost
		- represents the monetary cost for designing the system.
		- large number of units can be produced without any additional design cost.
		- Since cost doesn't occur more than once for a particular system, it is termed as non-recurring.
	- Unit Cost:
		- monetary cost of manufacturing each unit of the system excluding NRE cost
	- Size:
		- physical space required by the system.
		- for software it is measured in terms of bytes and for hardware it is measured in terms of no. of gates or transistors.
	- Performance:
		- it represents the execution of the system
	- Power:
		- The amount of power consumed by the system
		- may determine the lifetime of a battery
		- or cooling requirements of the IC
	- Flexibility:;
		- ability to change the functionality of the system without incurring heavy NRE cost.
	- Time to Prototype:
		- the time needed to build a working version of the system, which may be bigger or more expensive than the final system implementation.
		- can be used to verify the system's usefulness and correctness and to refine the system's functionality.
	- Time to Market:
		- time required to develop a system to the point that it can be released and sold to customers.
	- Maintainability:
		- the ability to modify the system after its initial release
	- Correctness:
		- we can check the functionality throughout the process of designing the system and we can insert test circuitry to check that manufacturing was correct.
	- Safety:
		- the system is supposed to cause no harm.
### # The Time to Market Design Metric
- Introduction of an embedded system to the marketplace significantly affects the overall system profitability.
- the market window, period during which the product have highest sales, for products is getting shorter, so a short delay on introduction of product to the marketplace can render huge loss.
- using a simplified model of revenue, we will deduce the loss of revenue that can occur due to the delayed entry of a product in the market.
- ![[Pasted image 20260222110557.png]]
- This model assumes the peak of the market occurs at the halfway point, denoted as W, of the product life.
- the peak is same for delayed entry.
- the revenue for an on-time market entry is the area of the triangle labeled On-time, and for delayed entry is the area of triangle labeled *Delayed*.
- The difference between the areas of two triangles gives the revenue loss for a delayed entry.
- Revenue Loss = ((On time - Delayed) / On Time) * 100
- Area of On Time Triangle = $1/2$ * base * height
	- = $1/2$ * 2 * W * W * tan($\beta$) (Assuming, market rise angle is $\beta$)
	- W$^2$ tan($\beta$)
- Area of delayed entry triangle = $\frac{1}{2} \cdot (2W - D) \cdot (W - D) \cdot \tan(\alpha)$
- Assuming $\beta$ = $\alpha$ and on solving we get,
	- Revenue Loss = $\left(\dfrac{D(3W - D)}{2W^2}\right) \cdot 100\%$
### # The NRE and Unit Cost Design Metrics
- The NRE cost is the one time monetary cost of designing the system, whereas the unit cost represents the monetary cost of manufacturing each copy of the system, excluding NRE cost.
	- Total Cost = NRE cost + unit cost * # of units
	- Per-product Cost = total cost / # of units
		- NRE cost / # of units + unit cost
- the larger the volume the per-product cost, since the NRE cost can be distributed over more products.
- The per-product cost of the product approaches the unit cost for very large volume.

### # Example
- let us consider products using three different technologies
- Technology A with NRE cost of $2000 and unit cost of $100, B with NRE cost of $30,000 and unit cost $30, and C with NRE cost of $100000 and unit cost $2
- A and B meet at 300 units which implies A yields lowest total cost for low volumes (< 300) units.
- B yields lowest total cost for volume between 300 and 1800, since the line of technology B and C meet at 1800.
- furthermore, tech C yields lowest cost for volumes above 1800.
### # Performance Design Metric
- Performance is a measure of duration the system takes to execute our desired tasks.
- Though the performance of a system is governed by clock frequency or instructions per second.
- main measures of performance are:
	- Latency or response time: the time between the start of the task's execution and the end.
	- throughput: the number of tasks that can be processed per unit time.
	- Speedup: common method of comparing the performance of two systems.
		- the speedup system A over system B is determined by:
		- speedup of A over B = performed of A/performance of B
### # Example of an embedded system - a digital camera
- A digital camera can be taken as embedded system as it performs only a single function of capturing image.
- it is tightly constrained as it is affordable, portable, and consumes less power.
- as it is fast enough to process numeral images in milliseconds, it exhibits real time feature.
- but however, a simple digital camera may not possess high degree of reactive attribute.
- on the contrary, few contemporary digital cameras are capable of detecting human expressions.
# 1.2 Classification of Embedded Systems
## 1.2.A Classification based on Generation
### 2.A.i First Generation
- designed using 8 bit microprocessors or 4 bit microcontrollers.
- hardware circuits were simple and the firmware was developed using assembly code.
- motor controller using 8085 can be an example of first generation embedded system.
### 2.A.ii Second Generation
- systems were built using 16 bit microprocessors and 8/16 bit microcontrollers.
- more complex and powerful instructions were available for the designer to work with.
- some systems involved embedded operating systems for their operation.
- data acquisition systems can be an example of second generation.
### 2.A.iii Third generation
- system were designed with more advanced processor technology in the form of 32 bit processors and 16 bit microcontrollers.
- along with complex and powerful instruction sets, instruction pipelining was introduced
- better performance
- dedicated embedded real time operating system implementation was another important feature in this generation.
- also the concept of application specific processors like DSP and ASIC came into existence
### 2.A.iv Fourth Generation
- marked with advent of SoC, reconfigurable processors and multicore processors.
- These embedded systems used high performance real time embedded operating systems for its operation.
## 1.2.B Classification Based on Complexity and Performance
### 2.B.i Small Scale ES
- designed with a single 8 or 16 bit microcontroller (8051 family, PIC16F8X, Hitachi H8)
- they have little hardware and software complexities and involve board level design.
- may be battery operated.
- while developing embedded software for these system, an editor, assembler and cross assembler specific to the microcontroller or processor are used as the main programming tool.
- Usually C language is used for developing these systems.
- to develop such systems, the size requirement of the software must not exceed the available memory while the hardware design must be done in such a way that power dissipation must be limited when the system is running continuously.
- Automatic vending machine, stepper motor controller for a robotics system etc can be the examples of small scale embedded systems.
### 2.B.ii Medium Scale Embedded Systems
- designed with a single or few 16 or 32 microcontrollers (8051MX, PIC16F876) or DSPs or RISC.
- It may also employ the readily available single purpose processors and IPs for various functions.
- For example:
	- bus interfacing, encryption, deciphering and so on.
- these systems have both hardware and software complexities.
- For software design, the programming tools used is RTOS, Source code engineering tool, Simulator, Debugger and IDE.
- Software tools also provide the solutions to the hardware complexities.
- Some of the examples of medium scale embedded systems are Computer networking systems, signal tracking system, etc.
### 2.B.iii Sophisticated Embedded Systems or Large Scale Embedded Systems
- these systems have enormous hardware and software complexities and may need scalable processors or configurable processors and programmable logic arrays.
- they are used for cutting edge applications that need hardware and software co-design and integration in the final system.
- They are constrained by the processing speeds available in their hardware units.
- Certain software functions are implemented in the hardware to obtain additional speed by saving time.
- Some of the functions of the hardware resources in the system are also implemented by the Software.
- These systems general implement high performance real operating system
- Development tools for these systems may not readily be available at a reasonable cost or may not be available at all.
- in some cases, a compiler or retargetable compiler might have to be developed for these.
- A retargetable compiler is one that configures according to the given target configuration in a system.
- Embedded system for wireless LAN & for convergent technology devices is one of the sophisticated embedded systems.
# 1.3 Hardware and Software in a System
- hardware of the system represents the single purpose processor whereas the software represents the general purpose Processor.
## 1.3.A Single Purpose Processor
- digital circuit designed to execute to exactly one program.
- does not require a program memory since the program to run on the processor is fixed (only one) and it can be built into the digital circuit.
- the datapath contains only the essential components for the specified task.
- JPEG codec, Display controller, DMA controller etc can be taken as the examples of single purpose processor.
- Design metric of the single purpose processor
	- Performance may be fast, size and power may be small
	- Unit cost may be low for large quantities
- Design metric drawback of single purpose processor
	- design time and NRE cost may be high, flexibility low, unit cost for small quantities
	- performance may not match general purpose processors for some applications.
- Figure of block diagram of single purpose processor
	-   ![[Pasted image 20260223104613.png]]
### 1.3.B General Purpose Processor
- the required functionality is carried out by programming the processor's memory.
- in this context, a programmable device is built that is suitable for a variety of applications.
- Microprocessors are the examples of general purpose processor.
- Such processors include:
	- Program memory: the program cannot be built into the digital circuit in general purpose processors since the program likely to run on the processor will be unknown.
	- General Datapath: The datapath must be general enough to handle a variety of computations, so such datapath typically has a large register file and one or more general purpose ALUs
- Design metric benefits of general purpose processor
	- Time to market and NRE costs are  low because designer must only write a program but does not have to deal with any digital design.
	- flexibility is high because changing functionality requires changing only the program
	- unit cost may be low in small quantities
	- performance may be fast for computation intensive applications.
- Design metric demerits of GPP
	- unit cost may be relatively high for large quantities, since in large quantities we could design our own processor and amortize NRE costs
	- size and power may be large due to unnecessary processor hardware
	- performance may be slow for certain applications.
### 1.3.C Application Specific Processor
- programmable processors optimized for a particular class of applications.
- generally includes program memory, optimized datapath and special functional units
- provide optimum level of performance maintaining appropriate size and power consumption.
- microcontrollers for controlling application and digital signal processors (DSP) for huge data processing application are examples of application specific processors.
- Block diagram of Application Specific Processors
	- ![[Pasted image 20260223192838.png]]
# 1.4 Purpose and Application of Embedded Systems
## 1.4.A Purpose
### 4.A.i Data Collection
- data is collected from other external devices for storage, analysis, manipulation or transmission.
- data may be in analog or digital form.
- systems working with digital data require analog to digital converters if the collected data is in analog form.
- the collected data can be used for meaningful purpose based on the functionality of the embedded system.
- for instance, a digital camera collects data, stores it and finally procides graphical representation of data in the form of captured image.
### 4.A.ii Data Communication
- ES is requierd to connect 2 or more devices which may be at close vicinity or at remote location.
- the communication between devices can be done via wired line medium or wireless emdium.
- ES are incorporated with different wireless module or wire-line modules for communication purpose.
- Bluetooth, ZigBee, Wi-Fi and GSM are few wireless modules.
- for wire-line purpose, an embedded system may have RS-232, SPI, I2C, USB and other serial and parallel protocols.
- some embedded systems like network hubs, routers, etc. act as mediators in data communication and provide various features including data security.
### 4.A.iii Data Processing
- collected data in embedded system is subjected to some sort of processing for which embedded systems are attributed with data processing modules.
- speech coder, audio video codec, etc. can be few examples of data processing unit.
- data processing includes the manipulation of data for appropriate purpose.
### 4.A.iv Monitoring
- ES are incorporated with sensors to check the state of the different parameters.
- parameters can be current, voltage, temperature, humidity, etc which are continuously monitored and appropriate processing or controlling of devices is done.
- however, the value of the parameters cannot be controlled by the system itself.
- the values of parameters are used for some controlling purpose or for some graphical representation purpose or simply stored for further analysis and processing.
### 4.A.v Control
- for control purpose, actuators along with sensors are present in the embedded systems.
- the sensor connected in input port detects the change in the desired parameter and the actuators at output port are controlled accordingly to implement the desired functionality.
- electric motors are example of actuators.
- in an object avoiding robot, ultrasonic sensor senses the presence of certain kind of object and the motor is rotated accordingly to avoid the collision.
### 4.A.vi Application specific user interface
- to provide the better use interface based on application has been one of the concerns of contemporary embedded systems. Keypads, simple LCD modules, speakers, etc are basic and common interface for users. 
- however, sensitive touch pad along with high definition display has been the sophisticated interface implemented in current scenario.
## 4.B Application
1. Household appliances: 
	- Microwave ovens, television, DVD players and recorders.
2. Office automation
	- fax machines, printers, scanners
3. business equipment
	- alarm systems, card readers
4. automobiles
	- engine controller, fuel injection, antilock brakes
5. networking
	- modem, network cards, network switches and routers
6. medical equipment
7. aerospace equipment
8. integrated systems in aircraft and missiles
9. industrial and military applications