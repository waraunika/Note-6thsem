- **3 Hours**
- **4 Marks**

# 1 Embedded Systems Overview
## 1.1 Introduction
- Embedded System (**E.S.**) is a combination of computer hardware and software and may have additional mechanical or other parts designed to perform a specific function.
- is a kind of computer system that performs a dedicated function and/or is intended for use with a specific embedded software application. Embedded systems are devices which are used to control monitor or assist the operation of an equipment, machinery or plant.
- may be defined as a computer system designed for specific control functions within a larger system, often with real time computing constraints.
- It may be embedded as a part of a complete device often including hardware and mechanical parts.
## 1.2 Characteristics
### 1.2.1 Single Functioned
- as ES are designed for specific control functions, it usually executes a specific program to carry out specific function repeatedly.
- In some cases, exceptions may occur but in general, all embedded systems are supposed to carry out single specified function.
- One case is where an embedded system program is updated with a newer version.
- A second case is when several programs are swapped in and out of a system due to some constraint
### 1.2.2 Tightly Constrained
- Feasibility and utility of the embedded system are measured in terms of cost, size, performance, power and other parameters.
- These all parameters are referred as design metric.
- All computing systems are constraint with design metric but it is more tightly constraint in embedded systems.
- Embedded systems in general must be economic, small possible size, fast enough to process data in real time and must consume minimum power to extend battery life or prevent the necessity of a cooling fan.
### 1.2.3 Reactive and Real Time
- in general embedded systems must continually react to changes in the system's environment and must compute certain results in real time without delay.
- A delay in computation and slow response may result in a failure in the operation of the system.
## 1.3 Components
- An embedded system has mainly three components hardware, application software and real time operating system (small scale embedded system may not require RTOS).
### 1.3.1 Hardware
- It represents the physical component
	- which interacts with each other to perform the specific task.
- Processor, RAM, ROM, ADC, DAC, Timers, Ports etc. are some of the hardware components of the embedded system.
### 1.3.2 Application Software
- The application software may perform concurrently the series of tasks or multiple tasks.
- Generally they are written in Assembly, C, C++, Java, etc.
### 1.3.3 RTOS
- It supervises the application software and provides a mechanism to let the processor run a process as per scheduling and do the context-switch between various tasks.
- RTOS defines the way the system works and sets the rules during the execution of the application software.
- Win CE, VxWorks, Embedded Linux, etc.
## 1.4 Design Metrics
- a measurable feature used to evaluate and compare the quality or characteristics of a system's implementation.
- these metrics allow designers to make informed decisions by quantifying aspects like cost, performance, and physical size.
### 1.4.1 Key Design Metrics in Embedded Systems
| SN  | Name                                    | Definition                                                                                                                                         | Key-Point                                                                                                                                                                                                                                                                                        |
| --- | --------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 1   | Non-Recurring Engineering<br>(NRE) Cost | The one-time monetary cost spent on designing the system.                                                                                          | - This cost is incurred only once per design.<br>- Once the system is designed, any number of units can be produced without incurring this cost again.<br>- It includes expenses like salaries of the design team, software licenses, and prototyping.                                           |
| 2   | Unit Cost                               | The monetary cost of manufacturing each individual copy (or unit) of the system.                                                                   | - This cost excludes the NRE cost.<br>- It includes the cost of components, the manufacturing process, and packaging.<br>- For high-volume products, a small reduction in unit cost leads to massive savings.                                                                                    |
| 3   | Size                                    | The physical space required by the system.                                                                                                         | - software: size is measured in bytes (memory footprint).<br>- hardware: it is measured by the number of gates or transistors on a chip.<br>- Smaller size often leads to lower cost and lower power consumption.                                                                                |
| 4   | Performance                             | A measure of how quickly and efficiently the system executes its designated tasks.                                                                 | - Latency: The time between the start of a task and its completion.<br>- Throughput: The number of tasks the system can process within a given unit of time (e.g., tasks per second).<br>- Speedup: A way to compare two systems. It is calculated as `Performance of A / Performance of B`.<br> |
| 5   | Power                                   | The amount of electrical power consumed by the system.                                                                                             | - High power consumption can shorten the lifetime of a battery in portable devices<br>- or increase the cooling requirements for integrated circuits (ICs).                                                                                                                                      |
| 6   | Flexibility                             | The ability to change the system's functionality after it has been designed.                                                                       | - flexible system can be updated or adapted for new uses without incurring a heavy NRE cost.<br>- This is often a key advantage of software-based solutions over fixed hardware.                                                                                                                 |
| 7   | Time to Prototype                       | The time needed to build a working version of the system (the prototype).                                                                          | - the prototype is used to verify the system's functionality and correctness with real users<br>- used to refine the design before mass production.                                                                                                                                              |
| 8   | Time to Market                          | The total time required to develop a system from the initial concept to the point where it can be released and sold to customers.                  | - critical business metric<br>- Being late to market can drastically reduce profits, even if the product is technically superior.                                                                                                                                                                |
| 9   | Maintainability                         | The ease with which the system can be modified to fix bugs, <br>improve performance, or adapt to a changing environment after its initial release. |                                                                                                                                                                                                                                                                                                  |
| 10  | Correctness                             | Confidence that the system functions as intended.                                                                                                  | achieved through continuous verification during the design process and by inserting test circuitry to ensure the manufacturing process was error-free.                                                                                                                                           |
| 11  | Safety                                  | The assurance that the system will operate without causing harm to people, property, or the environment.                                           |                                                                                                                                                                                                                                                                                                  |
### 1.4.2 The Impact of Time to Market
- Introducing a product late can severely impact its profitability.
- The "market window"
	- the period of highest sales
	- is getting shorter for most products.
- Using a simplified revenue model (the "triangular" market window):
	- **On-time entry** captures the full peak of the market.
	- **Delayed entry** misses the peak, resulting in significantly less total revenue.
- The revenue loss from a delay of **D** weeks in a market window of width **2W** weeks can be estimated by the formula:
	- **Revenue Loss** = $$ \left( \dfrac{D(3W-D)}{2W^{2}} \right) \star 100\%$$
	- This shows that even a short delay can result in a substantial percentage of revenue loss.
### 1.4.3 Relationship Betn NRE Cost & Unit Cost
- The total cost of producing a system is a combination of its one-time NRE cost and its per-unit manufacturing cost.
	- **Total Cost = NRE Cost + (Unit Cost * Number of Units)**
	- **Per-Product Cost = (NRE Cost / Number of Units) + Unit Cost**
	- **The key takeaway is the effect of volume (number of units produced):**
	- For **low volumes**, the NRE cost dominates, making the per-product cost high.
    - For **high volumes**, the NRE cost is spread over many units, and the per-product cost approaches the unit cost.
- This is why different technologies are chosen for different production volumes:
	- **Low Volume:** A technology with low NRE cost might be best, even if its unit cost is higher (e.g., Technology A).
    - **High Volume:** A technology with a high NRE cost can be justified if it has a very low unit cost, as the NRE cost is amortized over millions of units (e.g., Technology C).
### 1.4.4 Example: The Digital Camera
A digital camera serves as a classic example of an embedded system:
- **Single Function:** Its primary purpose is to capture and store images.
- **Tightly Constrained:** It must be affordable (**cost**), portable (**size**), and run on batteries (**power**).
- **Real-Time Behavior:** It must process images quickly enough (**performance**) to be usable.
- **Reactive Nature:** More advanced cameras can react to the environment by detecting faces or smiles (**reactive/flexibility**).
---
# 2 Classification of Embedded Systems
## 2.1 Classification based on Generation
| Generation            | Time Period (Approx.) | Key Concept                  | Feature 1                                                                                                       | Feature 2                                                             | Example                                                                                | Other Key Points-1                                                                                                                   | Other Key Points-2                                                                                                                        |
| --------------------- | --------------------- | ---------------------------- | --------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------- | -------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------- |
| **First Generation**  | Early 1980s           | 8-bit Era                    | Built using **8-bit microprocessors** (e.g., Intel 8085) or **4-bit microcontrollers**.                         | Hardware circuits were simple.                                        | Firmware (software) was developed using **assembly code**.                             | Motor controller using the 8085 processor.                                                                                           | Marked the beginning of using microprocessors for dedicated control tasks.                                                                |
| **Second Generation** | Mid 1980s - 1990s     | 16-bit & OS Introduction     | Built using **16-bit microprocessors** and **8/16-bit microcontrollers**.                                       | More complex and powerful instruction sets were available.            | Some systems began to incorporate **embedded operating systems**.                      | Data acquisition systems.                                                                                                            | The move to 16-bit allowed for more complex applications and the need for basic OS management.                                            |
| **Third Generation**  | 1990s - 2000s         | High Performance & Real-Time | Built using **32-bit processors** and **16-bit microcontrollers**.                                              | Introduction of **instruction pipelining** for better performance.    | Implementation of dedicated **embedded Real-Time Operating Systems (RTOS)** .          | Application Specific Processors like **Digital Signal Processors (DSPs)** and **Application-Specific Integrated Circuits (ASICs)** . | The focus shifted to high performance and guaranteed response times for complex tasks like signal processing.                             |
| **Fourth Generation** | 2000s - Present       | Integration & Parallelism    | Marked by the advent of **System-on-Chip (SoC)** , **reconfigurable processors**, and **multicore processors**. | High level of integration, placing an entire system on a single chip. | Use of high-performance real-time embedded operating systems to manage multiple cores. | Smartphones, modern network routers, and advanced automotive systems.                                                                | This generation is defined by the ability to build incredibly complex and powerful systems that are small, efficient, and reconfigurable. |
## 2.2 Classification Based on Complexity and Performance
### 2.2.1 Small Scale ES
- designed with a single 8 or 16 bit microcontroller (8051 family, PIC16F8X, Hitachi H8)
- they have little hardware and software complexities and involve board level design.
- may be battery operated.
- while developing embedded software for these system, an editor, assembler and cross assembler specific to the microcontroller or processor are used as the main programming tool.
- Usually C language is used for developing these systems.
- to develop such systems, the size requirement of the software must not exceed the available memory while the hardware design must be done in such a way that power dissipation must be limited when the system is running continuously.
- Automatic vending machine, stepper motor controller for a robotics system etc can be the examples of small scale embedded systems.
### 2.2.2 Medium Scale Embedded Systems
- designed with a single or few 16 or 32 microcontrollers (8051MX, PIC16F876) or DSPs or RISC.
- It may also employ the readily available single purpose processors and IPs for various functions.
- For example:
	- bus interfacing, encryption, deciphering and so on.
- these systems have both hardware and software complexities.
- For software design, the programming tools used is RTOS, Source code engineering tool, Simulator, Debugger and IDE.
- Software tools also provide the solutions to the hardware complexities.
- Some of the examples of medium scale embedded systems are Computer networking systems, signal tracking system, etc.
### 2.2.3 Sophisticated Embedded Systems or Large Scale Embedded Systems
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
# 3 Hardware and Software in a System
- hardware of the system represents the single purpose processor whereas the software represents the general purpose Processor.
## 3.1 Single Purpose Processor
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
### 3.1.1 General Purpose Processor
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
### 3.1.2 Application Specific Processor
- programmable processors optimized for a particular class of applications.
- generally includes program memory, optimized datapath and special functional units
- provide optimum level of performance maintaining appropriate size and power consumption.
- microcontrollers for controlling application and digital signal processors (DSP) for huge data processing application are examples of application specific processors.
- Block diagram of Application Specific Processors
	- ![[Pasted image 20260223192838.png]]
# 4 Purpose, Features and Application
## 4.1 Purpose of Embedded Systems
### 4.1.1 Data Collection
- **Definition:** The embedded system gathers data from the external environment or other devices for storage, analysis, manipulation, or transmission.
- **Technical Details:**
    - The collected data can be in **analog** or **digital** form.
    - If the data is analog (e.g., a sound wave), the system requires an **Analog-to-Digital Converter (ADC)** to process it digitally.
- **Example:** A **digital camera** collects light data through its sensor, stores it, and then processes it to provide a graphical representation in the form of a captured image.
### 4.1.2 Data Communication
- **Definition:** The system's purpose is to connect two or more devices to exchange data, whether they are in close proximity or at remote locations.
- **Technical Details:**
    - Communication can occur via **wired** or **wireless** mediums.
    - **Wireless Modules:** Bluetooth, ZigBee, Wi-Fi, GSM.
    - **Wire-line Modules/Protocols:** RS-232, SPI, I2C, USB.
- **Example:** A **network router** acts as a mediator in data communication, directing traffic between devices and the internet, and often providing features like data security.
### 4.1.3 Data Processing
- **Definition:** The system takes collected data and subjects it to manipulation or transformation to achieve a desired result.
- **Technical Details:** Embedded systems are equipped with dedicated processing units (like microprocessors, DSPs, or codecs) to perform these tasks.
- **Example:** An **audio codec** in a smartphone processes digital audio data, compressing it for storage or decompressing it for playback through the speakers.
### 4.1.4 Monitoring
- **Definition:** The system uses sensors to continuously check the state of various parameters in the environment.
- **Technical Details:**
    - Parameters can include current, voltage, temperature, humidity, pressure, etc.
    - The system itself typically **does not control** these parameters. It simply observes, records, and may trigger alerts or display the information.
- **Example:** A **digital thermometer** with a sensor monitors the room temperature and displays the value on an LCD screen. It does not change the temperature.
### 4.1.5 Control
- **Definition:** The system actively manages and regulates physical parameters or devices based on input from sensors.    
- **Technical Details:** 
	- This purpose requires both **sensors** (to detect changes) and **actuators** (to cause a physical change). Actuators, such as electric motors, valves, or solenoids, are controlled by the system's output.
- **Example:** In an **object-avoiding robot**, an ultrasonic sensor detects an obstacle. The embedded system processes this input and controls the motors (actuators) to rotate in a different direction, thus avoiding a collision.
### 4.1.6 Application-Specific User Interface
- **Definition:** The system provides a means for the user to interact with the application, tailored to the device's specific function.
- **Technical Details:**
    - **Basic Interfaces:** Keypads, simple LCD modules, LEDs, speakers.
    - **Sophisticated Interfaces:** Sensitive touchpads, high-definition displays, voice recognition modules        
- **Example:** A **modern smart thermostat** uses a sensitive touchscreen and a high-definition display to provide an intuitive interface for the user to set schedules and monitor energy usage, unlike older thermostats with simple buttons and dials.
---
## 4.2 Features of Embedded Systems
1. **Dedicated Functionality:** They are designed to perform a specific set of tasks repeatedly, rather than being a general-purpose machine for multiple applications.
    - _Example:_ A **microwave oven** is dedicated to heating food. You cannot browse the internet on it.
2. **Real-Time Operation:** Many embedded systems must react to events in the environment (inputs from sensors) and produce outputs within a strictly defined time frame. Failure to meet these timing constraints can lead to system failure.
    - _Example:_ An **anti-lock braking system (ABS)** in a car must detect wheel lock and modulate brake pressure within milliseconds. A delay could cause the driver to lose control of the vehicle.
3. **Resource Constraints:** They operate under tight constraints on **processing power, memory, and energy consumption**. This necessitates highly optimized and efficient software (code).
    - _Example:_ A **fitness tracker** has a small battery, limited memory, and a low-power processor to last for days on a single charge, requiring extremely efficient code.
4. **Reliability and Stability:** Embedded systems are often deployed in critical applications where failure is unacceptable. They must operate reliably for long periods without human intervention, often in harsh environments.
    - _Example:_ The **engine control unit (ECU)** in a car must be extremely reliable. A failure while driving could be catastrophic.
5. **Processing Power:** They contain a microcontroller or microprocessor to execute the instructions. The power required depends on the complexity of the task
6. **Efficiency and Performance:** Designers constantly strive to balance performance (how fast tasks are completed) with efficiency (how little power and memory are used).
## 4.3 Applications of Embedded Systems
1. **Household Appliances:** Microwave ovens, televisions, DVD players, smart refrigerators, washing machines.
2. **Office Automation:** Fax machines, printers, scanners, photocopiers.
3. **Business Equipment:** Alarm systems, card readers, point-of-sale (POS) terminals.
4. **Automobiles:** Engine control units (ECU), fuel injection systems, anti-lock braking systems (ABS), airbag control, infotainment systems.
5. **Networking & Communications:** Modems, network interface cards (NICs), network switches, routers, mobile phone base stations.
6. **Medical Equipment:** Patient monitoring systems, pacemakers, infusion pumps, diagnostic imaging (MRI, CT scanners).
7. **Aerospace & Defense:** Navigation systems in aircraft and missiles, flight control systems, avionics.
8. **Industrial and Military Applications:** Robotics, process control systems in factories, surveillance systems, guidance systems.