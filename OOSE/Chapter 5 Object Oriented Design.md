- **8 Hours**

[[Chapter 4 Object Oriented Analysis]]
# 1 Concepts
## 1.1 OOA vs OOD
| Aspect       | Object Oriented Analysis (OOA)                            | Object Oriented Design (OOD)                                          |
| ------------ | --------------------------------------------------------- | --------------------------------------------------------------------- |
| **Focus**    | Finding and describing objects/concepts in problem domain | Defining software objects and their collaborations                    |
| **Question** | _What_ does the system need?                              | _How_ will the system be built?                                       |
| **Example**  | Book, Library, Librarian as concepts                      | Book software object with `title` attribute and `getChapter()` method |
| **Output**   | Conceptual model, requirements                            | Architecture, detailed design                                         |
## 1.2 Characteristics of OOD
| Characteristic              | Description                                                           |
| --------------------------- | --------------------------------------------------------------------- |
| **Objects as Abstractions** | Objects represent real-world or system entities and manage themselves |
| **Encapsulation**           | Objects are independent with encapsulated state and representation    |
| **Service-Oriented**        | System functionality expressed in terms of object services            |
| **Message Passing**         | Communication between objects through messages                        |
| **Distribution**            | Objects may be distributed, execute sequentially or in parallel       |
# 2 Booch method for OOD
## 2.1 Overview
- Authored by **Grady Booch** (1992, revised 1994)
- Widely used OO analysis and design methodology
- **Notation** superseded by UML (combined with OMT and OOSE)
- **Methodology** incorporated into Rational Unified Process (RUP)
## 2.2 Diagrams Used in Booch Method
| Level                    | Diagrams                                                                     |
| ------------------------ | ---------------------------------------------------------------------------- |
| **Design Level**         | Class diagram, Object diagram, State transition diagram, Interaction diagram |
| **Implementation Level** | Module diagram, Process diagram                                              |
## 2.3 Micro Development Process
- **Definition**: Daily activity of individual developer or small team; analysis and design phases intentionally blurred.
- **Steps**:
	1. Identify classes and objects at a given level of abstraction
	2. Identify semantics of these classes and objects
	3. Identify relationships among these classes and objects
	4. Specify interface, then implementation of these classes and objects
## 2.4 Macro Development Process
- **Definition**: Higher-level process focusing on **Risk** and **Architectural vision**.
- **Activity Cycle**:

| Phase                 | Description                       |
| --------------------- | --------------------------------- |
| **Conceptualization** | Establish core requirements       |
| **Analysis**          | Develop model of desired behavior |
| **Design**            | Create an architecture            |
| **Evolution**         | Implementation                    |
| **Maintenance**       | Evolution after delivery          |
## 2.5 Micro vs Macro Process
| Aspect       | Micro Process                         | Macro Process                    |
| ------------ | ------------------------------------- | -------------------------------- |
| **Scope**    | Daily individual/small team           | Overall project lifecycle        |
| **Focus**    | Class/object details                  | Risk and architecture            |
| **Duration** | Short cycles                          | Long-term phases                 |
| **Blurring** | Analysis/design intentionally blurred | Clear phase distinctions         |
| **Output**   | Class specifications                  | Project milestones, architecture |
# 3 The Coad-Yourdon Method
## 3.1 Overview
- Primary strength in **system analysis**
- Describes **static characteristics**
- Addresses both application and infrastructure
### 3.1.1 SOSAS Steps
| Step           | Description                                                                            |
| -------------- | -------------------------------------------------------------------------------------- |
| **Subjects**   | Data flow diagrams for objects                                                         |
| **Objects**    | Identify object classes and class hierarchies                                          |
| **Structures** | Classification structures (inheritance) and composition structures (other connections) |
| **Attributes** | Identify attributes of each class                                                      |
| **Services**   | Identify all behaviors/methods for each class                                          |
### 3.1.2 Four Major System Components
| Component                       | Description                       |
| ------------------------------- | --------------------------------- |
| **Problem Domain Component**    | Core business objects             |
| **Human Interaction Component** | User interface elements           |
| **Task Management Component**   | Concurrency and task coordination |
| **Data Management Component**   | Storage and retrieval of objects  |
# 4 Relationship between OOA and OOD
![[Pasted image 20260401143130.png]]
```
┌────────────────────────────────────────────────────────────────┐
│                    OOA → OOD TRANSFORMATION                    │
├────────────────────────────────────────────────────────────────┤
│                                                                │
│  OOA Models                    OOD Models                      │
│  ┌─────────────────┐          ┌─────────────────┐              │
│  │ Use Cases       │─────────▶│ Subsystem Design│              │
│  └─────────────────┘          └─────────────────┘              │
│                                                                │
│  ┌─────────────────┐          ┌─────────────────┐              │
│  │ CRC Cards       │─────────▶│ Class/Object    │              │
│  │ (attributes,    │          │ Design          │              │
│  │  operations,    │          └─────────────────┘              │
│  │  collaborations)│                                           │
│  └─────────────────┘                                           │
│                                                                │
│  ┌─────────────────┐          ┌─────────────────┐              │
│  │ Object          │─────────▶│ Message Design  │              │
│  │ Relationship    │          └─────────────────┘              │
│  │ Model           │                                           │
│  └─────────────────┘                                           │
│                                                                │
│  ┌─────────────────┐          ┌─────────────────┐              │
│  │ CRC Cards       │─────────▶│ Responsibilities│              │
│  │ (attributes,    │          │ Design          │              │
│  │  operations,    │          └─────────────────┘              │
│  │  collaborations)│                                           │
│  └─────────────────┘                                           │
└────────────────────────────────────────────────────────────────┘
```
## 4.1 OOA, OOD, OOP Relationship
| Phase   | Focus                                              | Output                           |
| ------- | -------------------------------------------------- | -------------------------------- |
| **OOA** | Understanding problem domain, identifying concepts | Requirements, conceptual classes |
| **OOD** | Defining software objects and their collaborations | Architecture, detailed design    |
| **OOP** | Implementing design in code                        | Executable software              |
## 4.2 Example
- Library System
- **OOA**: Identify Book, Member, Librarian as concepts
- **OOD**: Define Book class with `title`, `author`, `ISBN` attributes and `issue()`, `return()` methods; define relationships
- **OOP**: Write Java/C++ code implementing these classes

- subsystem design is derived by:
	- considering overall customer requirements (represented with use-cases)
	- events and states that are externally observable (the object behavior model)
- class and object design
	- mapped from the description of attributes, operation and collaboration contained in the CRC model
- Message design driven by
	- the object relationship model
- responsibilities design
	- is derived using the attributes, operations and collaborations described in CRC model.
## 4.3 Layers in Design Model
```
┌─────────────────────────────────────────────────────────────────┐
│                     DESIGN MODEL LAYERS                         │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  ┌─────────────────────────────────────────────────────────┐    │
│  │                    SUBSYSTEM LAYER                      │    │
│  │  • Subsystems enabling customer requirements            │    │
│  │  • Technical infrastructure support                     │    │
│  └─────────────────────────────────────────────────────────┘    │
│                              │                                  │
│  ┌─────────────────────────────────────────────────────────┐    │
│  │                 CLASS AND OBJECT LAYER                  │    │
│  │  • Hierarchy of classes (generalization/specialization) │    │
│  │  • Individual object representation                     │    │
│  └─────────────────────────────────────────────────────────┘    │
│                              │                                  │
│  ┌─────────────────────────────────────────────────────────┐    │
│  │                    MESSAGE LAYER                        │    │
│  │  • Object communication details                         │    │
│  │  • Internal and external interfaces                     │    │
│  └─────────────────────────────────────────────────────────┘    │
│                              │                                  │
│  ┌─────────────────────────────────────────────────────────┐    │
│  │                 RESPONSIBILITIES LAYER                  │    │
│  │  • Data structure for attributes                        │    │
│  │  • Algorithmic design for operations                    │    │
│  └─────────────────────────────────────────────────────────┘    │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```
1. The Subsystem layer:
	- contains a representation of each of the subsystems that enable the software to achieve its customer defined requirements and to implement the technical infrastructure that supports customer requirements.
- The Class and Object Layer:
	- This layer contains a hierarchy of classes, which enable the system to be created using generalizations and increasingly more targeted specializations
	- this layer also represents each object
- The Message Layer:
	- this layer contains the design details, which enables each object to communicate with its collaborators.
	- this layer establishes the internal and external interfaces for the system
- The Responsibilities Layer:
	- this layer contains the data structure and algorithmic design for all operations and attributes for each object.
## 4.4 Generic Component for OOD
| Component                       | Description                                                                             |
| ------------------------------- | --------------------------------------------------------------------------------------- |
| **Problem Domain Component**    | Problem domain classes from OOA; subsystems implementing customer requirements directly |
| **Human Interaction Component** | Subsystems for user interface, interaction design                                       |
| **Task Management Component**   | Subsystems for controlling and coordinating concurrent tasks                            |
| **Data Management Component**   | Subsystems for storage and retrieval of object                                          |
# 5 System Design Process
## 5.1 Definition
- System design develops architectural detail 
- required to build a system or product, 
- defining modules, architecture, components, interfaces, and data 
- based on specified requirements.
## 5.2 System Design Activities
| Activity                       | Description                                   |
| ------------------------------ | --------------------------------------------- |
| **Partition analysis model**   | Divide into cohesive subsystems               |
| **Identify concurrency**       | Determine inherent concurrency from problem   |
| **Allocate subsystems**        | Assign to processors and tasks                |
| **Design user interface**      | Develop UI architecture                       |
| **Design data management**     | Choose strategy for storage/retrieval         |
| **Identify global resources**  | Determine control mechanisms for resources    |
| **Design control mechanisms**  | Define system control flow                    |
| **Handle boundary conditions** | Consider initialization, termination, failure |
| **Review trade-offs**          | Evaluate design alternatives                  |
## 5.3 Partition the Analysis Model
## 5.4 Subsystems
- **Definition**: Cohesive collections of classes, relationships, and behavior packaged together
- **Characterized by**: Responsibilities (services they provide)
- **Interface**: Well-defined interface for external communication
## 5.5 Subsystem Characteristics
| Characteristic            | Description                                      |
| ------------------------- | ------------------------------------------------ |
| **Cohesion**              | Elements share common property or function       |
| **Encapsulation**         | Classes collaborate mainly within subsystem      |
| **Small number**          | Keep number of subsystems manageable             |
| **Internal partitioning** | Can be further divided to reduce complexity      |
| **Communication**         | Peer-to-peer or client-server between subsystems |
# 6 Concurrency and Subsystem allocation
## 6.1 Identifying Inherent Concurrency
- Two objects are **inherently concurrent** if they react to events simultaneously without interacting
- Example: CPU and speaker must operate concurrently
## 6.2 Concurrency Options
| Option                                         | When to Use                                      |
| ---------------------------------------------- | ------------------------------------------------ |
| **Allocate to independent processors**         | High performance, physical distribution required |
| **Allocate to same processor with OS support** | Cost-effective, less overhead                    |
## 6.3 Decision Factor
- Performance requirements
- Cost constraints
- Interprocessor communication overhead
# 7 Task Management
## 7.1 Task Characteristics
| Aspect          | Considerations                                              |
| --------------- | ----------------------------------------------------------- |
| **Initiation**  | Event-driven or clock-driven (both activated by interrupts) |
| **Priority**    | High-priority tasks get immediate resource access           |
| **Criticality** | High-criticality tasks continue even in degraded mode       |
## 7.2 Task Template
| Field                | Description                               |
| -------------------- | ----------------------------------------- |
| **Task Name**        | Name of the object                        |
| **Description**      | Narrative describing purpose              |
| **Priority**         | Low, medium, high                         |
| **Services**         | List of operation responsibilities        |
| **Coordinated By**   | How object behavior is invoked            |
| **Communicates Via** | Input/output data values relevant to task |
# 8 Data Management Component
## 8.1 Areas of Concern
1. Management of critical application data
2. Infrastructure for storage and retrieval of objects
## 8.2 Design Approach
- **Layered design**: Isolate low-level data manipulation from high-level attribute handling
- **DBMS**: Often used as common data store for all subsystems
# 9 Resource Management Component
- Resources: disk drives, processors, communication lines, databases, objects
- **Design challenge**: Subsystems compete for resources concurrently
- **Solution**: Design control mechanisms regardless of resource nature
# 10 Intersubsystem Communication
## 10.1 Contract Definition
| Element            | Description                    |
| ------------------ | ------------------------------ |
| **Type**           | Client-server or peer-to-peer  |
| **Collaborators**  | Participating subsystems       |
| **Components**     | Subsystems supporting services |
| **Message Format** | Structure of communication     |
# 11 Object Design Process
## 11.1 Purpose
- Prepare for implementation based on system design decisions
- Transform analysis and system design models
- Investigate alternative implementations
- Minimize execution time, memory, and other cost measures
## 11.2 Forms of Object Description
| Form                           | Description          | Contents                                                       |
| ------------------------------ | -------------------- | -------------------------------------------------------------- |
| **Protocol Description**       | Interface definition | Messages an object can receive, corresponding operations       |
| **Implementation Description** | Internal details     | Private data structures, procedural descriptions of operations |
## 11.3 Object Design Steps
| Step                                           | Description                            |
| ---------------------------------------------- | -------------------------------------- |
| 1. Develop problem statement                   | Clarify the problem to be solved       |
| 2. Identify objects and classes                | Extract nouns from requirements        |
| 3. Filter out required classes                 | Apply selection criteria               |
| 4. Identify associations, attributes, links    | Determine relationships and properties |
| 5. Prepare data dictionary                     | Document all terms                     |
| 6. Discard unnecessary associations/attributes | Remove redundant or irrelevant items   |
| 7. Apply inheritance                           | Factor commonality into parent classes |
| 8. Check accessibility                         | Ensure queries can be answered         |
| 9. Iterate and refine                          | Continuously improve model             |
| 10. Group classes into modules                 | Organize into cohesive packages        |
# 12 Comparisons
## 12.1 Structured vs OO System Design
| Aspect                 | Structured Design       | Object Oriented Design          |
| ---------------------- | ----------------------- | ------------------------------- |
| **Primary Unit**       | Functions/modules       | Objects                         |
| **Data & Operations**  | Separated               | Encapsulated together           |
| **Reusability**        | Limited                 | High (inheritance, composition) |
| **Maintainability**    | Harder (ripple effects) | Easier (localized changes)      |
| **Real-world Mapping** | Artificial              | Natural                         |
| **Change Impact**      | Widespread              | Localized                       |
## 12.2 System Design vs Object Design
| Aspect      | System Design                 | Object Design                         |
| ----------- | ----------------------------- | ------------------------------------- |
| **Focus**   | High-level architecture       | Detailed object internals             |
| **Scope**   | Overall system structure      | Individual objects                    |
| **Output**  | Subsystems, processors, tasks | Attribute types, operation algorithms |
| **Linkage** | Defines framework             | Fills in details within framework     |
# 13 Design Patterns
## 13.1 Concept
- **Design Pattern** = reusable solution to common design problems
- Captures proven solutions in a structured format
## 13.2 Use in OOAD
| Benefit            | Description                              |
| ------------------ | ---------------------------------------- |
| **Reusability**    | Solutions can be applied across projects |
| **Communication**  | Common vocabulary for designers          |
| **Best Practices** | Encapsulates expert knowledge            |
| **Documentation**  | Well-documented, understood solutions    |
## 13.3 Common Design Patterns
| Pattern       | Purpose                                            |
| ------------- | -------------------------------------------------- |
| **Singleton** | Ensure only one instance of a class                |
| **Factory**   | Create objects without specifying concrete classes |
| **Observer**  | Notify dependents of state changes                 |
| **MVC**       | Separate presentation from business logic          |
# 14 Mapping Design to Code
## 14.1 Process
1. **Class Definition**: Convert class diagram to class declarations
2. **Attribute Implementation**: Map attributes to instance variables
3. **Operation Implementation**: Implement methods as defined
4. **Relationship Implementation**: Implement associations (references, collections)
5. **Interface Implementation**: Implement required interfaces
## 14.2 Example: Construction Company
**Class Diagram Elements**:
- `Company` (1) ― (\*) `Project`
- `Project` (1) ― (1) `ProjectManager`
- `ProjectManager` (1) ― (\*) `TeamMember`
- `Project` (1) ― (\*) `MarketingExecutive`
**Code Mapping**:
```java
class Company {
    private List<Project> projects;
    public void addProject(Project p) { ... }
}

class Project {
    private String location;
    private Date startDate;
    private Date completionDate;
    private ProjectManager manager;
    private List<MarketingExecutive> marketers;
}

class ProjectManager {
    private String name;
    private List<TeamMember> team;
}

class TeamMember {
    private String category; // designer, plumber, etc.
}
```
# 15 Exception and Error Handling
## 15.1 Types of Exceptions
| Type                     | Description                 | Example                                     |
| ------------------------ | --------------------------- | ------------------------------------------- |
| **Checked Exceptions**   | Must be handled or declared | IOException, SQLException                   |
| **Unchecked Exceptions** | Runtime; may not be handled | NullPointerException, ArrayIndexOutOfBounds |
| **Errors**               | Serious system problems     | OutOfMemoryError, StackOverflowError        |
## 15.2 Exception Handling in OOP
### 15.2.1 Mechanisms
- `try` – block where exception may occur
- `catch` – block that handles specific exception
- `throw` – explicitly raise exception
- `throws` – declare exceptions that method may throw
- `finally` – block that always executes
### 15.2.2 Example:
```java
try {
    // risky operation
    int result = 100 / divisor;
} catch (ArithmeticException e) {
    // handle division by zero
    System.out.println("Cannot divide by zero");
} finally {
    // cleanup code
}
```
## 15.3 Error Handling Best Practices
|Practice|Description|
|---|---|
|**Specific Exceptions**|Catch specific rather than generic|
|**Meaningful Messages**|Provide context for debugging|
|**Logging**|Record errors for analysis|
|**Resource Cleanup**|Use finally or try-with-resources|
|**Fail Fast**|Detect errors early|
# 16 Interface and Implementation in OOD
|Concept|Description|
|---|---|
|**Interface**|Contract specifying what operations are available|
|**Implementation**|Actual code providing the functionality|
**Example**:
```java
// Interface (what)
public interface PaymentProcessor {
    boolean processPayment(double amount);
    void refund(double amount);
}

// Implementation (how)
public class CreditCardProcessor implements PaymentProcessor {
    public boolean processPayment(double amount) {
        // credit card specific logic
    }
    public void refund(double amount) {
        // credit card specific refund
    }
}
```
# 17 Object DBMS
## 17.1 Major Features
|Feature|Description|
|---|---|
|**Object Identity**|Unique OIDs for objects|
|**Complex Objects**|Support for nested/composite objects|
|**Encapsulation**|Data + methods stored together|
|**Inheritance**|Class hierarchies in database|
|**Polymorphism**|Operations on subtypes|
|**Persistence**|Objects survive program execution|
## 17.2 Object DBMS vs RDBMS
|Aspect|Object DBMS|RDBMS|
|---|---|---|
|**Data Model**|Objects and classes|Tables and rows|
|**Data Representation**|Complex objects|Flat tables|
|**Relationships**|Direct references|Foreign keys|
|**Inheritance**|Supported|Not directly supported|
|**Encapsulation**|Methods stored with data|Business logic separate|
|**Query Language**|Object Query Language (OQL)|SQL|
|**Performance**|Better for complex objects|Better for simple queries|
|**Schema Evolution**|Easier|Requires migration|
# 18 Summary
|Topic|Key Points|
|---|---|
|**OOA vs OOD**|OOA: _what_; OOD: _how_|
|**Booch Method**|Micro (daily) + Macro (project) processes|
|**Coad-Yourdon**|SOSAS: Subjects, Objects, Structures, Attributes, Services|
|**Design Layers**|Subsystem → Class/Object → Message → Responsibilities|
|**OOD Components**|Problem domain, Human interaction, Task management, Data management|
|**System Design**|Partition, concurrency, allocation, UI, data management|
|**Object Design**|Protocol + Implementation descriptions|
|**Design Patterns**|Reusable solutions to common problems|
|**Exception Handling**|Checked, unchecked, errors; try-catch-finally|
|**Object DBMS**|OIDs, inheritance, encapsulation; vs RDBMS|


[[Chapter 6 Object Oriented Testing]]