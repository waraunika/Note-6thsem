- **4 Hours**
- **8 Marks**
# 1 Introduction
- VHDL stands for VHSIC HDL
	- Very high speed integrated circuits
	- Hardware description language
## 1.1 Purpose
- Model and synthesize digital circuits
- simulation  and testing of design
- create digital integrated circuits
- implement circuits in programmable devices or forward for fabrication
## 1.2 VHDL rules
- not case-sensitive
- not sensitive to white space
- comments begin with `--`
- parentheses usages is optional in many cases
- every statement terminated with semicolon
- statements are inherently concurrent; only statements inside a `PROCESS`, `Function`, or `PROCEDURE` execute sequentially
# 2 VHDL Code structure
## 2.1 Fundamental Sections
| Section                 | Purpose                                                 |
| ----------------------- | ------------------------------------------------------- |
| **LIBRARY Declaration** | Collection of pre-defined, reusable code                |
| **ENTITY**              | Specifies I/O connections (interface)                   |
| **ARCHITECTURE**        | Describes how the circuit functions (internal behavior) |
libraries STD and WORK are visible by default, no need to declare
## 2.2 Entity Declaration
Syntax
```vhdl
ENTITY entity_name IS
    PORT (
        port_name : signal_mode signal_type;
        port_name : signal_mode signal_type
    );
END entity_name;
```
## 2.3 Signal Modes (Direction)
|Mode|Direction|Description|
|---|---|---|
|`IN`|Input only|Unidirectional, read-only|
|`OUT`|Output only|Unidirectional, write-only|
|`INOUT`|Bidirectional|Can be read or written|
|`BUFFER`|Internal feedback|Output that can be read internally|
## 2.4 Signal Types
- `BIT`, `BIT_VECTOR`
- `STD_LOGIC`, `STD_LOGIC_VECTOR`
- `INTEGER`, `NATURAL`, `REAL`
- User-defined types
## 2.5 Entity Examples
### 2.5.1 AND Gate
```vhdl
ENTITY AND_GATE IS
    PORT (
        IN_A : IN STD_LOGIC;
        IN_B : IN STD_LOGIC;
        OUT_Z : OUT STD_LOGIC
    );
END AND_GATE;
```
### 2.5.2 4x1 MUX (3 bit inputs)
```vhdl
ENTITY MUX IS
    PORT (
        A, B, C, D : IN STD_LOGIC_VECTOR(2 DOWNTO 0);
        SEL : IN STD_LOGIC_VECTOR(1 DOWNTO 0);
        Y : OUT STD_LOGIC_VECTOR(2 DOWNTO 0)
    );
END MUX;
```
## 2.6 Architecture Declaration
Syntax
```vhdl
ARCHITECTURE architecture_name OF entity_name IS
    -- Declarations (signals, components, constants, types)
BEGIN
    -- Concurrent statements
END architecture_name;
```
## 2.7 COMPONENT Declaration
- Definition:
	- declares a reusable module that can be instantiated multiple times
- similar to ENTITY declaration but uses the `COMPONENT` keyword.
- Syntax:
```vhdl
COMPONENT component_name
    PORT (
        port_name : signal_mode signal_type;
        ...
    );
END COMPONENT;
```
- Placement: in the declarative part of ARCHITECTURE, between IS and BEGIN
- Example:
```vhdl
COMPONENT and_gate
    PORT (
        X : IN STD_LOGIC;
        Y : IN STD_LOGIC;
        W : OUT STD_LOGIC
    );
END COMPONENT;
```
- instantiation:
```vhdl
instance_name: component_name PORT MAP (port_map_list);
```
# 3 Three Architecture Models
|Model|Description|Execution|Best For|
|---|---|---|---|
|**Dataflow**|Concurrent data flow representation using signal assignments|Concurrent|Small/primitive circuits|
|**Behavioral**|Describes **how** circuit behaves (inputs → outputs) using PROCESS|Sequential (inside PROCESS)|Complex designs, FSMs|
|**Structural**|Modular, hierarchical; connects components like building blocks|Concurrent (component instances)|Large, reusable designs|
## 3.1 Dataflow
### 3.1.1 Definition
- Specifies a circuit as a concurrent representation of data flow through the circuit
- internal working implemented using concurrent statements (no PROCESS)
### 3.1.2 Characteristics
- Expression evaluated whenever RHS signal changes
- Good for small/primitive circuits
- Not suitable for complex designs
### 3.1.3 Example: HA
```vhdl
ARCHITECTURE half_adder_arch OF half_adder IS
BEGIN
    S <= A XOR B;    -- concurrent
    C <= A AND B;    -- concurrent
END half_adder_arch;
```
## 3.2 Behavioral Model
### 3.2.1 Definition
- Models how the circuit outputs behave in response to inputs
- May not reflect actual synthesized circuit implementation
- uses sequential statements inside a `PROCESS`
### 3.2.2 Charateristics
- `PROCESS` statement is core
- Statements execute sequentially
- More abstract than dataflow
- Suitable for FSMs, counters, complex logic
### 3.2.3 Example: HA
```vhdl
ARCHITECTURE half_adder_arch OF half_adder IS
BEGIN
    PROCESS_ADDER: PROCESS (A, B)    -- sensitivity list
    BEGIN
        S <= A XOR B;
        C <= A AND B;
    END PROCESS PROCESS_ADDER;
END half_adder_arch;
```
## 3.3 Behavioral vs Dataflow
|Aspect|Behavioral|Dataflow|
|---|---|---|
|**Execution**|Sequential (inside PROCESS)|Concurrent|
|**Level of abstraction**|Higher (algorithmic)|Lower (logic equations)|
|**PROCESS required**|Yes|No|
|**Synthesis mapping**|Less direct (may infer different hardware)|Direct (each assignment = gate)|
|**Best for**|FSMs, counters, complex sequential logic|Combinational logic, small circuits|
## 3.4 Structural Model
### 3.4.1 Definition
- Modular, hierarchical approach that connects lower-level components (like building blocks) to form a system.
- supports design re use.
### 3.4.2 Characteristics
- Components declared then instantiated
- Port mapping connects signals to component ports
- Essential for complex digital designs
- May not be efficient for simple designs
### 3.4.3 Steps
1. Define `ENTITY` and `ARCHITECTURE` for individual gates/modules
2. Declare `COMPONENT`'s (similar to `ENTITY` but with `COMPONENT` keyword)
3. Declare internal signals (interconnects)
4. Instantiate components with `PORT MAP`
### 3.4.4 Example: Z = (A * B) + (C * D)
```vhdl
ARCHITECTURE test_arch OF test IS
    COMPONENT and_gate
        PORT (
	        X, Y: IN STD_LOGIC;
	        W: OUT STD_LOGIC
	      );
    END COMPONENT;
    
    COMPONENT or_gate
        PORT (
	        X, Y: IN STD_LOGIC;
	        W: OUT STD_LOGIC
				);
    END COMPONENT;
    
    SIGNAL E, F: STD_LOGIC;
BEGIN
    U1: and_gate PORT MAP (X => A, Y => B, W => E);
    U2: and_gate PORT MAP (X => C, Y => D, W => F);
    U3: or_gate  PORT MAP (X => E, Y => F, W => Z);
END test_arch;
```