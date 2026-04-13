- **8 Hours**

[[Chapter 1 Introduction to Software and Software Engineering]]
# 1 Fundamental Concepts of Object Orientation
## 1.1 Class
- **Definition**: Blueprint or template that describes characteristics and behavior of similar objects.
- **Analogy**: A class is like a cookie cutter; objects are the cookies.
- **Example**: `Computer` is a class representing all computers (lab computers, home computers) regardless of model or manufacturer.
## 1.2 Objects
- **Definition**: Identifiable entity with characteristics (attributes) and behavior (operations). Instance of a class.
- **Creation**: Space allocated in memory only when object is physically created.
- **Relationship**: Multiple objects can be created from one class.
```
┌─────────────────┐              ┌───────────────────┐
│     Class       │              │     Objects       │
│   Computer      │  instantiates│                   │
│ (blueprint)     │ ───────────▶ │  myPC : Computer  │
└─────────────────┘              │  labPC : Computer │
                                 │  server : Computer│
                                 └───────────────────┘
```
## 1.3 Inheritance
-  **Definition**: Ability to create new class from existing class, inheriting all non-private features.
- **Purpose**: Promotes **reusability** and **reliability**.
- **Direction**: Base class (parent) → Derived class (child).
```
┌─────────────────┐
│     Fruit       │  ← Base class
│ - taste         │     (common characteristics)
│ - price         │
│ - season        │
└─────────────────┘
        ▲
        │ inheritance
    ┌───┴───────┬─────────────────┐
    │           │                 │
┌───▼────┐  ┌───▼───────┐  ┌──────▼─────┐
│ Mango  │  │ Orange    │  │ Banana     │  ← Derived classes
│ + pulp │  │ + peel    │  │ + length   │   (specific features)
│ + color│  │ + segments│  │ + curvature│
└────────┘  └───────────┘  └────────────┘
```
## 1.4 Polymorphism
- **Definition**: Ability to take more than one form (poly = many, morphe = forms).
- **Achieved through**: Function overloading, operator overloading, function overriding, templates.
### 1.4.1 Types
| Type            | Compile Time                               | Run Time                    |
| --------------- | ------------------------------------------ | --------------------------- |
| When Determined | At compilation                             | At execution                |
| Mechanism       | Function overloading, operator overloading | virtual functions, pointers |
| Speed           | fast                                       | slower                      |
| Flexibility     | less                                       | more                        |
```cpp
// Compile-time polymorphism (overloading)
void draw(Circle c);
void draw(Square s);

// Run-time polymorphism (overriding)
class Shape { virtual void draw(); };
class Circle : public Shape { void draw(); };  // draw() behaves differently
```
## 1.5 Encapsulation
- **Definition**: Binding functions and data together, hiding data from unauthorized access.
- **Purpose**: Data hiding, exposing only relevant details.
- **Real-world analogy**: Smart phone – you know how to make calls but not the internal circuitry.
```
┌─────────────────────────────┐
│          Object             │
│  ┌─────────────────────┐    │
│  │     Data (hidden)   │    │
│  │  - attribute1       │    │
│  │  - attribute2       │    │
│  └─────────────────────┘    │
│  ┌─────────────────────┐    │
│  │   Operations        │    │
│  │  (exposed interface)│    │
│  │  + operation1()     │    │
│  │  + operation2()     │    │
│  └─────────────────────┘    │
└─────────────────────────────┘
```
## 1.6 Data Abstraction
- **Definition**: Representing essential features without including background details.
- **Purpose**: Use complex objects without knowing internal workings.
- **Example**: Building a `Car` class using `Engine`, `Gearbox`, `Steering` components – you only need to know how to interface with them, not how they work internally.
## 1.7 Adv of OOSD
| Benefit                           | Description                                  |
| --------------------------------- | -------------------------------------------- |
| **Less Maintenance**              | Modular structure makes changes easier       |
| **Code Reusability**              | Inheritance allows reuse across projects     |
| **Faster Development**            | Reuse reduces development time               |
| **Improved Reliability**          | Tested components reused                     |
| **Real-world Modeling**           | Natural representation of problem domain     |
| **Better Abstraction**            | Complexity hidden at object level            |
| **Reduced Transition Complexity** | Smoother movement between development phases |
## 1.8 OOS vs Procedural/Functional Oriented System
| Aspect                    | Object Oriented System            | Procedural/Function Oriented     |
| ------------------------- | --------------------------------- | -------------------------------- |
| **Focus**                 | Data and operations together      | Functions (operations)           |
| **Modularity**            | Objects encapsulate data          | Functions operate on global data |
| **Data Security**         | Data hiding through encapsulation | Data accessible globally         |
| **Reusability**           | High (inheritance, composition)   | Low (copy-paste code)            |
| **Maintenance**           | Easier (localized changes)        | Harder (ripple effects)          |
| **Real-world Mapping**    | Natural                           | Artificial                       |
| **Complexity Management** | Better abstraction                | Limited abstraction              |
# 2 Object Oriented System development
## 2.1 OO Development Cycle
- Applies object orientation across **all development activities**: analysis, design, programming, testing, maintenance.
- Requires **more time in early phases** (requirements, analysis, design) – about 25% of development time before coding begins.
### 2.1.1 Transformations in OOD
| Transformation     | Input             | Output                                    | Focus                       |
| ------------------ | ----------------- | ----------------------------------------- | --------------------------- |
| **Analysis**       | User needs        | System requirements, responsibilities     | _What_ the system should do |
| **Design**         | Problem statement | Detailed design, architecture, test plans | _How_ to build the system   |
| **Implementation** | Detailed design   | Operational system, deployment            | _Building_ the solution     |
## 2.2 OO Analysis
- **Definition**: Investigation of the problem and requirements rather than finding a solution.
- **Key Questions in OOA**:
	- What will my program do?
	- What will the classes be?
	- What will each class be responsible for?
- **OOA Activities**:
	1. Finding objects
	2. Organizing objects
	3. Describing how objects interact
	4. Defining operations of objects
	5. Defining objects internally
## 2.3 Identifying Elements in Object Model
### 2.3.1 Identifying Objects and Classes
#### 2.3.1.1 Grammatical Parse Method:
1. underline each noun/noun clause in problem statement
2. Enter in a table
3. Note Synonyms
4. Filter using selection criteria
#### 2.3.1.2 Categories of Objects to Look For:
| Category                 | Description                                             | Example                           |
| ------------------------ | ------------------------------------------------------- | --------------------------------- |
| **External Entities**    | Systems/devices/people that produce/consume information | Sensors, user, other systems      |
| **Things**               | Reports, displays, signals                              | Alarm, receipt, status display    |
| **Occurrences/Events**   | Actions within system operation                         | Sensor event, transaction         |
| **Roles**                | People interacting with system                          | Manager, homeowner, operator      |
| **Organizational Units** | Relevant groups                                         | Division, monitoring service      |
| **Places**               | Context of problem                                      | Manufacturing floor, loading dock |
| **Structures**           | Classes of objects                                      | Four-wheel vehicle, sensor array  |
### 2.3.2 SafeHome Example: Object Identification
- **Problem Statement (excerpt)**:  
> _SafeHome software enables the homeowner to configure the security system, monitors all sensors connected to the security system, and interacts with the homeowner through a keypad and function keys contained in the SafeHome control panel._

**Extracted Potential Objects**:

| Potential Object         | Classification         |
| ------------------------ | ---------------------- |
| Homeowner                | Role / External Entity |
| Sensor                   | External Entity        |
| Control Panel            | External Entity        |
| Installation             | Occurrence             |
| System (security system) | Thing                  |
| Master Password          | Thing                  |
| Telephone Number         | Thing                  |
| Sensor Event             | Occurrence             |
| Audible Alarm            | External Entity        |
| Monitoring Service       | Organizational Unit    |
### 2.3.3 Selection Criteria for Objects
|Criterion|Description|
|---|---|
|**Retained Information**|Information must be remembered for system to function|
|**Needed Services**|Identifiable operations that change attributes|
|**Multiple Attributes**|Single-attribute objects may be better as attributes|
|**Common Attributes**|Attributes apply to all occurrences|
|**Essential Requirements**|External entities essential to solution|
Potential object should satisfy most/all of these
# 3 Specifying the Attributes
- Attributes **define the object** in problem context.
- **How to find attributes**:
    1. Study processing narrative
    2. Identify data items that "belong" to the object
    3. Ask: _What data fully defines this object in the problem context?_
## 3.1 Visibility in OOD
| Visibility    | Symbol | Scope        | Description                             |
| ------------- | ------ | ------------ | --------------------------------------- |
| **Public**    | `+`    | Any          | Accessible to all classes               |
| **Private**   | `-`    | Same class   | Accessible only within class            |
| **Protected** | `#`    | Subclasses   | Accessible within inheritance hierarchy |
| **Package**   | `~`    | Same package | Accessible within same package          |
## 3.2 Types of Visibility
### 3.2.1 Attribute Visibility
- Determines which classes can access an attribute
- **Private attributes**: Encapsulated, accessed only through methods
- **Public attributes**: Directly accessible (less secure)
### 3.2.2 Parameter Visibility
- **Definition**: Variables passed to methods as parameters
- **Scope**: Exist only during method execution
- **Example**: In `calculateArea(length, width)`, `length` and `width` have parameter visibility
### 3.2.3 Global Visibility
- **Definition**: Variables accessible throughout the program
- **Risk**: May violate encapsulation principles
- **Better alternative**: Use class-level (static) attributes with controlled access
```cpp
class BankAccount {
private:                     // Private visibility
    double balance;          // Only accessible within class methods
    
public:                      // Public visibility
    void deposit(double amt) {  // amt has parameter visibility
        balance += amt;
    }
};

double globalTaxRate = 0.15;  // Global visibility (avoid in OOP)
```
## 3.3 Association Visibility
- **Definition**: How objects can navigate to related objects via associations
- **Types**:
    - **Navigable** (→): One-way access
    - **Bidirectional** (↔): Both objects can access each other
    - **Non-navigable** (—): No direct access (access through other means)
```
┌─────────┐  navigable     ┌─────────┐
│ Order   │───────────────▶│ Customer│  (Order can access Customer)
└─────────┘                └─────────┘

┌─────────┐  bidirectional ┌─────────┐
│ Student │◀──────────────▶│ Course  │  (Both can access each other)
└─────────┘                └─────────┘

┌─────────┐  non-navigable ┌─────────┐
│ Teacher │────────────────│ Student │  (No direct access either way)
└─────────┘                └─────────┘
```
# 4 Defining Operations
## 4.1 Three Categories of Operations
| Category         | Description                      | Example                             |
| ---------------- | -------------------------------- | ----------------------------------- |
| **Manipulation** | Add, delete, modify, select data | `addSensor()`, `deleteEvent()`      |
| **Computation**  | Perform calculations             | `calculateFine()`, `computeTotal()` |
| **Monitoring**   | Detect events or conditions      | `checkSensor()`, `monitorAlarm()`   |
## 4.2 How to Find Operations
1. Study processing narrative
2. Isolate verbs (grammatical parse)
3. Connect verbs to specific objects
4. Consider communication between objects
### 4.2.1 Generic Life History Operations:
- **Create** – instantiate object
- **Modify** – change attribute values
- **Read** – retrieve information
- **Delete** – destroy object
# 5 CRC Cards
## 5.1 Concept
- Class Responsibility Collaboration Cards
- Index cards used for object oriented analysis and design
- purpose: brainstorming, identifying classes, their responsibilities and collaborations
## 5.2 CRC Card Structure
```
┌─────────────────────────────────────┐
│           CLASS NAME                │
├─────────────────────────────────────┤
│           RESPONSIBILITIES          │
│  • Responsibility 1                 │
│  • Responsibility 2                 │
│  • Responsibility 3                 │
├─────────────────────────────────────┤
│           COLLABORATIONS            │
│  • Collaborator Class A             │
│  • Collaborator Class B             │
└─────────────────────────────────────┘
```
## 5.3 Components
| Component            | Description                                             |
| -------------------- | ------------------------------------------------------- |
| **Class**            | Name of the class (noun from problem domain)            |
| **Responsibilities** | What the class knows (attributes) and does (operations) |
| **Collaborations**   | Other classes needed to fulfill responsibilities        |
## 5.4 Importance in Object Modeling
|Purpose|Description|
|---|---|
|**Brainstorming**|Collaborative identification of classes|
|**Simplicity**|Low-tech, easy to modify|
|**Focus**|Forces focus on responsibilities, not implementation|
|**Communication**|Visual tool for team discussions|
|**Iterative**|Easy to refine and reorganize|
## 5.5 Example for Library Ssytem
```
┌─────────────────────────────────────┐
│              Book                   │
├─────────────────────────────────────┤
│  RESPONSIBILITIES:                  │
│  • Know its title, author, ISBN     │
│  • Track availability               │
│  • Update status on loan            │
├─────────────────────────────────────┤
│  COLLABORATIONS:                    │
│  • Loan                             │
│  • Catalog                          │
└─────────────────────────────────────┘

┌─────────────────────────────────────┐
│              Loan                   │
├─────────────────────────────────────┤
│  RESPONSIBILITIES:                  │
│  • Record borrower details          │
│  • Track due date                   │
│  • Calculate fines                  │
├─────────────────────────────────────┤
│  COLLABORATIONS:                    │
│  • Book                             │
│  • Member                           │
└─────────────────────────────────────┘
```
# 6 OO vs Conventional Approaches
## 6.1 Key Differences
| Aspect            | Conventional Design          | OO Design                          |
| ----------------- | ---------------------------- | ---------------------------------- |
| **Primary Unit**  | Functions/modules            | Objects                            |
| **Data Handling** | Data separate from functions | Data + functions together          |
| **Encapsulation** | Limited (global data)        | Strong (data hiding)               |
| **Inheritance**   | Not supported                | Supported                          |
| **Reusability**   | Limited                      | High (via inheritance/composition) |
| **Change Impact** | Ripple effects               | Localized                          |
| *Maintenance**    | More difficult               | Easier                             |
## 6.2 Encapsulation & Inheritance: OO vs Conventional
| Feature           | Conventional                | OO                         | Explanation                          |
| ----------------- | --------------------------- | -------------------------- | ------------------------------------ |
| **Encapsulation** | Data global or module-level | Data hidden within objects | OO protects data integrity           |
| **Inheritance**   | Not available               | Classes can inherit        | OO enables reuse without duplication |
## 6.3 OO Design Cycle vs Conventional Design Cycle
| Phase              | Conventional Design Cycle            | OO Design Cycle                       |
| ------------------ | ------------------------------------ | ------------------------------------- |
| **Analysis**       | Focus on functions                   | Focus on objects and responsibilities |
| **Design**         | Data flow diagrams, structure charts | Class diagrams, interaction diagrams  |
| **Implementation** | Functions operating on data          | Objects sending messages              |
| **Testing**        | Unit, integration, system            | Class testing, inter-class testing    |
| **Transition**     | Distinct phase boundaries            | Smoother transitions between phases   |
## 6.4 Example: Building a Library System
| Conventional Approach                                    | OO Approach                                  |
| -------------------------------------------------------- | -------------------------------------------- |
| Functions: `issueBook()`, `returnBook()`, `searchBook()` | Objects: `Book`, `Member`, `Loan`, `Catalog` |
| Data stored in global structures                         | Data encapsulated within objects             |
| Changes require modifying multiple functions             | Changes localized to specific objects        |
# 7 Requirement Elicitation in OOA
**Process**:
1. **Identify Stakeholders**: Users, domain experts, clients
2. **Gather Requirements**: Interviews, workshops, observation
3. **Analyze Domain**: Understand problem domain terminology
4. **Identify Objects**: Extract nouns from requirements
5. **Define Use Cases**: Capture interactions from user perspective
6. **Validate**: Confirm understanding with stakeholders

**How OOA Differs from Traditional Elicitation**:
- Focuses on identifying **objects** rather than functions
- Uses **real-world modeling** to capture domain concepts
- **Iterative refinement** of objects and relationships
# 8 Summary
| Topic             | Key Points                                                    |
| ----------------- | ------------------------------------------------------------- |
| **Class**         | Blueprint, template, group of similar objects                 |
| **Object**        | Instance of class, identifiable entity                        |
| **Inheritance**   | Reusability, is-a relationship, base/derived                  |
| **Polymorphism**  | Many forms, compile-time (overloading), run-time (overriding) |
| **Encapsulation** | Data hiding, binding data + methods, security                 |
| **Abstraction**   | Essential features only, complexity hiding                    |
| **OOA**           | What questions, find objects, define responsibilities         |
| **CRC Cards**     | Class-Responsibility-Collaboration, brainstorming tool        |
| **Visibility**    | Public (+), private (-), protected (#), package (~)           |


[[Chapter 3 Structural, Behavioral and Architectural Modeling]]