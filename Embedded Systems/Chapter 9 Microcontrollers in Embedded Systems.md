- **3 Hours**
- **8 Marks**
# 1 Intel 8051 Microcontroller Family
## 1.1 Introduction
- A microcontroller is a small computer on a single IC containing
	- processor core
	- memory (RAM and ROM)
	- I/O ports
	- Peripheral devices (timers, ADC, Serial communication, etc.)
- used in embedded applications for control-oriented tasks
## 1.2 Microprocessor vs Microcontroller
|SN|Microprocessor|Microcontroller|
|---|---|---|
|1|General purpose processor|Special purpose processor|
|2|Contains CPU only|CPU + Timers, I/O ports, internal RAM/ROM|
|3|Designer selects memory size, I/O ports, timers|Fixed memory size, I/O ports, timers for a given microcontroller|
|4|Clock speed: GHz range|Clock speed: MHz range|
|5|Powerful addressing modes; many instructions for memory-CPU data movement|Focuses on bit handling + byte processing|
|6|Access time for external memory/I/O is more|Access time for on-chip memory/I/O is less|
|7|Expensive, consumes more power|Cheap, consumes less power|
## 1.3 Criteria for choosing a microcontrolelr
- Must meet computational needs efficiently and cost effectively
- speed, packaging (DIP, QFP), power consumption
- Amount of RAM/ROM, I/O pins, timers
- Ease of amendments, cost per unit
- Availability of assembler, debugger, C compiler, emulator, technical support
- must be readily available in required quantities
## 1.4 Comparison of 8051 Family members
|Feature|8051|8052|8031|
|---|---|---|---|
|ROM|4K|8K|0K (ROMless)|
|RAM (bytes)|128|256|128|
|Timers|2|3|2|
|I/O Pins|32|32|32|
|Serial Port|1|1|1|
|Interrupt Sources|6|8|6|
8031 is also called ROMLESS 8051 because all features are common except ROM space
## 1.5 Architecture
### 1.5.1 Features of 8051 Architecture
- **8 bit CPU** with **registers A (Accumulator) and B**
	- A: mathematical and data transfer operations
	- B: multiplication and division
- **16-bit PC** and **DPTR**
	- PC: points to next instruction address in ROM
	- DPTR: points to memory address (internal/external code access, external data access)
	- DPTR = DPH (high byte) + DPL (low byte)
- **8-bit PSW**
	- Flags: CY, AC, OV, P
	- register select bits (RS1, RS0): select which register bank (0-3)
	- bits:
		- 7 - CY
		- 6 - AC
		- 5 - user defined flag F0
		- 4 - RS1
		- 3 - RS0
		- 2 - OV
		- 1 - P
		- 0 - reserved / user definable bit
- **8-bit Stack Pointer (SP)**: points to stack area (LIFO)
- **Internal ROM**: 4KB program memory (look up tables can be stored)
- **Internal RAM: 128 bytes** data memory
	- *Four register banks* (each with R0-R7)
		- Bank 0: 00H - 07H (default)
		- Bank 1: 08H - 0FH
		- Bank 2: 10H - 17H
		- Bank 3: 18H - 1FH
		- Total 32 registers (00H - 1FH)
		- RS1 = 0, RS0 = 1 selects bank 1
	- *16 bytes bit-addressable memory*: 20H-2FH (each bit addressable as 00H - 7FH)
	- *80 bytes general purpose* data memory: 30H - 7FH
- **32 I/O pin**s arranged as four 8-bit ports (bidirectional)
- **two 16-bit timer/counters** (T0 and T1)
	- timer: counts internal clock pulses
	- counter: counts external pusles
	- configured via TMOD register
- **Full duplex serial data receiver/transmitter**
	- SCON register controls communication
	- Pinis: RXD, TXD
	- SBUF holds data
- **Interrupts**:
	- 2 external (INT0, INT1) + 3 internal (timer overflow, RI, TI)
	- IE register selects enabled interrupt
- **Oscillator and clock**
	- AT89S51: 11.0592 MHz, 12 clocks per machine cycle
	- 1 machine cycle = 1.085 us.

- **Bit 0 - -:** Reserved/User Definable Bit. ![Broadwayinfosys](https://encrypted-tbn3.gstatic.com/faviconV2?url=https://ftp.broadwayinfosys.com&client=AIM&size=128&type=FAVICON&fallback_opts=TYPE,SIZE,URL)Broadwayinfosys +3
## 1.6 Pin Description
|Pin(s)|Name|Description|
|---|---|---|
|1-8|**PORT 1**|Bidirectional I/O (internal pull-up, no external resistors needed)|
|9|**RESET**|Must be high for 2 machine cycles to reset registers|
|10-17|**PORT 3**|Bidirectional, multifunctional: RXD, TXD, INT0, INT1, T0, T1, WR, RD|
|18-19|**XTAL**|Connect external crystal for system clock|
|20|**GND**|0V|
|21-28|**PORT 2**|Bidirectional I/O **OR** high-order address byte when accessing external memory|
|29|**PSEN**|Program Store Enable (active low). Connected to OE of external memory.|
|30|**ALE**|Address Latch Enable (active high). Latches lower address from Port 0. Also program pulse input during flash programming.|
|31|**EA**|External Access. GND = fetch code from external memory; VCC = use internal memory.|
|32-39|**PORT 0**|Open drain bidirectional I/O **OR** low-order address/data bus for external memory|
|40|**VCC**|+5V|
### 1.6.1 PORT 3 Alternate Functions
| Pin  | Function | Description                  |
| ---- | -------- | ---------------------------- |
| P3.0 | RXD      | Serial receive               |
| P3.1 | TXD      | Serial transmit              |
| P3.2 | INT0     | External interrupt 0         |
| P3.3 | INT1     | External interrupt 1         |
| P3.4 | T0       | Timer 0 external input       |
| P3.5 | T1       | Timer 1 external input       |
| P3.6 | WR       | External memory write strobe |
| P3.7 | RD       | External memory read strobe  |
### 1.6.2 PORT 2 Purpose
- General purpose I/O (similar to Port 1)
- **Alternate use**: Provides **high-order address** (A8-A15) when accessing external memory (in conjunction with Port 0)
## 1.7 Addressing Modes in 8051
| Mode                  | Description                                               | Example                        |
| --------------------- | --------------------------------------------------------- | ------------------------------ |
| **Immediate**         | Source operand is constant (preceded by #)                | `MOV A, #25H`                  |
| **Direct**            | Instruction contains actual RAM address                   | `MOV A, 80H`                   |
| **Register Direct**   | Operand is a register holding the data                    | `ADD A, R5`                    |
| **Register Indirect** | Register (R0, R1, DPTR) points to address (preceded by @) | `MOV A, @R0`                   |
| **Relative**          | Offset added to PC (used in jump instructions)            | `JC rel`                       |
| **Absolute**          | 11-bit or 16-bit address in instruction                   | `ACALL addr11`, `LCALL addr16` |
| **Indexed**           | Base + index (A + DPTR or A + PC)                         | `MOVC A, @A+DPTR`              |
## 1.8 Port based vs Bus based I/O
| Feature         | Port Based I/O                                            | Bus Based I/O                                             |
| --------------- | --------------------------------------------------------- | --------------------------------------------------------- |
| **Used in**     | Microcontrollers (8051)                                   | Microprocessors (8085, 8086)                              |
| **Addressing**  | I/O ports are memory-mapped or have separate instructions | Separate I/O address space (IN/OUT instructions)          |
| **Hardware**    | Dedicated I/O pins (Ports 0,1,2,3)                        | Shared address/data bus with separate I/O control signals |
| **Decoding**    | Minimal or no external decoding                           | Requires external address decoding                        |
| **Flexibility** | Fixed number of I/O pins                                  | Expandable via bus interface                              |
| **Speed**       | Faster (dedicated pins)                                   | Slower (bus arbitration, sharing)                         |
## 1.9 Timer/Counter Operation (Basic)
Two 16-bit timers/counters: **T0** and **T1**
#### 1.9.1.1 TMOD Register (Timer Mode Control) - Address 89H
| Bit | D7            | D6  | D5  | D4  | D3            | D2  | D1  | D0  |
| --- | ------------- | --- | --- | --- | ------------- | --- | --- | --- |
|     | GATE          | C/T | M1  | M0  | GATE          | C/T | M1  | M0  |
|     | **Timer 1** → |     |     |     | **Timer 0** → |     |     |     |
- **GATE**: 1 = enables external control (INT0/INT1 pin)
- **C/T**: 1 = Counter (external pulses), 0 = Timer (internal clock)
- **M1, M0**: Mode selection

| M1  | M0  | Mode | Description                                                   |
| --- | --- | ---- | ------------------------------------------------------------- |
| 0   | 0   | 0    | 13-bit timer (TH + TL lower 5 bits)                           |
| 0   | 1   | 1    | 16-bit timer                                                  |
| 1   | 0   | 2    | 8-bit auto-reload (TH holds reload value)                     |
| 1   | 1   | 3    | Split mode (Timer 0 only: TL0 & TH0 as separate 8-bit timers) |
#### 1.9.1.2 TCON Register (Timer Control) - Address 88H (bit-addressable)
| Bit | Symbol | Description                                        |
| --- | ------ | -------------------------------------------------- |
| D7  | TF1    | Timer 1 overflow flag                              |
| D6  | TR1    | Timer 1 run control (1 = start)                    |
| D5  | TF0    | Timer 0 overflow flag                              |
| D4  | TR0    | Timer 0 run control (1 = start)                    |
| D3  | IE1    | External interrupt 1 edge flag                     |
| D2  | IT1    | Interrupt 1 type (1 = falling edge, 0 = low level) |
| D1  | IE0    | External interrupt 0 edge flag                     |
| D0  | IT0    | Interrupt 0 type (1 = falling edge, 0 = low level) |
