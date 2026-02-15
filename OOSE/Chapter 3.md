---
---
# 3.1 Class Relationship
Present at: [[#3.A.v Class Relationship]]
# 3.2 Conceptual Model of UML
## 3.2.A Concept of UML
- Unified Modeling Language
- standardized visual language for specifying, constructing and documenting software systems.
- is not a method, only notation.
- used with various development processes.
- combines best practices from earlier OO methods (Booch, OMT, OOSE).
	- OMT (Object Modeling Technique)
		- precursor to UML
		- focusing on objects, dynamics and functions
## 3.2.B Use of UML in System Development
| Purpose       | Description                                                    |
| ------------- | -------------------------------------------------------------- |
| **Visualize** | Represent complex systems graphically for better understanding |
| **Specify**   | Build precise, unambigouus models of systems                   |
| **Construct** | Map models directly to implementation code                     |
| **Document**  | Capture architectural decisions, requirements, design          |
## 3.2.C Five views of UML
| View                | Focus                                              | Diagrams Used                                 |
| ------------------- | -------------------------------------------------- | --------------------------------------------- |
| **Use Case View**   | System Functionality from user persepctive         | Use Case                                      |
| **Logical View**    | System structure (classes, objects, relationships) | Class, Object, State, Sequence, Communication |
| **Process View**    | Concurrency, performance, scalability              | Activity, State, Sequence                     |
| **Deployment View** | Physical distribution across hardware              | Deployment                                    |
## 3.2.D Conceptual Model of UML
Has 3 major elements
### 2.D.i Basic Building Blocks
#### D.i.a Things
- nouns of the model
- structural - mostly static parts
- behavioral - dynamic parts
- grouping things - organizational parts
- annotational things - explanatory parts
##### i.a.1 Structural Things
| Thing             | Description                                                  | Notation                                            |
| ----------------- | ------------------------------------------------------------ | --------------------------------------------------- |
| **Class**         | Set of objects with shared attributes, operations, semantics | Rectangle with name, attributes, operations         |
| **Interface**     | Collection of operations specifying a service                | Circle (lollipop) or rectangle with `<<interface>>` |
| **Collaboration** | Defines interaction between roles                            | Dashed ellipse                                      |
| **Use Case**      | Sequence of actions yielding observable result               | Ellipse with name                                   |
| **Component**     | Physical resource (processor/device)                         | Cube                                                |
##### i.a.2 Behavioral Things
| Thing             | Description                                          |
| ----------------- | ---------------------------------------------------- |
| **Interaction**   | Set of messages exchanged between objects            |
| **State Machine** | Behavior showing states and transitions of an object |
| **Activity**      | Flow of control between steps                        |
##### i.a.3 Grouping Things
| Thing             | Description                                    | Notation                                            |
| ----------------- | ---------------------------------------------- | --------------------------------------------------- |
| **Package**       | General-purpose mechanism to group elements    | Tabbed folder                                       |
##### i.a.4 Annotational Things
| Thing    | Description                 | Notation                        | Figure:                                     |
| -------- | --------------------------- | ------------------------------- | ------------------------------------------- |
| **Note** | Comment attached to element | Rectangle with dog eared corner | ![[Pasted image 20260207224041.png \| 400]] |
#### D.i.b Relationships
- verbs of the model
##### i.b.1 Dependency Relationship
- One thing (client) uses another thing (supplier)
- change to supplier may affect client
- unidirectional (client -> supplier)
- notation of dashed directed line (->)
 - used when one class uses operations/variables of another; temporary connection.
- figure:
  ![[Pasted image 20260208112349.png]]
##### i.b.2 Association Relationship
- Structural connection between objects of two classes.
- notation of solid line connecting clauses
- binary association: connects exactly 2 classes
- N-ary association: connects 3+ classes
###### Association Adornments:
| Adornment    | Description                                          | Example                   |
| ------------ | ---------------------------------------------------- | ------------------------- |
| Name         | Describes nature of relationship                     | `works for`               |
| Role         | Face a class presents at assocation end              | `employee`, `employer`    |
| Multiplicity | How many objects connected                           | `1`, `0..*`, `1..*`       |
| Aggregation  | "Has-a" relationship (whole-part)                    | Car has Wheels            |
| Composition  | Stronger whole-part where part lives/dies with whole | Order contains OrderItems |
Figures:
1. Name:
	1. ![[Pasted image 20260209080653.png]]
2. Role: 
	1. ![[Pasted image 20260209080849.png]]
3. Multiplicity
	- ![[Pasted image 20260209081206.png]]
4. Aggregation
	1. ![[Pasted image 20260209082121.png]]
	2. ![[Pasted image 20260209082131.png]]
5. Composition:
	1. ![[Pasted image 20260214165610.png]]
###### Multiplicity Values
| Expression    | Meaning             |
| ------------- | ------------------- |
| `1`           | Exactly one         |
| `0..1`        | Zero or one         |
| `0..*` or `*` | Zero or more (many) |
| `1..*`        | One or more         |
| `2..5`        | Integer range       |
##### i.b.3 Aggregation vs Composition
| Aspect        | Aggregation             | Composition                       |
| ------------- | ----------------------- | --------------------------------- |
| Diamond       | Hollow                  | Filled                            |
| Part lifetime | Can exist without whole | cannot exist without whole        |
| sharing       | part can be shared      | part belongs to exactly one whole |
| example       | Car <-> Wheel           | Window <- Frame                   |
| Relationship  | "has-a" (weaker)        | "contains" (stronger)             |
##### i.b.4 Generalization
- Parent/child relationship where child inherits from parent
- notation of solid line with hollow triangular arrowhead (-> ▷ ) pointing to parent.
- also called inheritance "is-a" relationship
- figure:
	- ![[Pasted image 20260208112711.png]]
##### i.b.5 Realization
- one element specifies behavior, another implements it.
- notation of: dashed line with hollow triangular arrowhead.
- commonly uses: Interface - -> Class, Use Case - -> Collaboration.

	- Dependency, Association, Generalization, Realization
- Diagrams (views of the model)
	- 13 diagram types organized into structural/behavioral categories
### 2.D.ii Rules
- How building blocks may be put together
- Rules for:
	- Naming (what one can call things)
	- Scope (context visibility)
	- Integrity (how things relate properly)
### 2.D.iii Common Mechanisms
- Stereotypes -> Extend UML vocabulary ( `<<include>>`, `<<extend>>`)
- Tagged values -> properties (`{author=Smith}`)
- Constraints -> rules (`{balance >= 0}`)
## 3.2.E Conceptual Model vs Implementation Model
| Aspect          | Conceptual Model                 | Implementation Model                   |
| --------------- | -------------------------------- | -------------------------------------- |
| **Purpose**     | Understand real-world domain     | Build software system                  |
| **Abstraction** | High-level, problem-focused      | Low-level, solution-focused            |
| **Language**    | Domain vocabulary                | Programming Language constructs        |
| **Audience**    | Stakeholders, domain experts     | Developers, testers                    |
| **Change**      | Stable (domain rarely changes)   | Volatile (code evolves)                |
| **Examples**    | Domain model, conceptual classes | Class Diagram with methods, DB schemas |
## 3.2.F Behavioral Model of the System
- Describes dynamic behavior of objects over time
- it answers how the system responds to events
- Diagrams used:
	- State Chart diagram (object states)
	- Activity Diagram (workflow)
	- Sequence Diagram (message ordering)
	- Communication Diagram (message structure)
## 3.2.G Domain Modeling
- Domain Model = visual representation of real world concepts, not software classes.
- Shows:
	- Conceptual classes (real world entities)
	- Associations between them
	- Attributes (simple properties)
- Purpose:
	- Bridges communication gap between domain experts and developers
	- Capture key terminology and relationships
	- Foundation for design class diagrams.
## 3.2.H Conceptual Classes
- Definition:
	- Real world concepts or things in the domain of interest
- not software classes -> they exist regardless of system
- how to find them:
	- noun identification (underline nouns in requirements)
	- category lists (use predefined categories)
	- reuse existing domain models
### 2.H.i Category List Method:
| Category         | Examples                    |
| ---------------- | --------------------------- |
| Physical objects | Bok, Car, Product           |
| Places           | Store, Warehouse, Office    |
| Transactions     | Sale, Payment, Order        |
| People           | Customer, Employee, Manager |
| Organizations    | Department, Company, Bank   |
### 2.H.ii Online Movie Ticket Booking
- Conceptual classes: Movie, Show, Theater, Seat, Booking, Payment, Customer
- Not Conceptual classes: Database, Connection, Controller
	- these are design/implementation

- The vocabulary of the UML encompasses three kinds of building blocks:
---
---
# 3.3 UML Diagrams
## 3.3.A Class Diagram
### 3.A.i Concept
- Class diagram = static structure diagram showing system's classes, attributes, operations and relationships
- most common UML diagram for object oriented modeling
- represents the logical view of a system.
- blueprint for implementation
### 3.A.ii Notation
- A class is rendered as a rectangle divided into 3 compartments
	- Name, Attribute & Operations
- figure:
  ![[Pasted image 20260208104157.png]]
### 3.A.ii Components
#### A.iii.a Class Name
- **Simple name**: Just the class name (e.g., `Student`)
- **Qualified Name**: Package + classname (e.g., `University::Student)
- **Abstract class**: Name in italics of `{abstract}`
- a class maybe drawn showing only its name as shown below
- symbols:
	- ![[Pasted image 20260208104404.png]]
#### A.iii.b Attributes
| Visbility | Symbol | Meaning                                |
| --------- | ------ | -------------------------------------- |
| Public    | +      | Accessibly by any class                |
| Private   | -      | Accessibly only within class           |
| Protected | #      | Accessible within class and subclasses |
| Package   | ~      | Accessible within same package         |
- Visibility example:
	- ![[Pasted image 20260208110422.png]]
- Attribute example:
```txt
+ name: String
- studentId: Integer = 1001
# dateOfBirth: Date
~ gpa: Float {readonly}
```
- a class may have any number of attributes or no attributes
- represents some property of the thing to be modeled
- shared by all objects of that class
- attribute name is a short noun or noun phrase that represents some property of its enclosing class.
- unless otherwise specified, attributes are always changeable.
- use the readonly property to indicate that the attribute's value may not be changed after the object is initialized
- we can also specify the visibility, scope and multiplicity of each attribute
	- for example, legal attribute declarations
		- origin <- Name only
		- + origin <- Visibility and name
		- origin: Point <- Name and type
		- name: string\[0..1] <- Name, type, and multiplicity
		- origin: Point = (0, 0) <- Name, type and initial value
		- id: Integer `{readonly}` <- Name and property
- Figures:
	- 1.
		- ![[Pasted image 20260208104526.png]]
	- 2.
		- ![[Pasted image 20260208104553.png]]
#### A.iii.c Operations
- abstraction of something you can do to an object that is shared by all objects of that class
- Implementation of a service can be requested from an object.
- Represents what the class does.
- Syntax: `[visibility] name ([parameter list]) [: return type] [{property}] `
- operations may be drawn showing only their names
- can specify the visibility, scope, parameters, return type, concurrency semantics, etc. of each operation.
- collectively, the name of an operation plus its parameters (including its return type, if any) is called the operation's signature
- For example: the following are legal declarations:
	- display <- Name only
	- + display <- visibility and name
	- set(n: Name, s: String) <- Name and parameters
	- getID(): Integer <- Name and return type
	- restart() `{guarded}` <- Name and property
- Example:
```txt
+ registerCourse(courseId: Integer): Boolean
- calculateGPA(): Float
# validatePayment(): void
```
- Figure:
	- ![[Pasted image 20260208104825.png]]
#### A.iii.d Responsibilities
- Contract or obligation of a class
- Documented in a separate compartment at bottom
- Textual description of what class must provide
- Example:
```txt
┌───────────────────────────────────┐
│    Student                        │
├───────────────────────────────────┤
│ - name: String                    │
│ - id: Integer                     │
├───────────────────────────────────┤
│ + register()                      │
│ + dropCourse()                    │
├───────────────────────────────────┤
│ Responsibilities                  │
│ • Maintain student personal info  │
│ • Handle course registration      │
└───────────────────────────────────┘
```
### 3.A.iv Advanced Class Features
#### A.iv.a Multiplicity of a class
- number of instances a class may have.
- written in upper right corner
- example
```txt
┌─────────────────────┐
│    NetworkController│ 1
├─────────────────────┤
│ ...                 │
└─────────────────────┘

┌─────────────────────┐
│    ControlRod       │ 3
├─────────────────────┤
│ ...                 │
└─────────────────────┘
```
- figure:
	- ![[Pasted image 20260208110654.png]]
#### A.iv.b Abstract, Root, Leaf
| Type            | Notation                    | Meaning            |
| --------------- | --------------------------- | ------------------ |
| Abstract Class  | *ClassName* or `{abstract}` | Cannot instantiate |
| Abstract Method | *methodName()*              | No implementation  |
| Root Class      | `{root}`                    | No ancestors       |
| Leaf Class      | `{leaf}`                    | No descendants     |
#### A.iv.c Polymorphic Elements
- Methods with same signature in different classes.
- Represented in *italics*.
### 3.A.v Class Relationship
| Relationship       | Notation | Description                  |
| ------------------ | -------- | ---------------------------- |
| **Dependency**     | - - - →  | Uses relationship            |
| **Association**    | ———      | Structural connection        |
| **Aggregation**    | ◇———     | Has-a (weak whole-part)      |
| **Composition**    | ◆———     | Contains (strong whole-part) |
| **Generalization** | —▷       | Inheritance (is-a)           |
| **Realization**    | - - - ▷  | Interface implementation     |
### 3.A.vi UML classifiers
| Name        | Description                                                                                                                                                         | Figure                               |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------ |
| Interface   | collection of operations that are used to specify a service of a class or component                                                                                 | ![[Pasted image 20260208105648.png]] |
| Datatype    | - type whose values are immutable<br>- including primitive built-in and enumeration types                                                                           | ![[Pasted image 20260208105732.png]] |
| Association | Description of a set of links, each of which relates two or more objects                                                                                            |                                      |
| Signal      | the specification of an asynchronous message communicated between instances                                                                                         |                                      |
| Component   | a modular part of a system that hides its implementation behind a set of external interfaces                                                                        | ![[Pasted image 20260208105843.png]] |
| Node        | a physical element that exists at run time and that represents a computational resource generally having atleast some memory and often processing capabilities.     | ![[Pasted image 20260208110136.png]] |
| Use Case    | - a description of a set of a sequence of actions, including variants<br>		- that a system performs that yields an observable result of value to a particular actor | ![[Pasted image 20260208110147.png]] |
| Subsystem   | a component that represents a major part of a system                                                                                                                | ![[Pasted image 20260208110155.png]] |
### 3.A.vi Example
1. Library Management System
```txt
┌─────────────┐          ┌──────────────┐
│   Librarian │1        *│   Book       │
├─────────────┤ manages  ├──────────────┤
│ - name      ├─────────►│ - title      │
│ - id        │          │ - author     │
├─────────────┤          │ - ISBN       │
│ + addBook() │          ├──────────────┤
│ + removeBook│          │ + issueBook()│
│ + search()  │          │ + returnBook │
└─────────────┘          └──────────────┘
       │                        │
       │                        1
       │                        │
       │                        │
┌──────▼──────┐           ┌─────▼──────┐
│   User      │           │  Account   │
├─────────────┤           ├────────────┤
│ - name      │           │ - fine     │
│ - userId    │           │ - borrowed │
├─────────────┤           ├────────────┤
│ + login()   │           │ + calcFine │
│ + logout()  │           └────────────┘
└─────────────┘
       ▲
       │
   ┌───┴───┐
   │       │
┌──▼───┐ ┌─▼─────┐
│Staff │ │Student│
└──────┘ └───────┘
```
2. Diagram Tool Example
![[Pasted image 20260213201103.png]]
## 3.3.B Object Diagram
### 3.B.i Concept
- object diagram = snapshot of system at a specific point in time.
- Shows instances of classes (objects) and their relationships (links)
- Also called instance diagram.
- represents the static design view at a moment in time.
- essentially an instance of a class diagram or the static part of an interaction diagram.
- important for
	- visualizing, specifying and documenting structural models
	- constructing static aspects of system through forward/reverse engineering
- object diagram is a collection of vertices and arcs
- expresses the static part of an interaction, consisting of the objects that corroborate, but without any of the messages passed among them.
- figure:
	- ![[Pasted image 20260214105919.png]]
### 3.B.ii Components
#### B.ii.a Objects
- Notation: Rectangle with `objectName : ClassName` underlined
- Format: `[instanceName] : [ClassName]`
- Both parts underlined
- example:
```
┌─────────────┐
│ john : Student │  ← Named object
└─────────────┘

┌─────────────┐
│ : Student   │  ← Anonymous object
└─────────────┘
```
#### B.ii.b Object State
- Attributes with Values
- Can show attribute values in a second compartment
- example:
```
┌─────────────────────┐
│ john : Student      │
├─────────────────────┤
│ name = "John Smith" │
│ id = 1001           │
│ gpa = 3.75          │
└─────────────────────┘
```
#### B.ii.c Links
- instance of an association that shows connection between objects.
- notation of solid line between objects.
- can show link name and role names.
- example:
```txt
┌───────────────┐         ┌───────────────┐
│ john : Student│         │ cs101 : Course│
└───────────────┘         └───────────────┘
        │                     │
        │ takes               │
        └─────────────────────┘
```
#### B.ii.d Multiplicity at Instance Level
- Shows actual number of connected objects at that moment.
### 3.B.iii Purpose
| Purpose       | Description                               |
| ------------- | ----------------------------------------- |
| **Visualize** | Concrete examples of system state         |
| **Validate**  | Test class diagram against real scenarios |
| **Document**  | Prototypical instances for understanding  |
| **Debug**     | Trace object relationships at runtime     |
### 3.B.iv Object vs Class Diagram
| Aspect           | Class Diagram          | Object Diagram           |
| ---------------- | ---------------------- | ------------------------ |
| **Purpose**      | Blueprint/type         | Snapshot/instance        |
| **Contents**     | Classes, associations  | Objects, links           |
| **Names**        | Plain (not underlined) | Underlined               |
| **Values**       | No attribute values    | Shows actual values      |
| **Multiplicity** | Shows possible range   | Shows actual connections |
| **Abstraction**  | High-level             | Concrete                 |
| **Time**         | Static (timeless)      | Specific moment          |
### 3.B.v Examples
1. Simple Object Diagram
```
At a specific moment in a library system:

┌─────────────────┐         ┌─────────────────┐
│ lib1 : Library  │         │ book101 : Book  │
├─────────────────┤         ├─────────────────┤
│ name = "Central"│         │ title = "UML"   │
│ address = "Main"│         │ author = "Booch"│
└─────────────────┘         └─────────────────┘
        │                           │
        │ contains                  │
        └───────────────────────────┘
```
2. Multiple Objects with Links
```
Course Registration Snapshot:

┌─────────────────┐
│ alice : Student │
├─────────────────┤
│ id = "S001"     │
│ name = "Alice"  │
└─────────────────┘
        │
        │ enrolled
        ▼
┌─────────────────┐        ┌─────────────────┐
│ math201 : Course│        │ bob : Student   │
├─────────────────┤        ├─────────────────┤
│ code = "MATH201"│        │ id = "S002"     │
│ credits = 3     │        │ name = "Bob"    │
└─────────────────┘        └─────────────────┘
        ▲                           ▲
        │ enrolled                  │ enrolled
        │                           │
┌─────────────────┐        ┌─────────────────┐
│charlie : Student│        │ : Professor     │
├─────────────────┤        ├─────────────────┤
│ id = "S003"     │        │ name = "Dr. X"  │
│ name = "Charlie"│        │ dept = "Math"   │
└─────────────────┘        └─────────────────┘
```
3. Object Diagram from ATM System
```
ATM Transaction at 10:30 AM:

┌──────────────────┐         ┌─────────────────┐
│ atm12 : ATM      │         │ acc456 : Account│
├──────────────────┤         ├─────────────────┤
│ location = "Mall"│         │ number = "456"  │
│ cash = 5000      │         │ balance = 1500  │
└──────────────────┘         └─────────────────┘
        │                           ▲
        │ uses                      │ owns
        │                           │
┌───────▼───────────────┐   ┌───────┴─────────┐
│ txn789 : Transaction  │   │ jane : Customer │
├───────────────────────┤   ├─────────────────┤
│ type = "withdrawal"   │   │ name = "Jane"   │
│ amount = 200          │   │ cardNo = "789"  │
│ time = "10:30:00"     │   └─────────────────┘
└───────────────────────┘
```
### 3.B.vi When to Use
| Scenario                             | Benefit                                         |
| ------------------------------------ | ----------------------------------------------- |
| **Testing class diagrams**           | Verify relationships work with real data        |
| **Explaining complex relationships** | Concrete examples help understanding            |
| **Reverse engineering**              | Show actual object structures from running code |
| **Documenting prototypes**           | Capture typical system states                   |
| **Debugging**                        | Visualize object connections at breakpoints     |
### 3.3.B.vii Relationship with Other Diagrams
- **Class Diagram** → defines the types
- **Object Diagram** → shows instances of those types
- **Interaction Diagrams** → object diagrams + messages (dynamic)
### 3.3.B.viii Key Points for Exam
- Object diagram = **snapshot in time**.
- Object names are **underlined**: `instance : Class`.
- Shows **attribute values**, not just types.
- Links = **instances of associations**.
- Used to **validate class diagrams** with concrete examples.
- Helpful for **testing, debugging, documentation**.
---
## 3.3.C Use Case Diagram
### 3.C.i Concept
- shows interactions between actors and use cases within a system boundary.
- Captures functional requirements from an external perspective.
- Answers: *What does the system do?*
- doesn't care about how
- represents the **use case view of the system**.
### 3.C.ii Purpose
| Purpose                           | Description                                 |
| --------------------------------- | ------------------------------------------- |
| **Capture requirements**          | Identify what users need from system        |
| **Communicate with stakeholders** | Simple, non-technical view                  |
| **Define scope**                  | System boundary separates internal/external |
| **Drive development**             | Use cases guide design and testing          |
### 3.C.iii Components
#### C.iii.a Actor
- **Definition**: Someone/something that interacts with the system (external).
- **Notation**: Stick figure or rectangle with `<<actor>>`. 
- **Location**: Outside system boundary.
- e.g. figure:
	![[Pasted image 20260208073322.png]]
- single actor may perform more than 1 functionality (use case)
- **function**:
	- input information to the system
	- receive information from the system
	- input to and out from the system
- **Finding Actors - Ask:**
	- Who uses the system?
	- Who installs/maintains the system?
	- What other systems interact with this system?
	- Who provides information to the system?
	- Who receives information from the system?
- categories

| Category              | Description                | Example                   |
| --------------------- | -------------------------- | ------------------------- |
| **Primary**           | Uses main system functions | Customer, User            |
| **Secondary**         | Administration/maintenance | Admin, Support Staff      |
| **External Hardware** | Physical devices           | Card Reader, Sensor       |
| **External System**   | Other software             | Payment Gateway, Database |
#### C.iii.b Use Case
- **Definition**: Sequence of actions producing observable result of value to actor.
- **Notation**: Ellipse with name inside.
- **Name**: Verb phrase (e.g., "Withdraw Money", "Register Student").
- **Finding Use Cases - Ask:**
	- What functions does actor want from system?
	- Does system store information? Who creates/reads/updates/deletes?
	- Does system notify actors about changes?
	- What events trigger system actions?
- e.g. 
	- figure:
	![[Pasted image 20260208073716.png | 400]]
	- description of opening a new account in the bank
		- use case: open new account
		- actors: customer, cashier, manager
		- purpose like to have a new saving account
		- description: 
			- a customer arrives in the bank to open the new account
			- customer requests for the new account form, fill the form and submit
				- along with the minimal deposit
			- at the end of complete successful process customer receives the passbook
#### C.iii.c System Boundary
- **Definition**: Rectangle separating system from external environment.
- **Inside**: Use cases.
- **Outside**: Actors.
- Shows **scope** of system.
- e.g., figure:
	![[Pasted image 20260208074117.png]]
#### C.iii.d Relationship
##### iii.d.1 Association
- Actor <-> Use case
- **Definition**: Communication between actor and use case.
- **Notation**: Solid line.
- **Direction**: Arrow optional (shows who initiates).
- example:
```
┌─────────┐       ┌─────────────┐
│ Customer│───────│ Place Order │
└─────────┘       └─────────────┘
```
##### iii.d.2 Include Relationship
- Use Case <-> Use Case
- **Definition**: One use case **always includes** behavior of another.
- **Notation**: Dashed arrow with `<<include>>`.
- **Direction**: From base to included use case.
- **Purpose**: Reuse common functionality.
- example:
```txt
┌─────────────┐       <<include>>    ┌─────────────┐
│ Place Order │─────────────────────▶│ Validate    │
└─────────────┘                      │ User        │
                                     └─────────────┘
┌─────────────┐       <<include>>    ┌─────────────┐
│ Track Order │─────────────────────▶│ Validate    │
└─────────────┘                      │ User        │
                                     └─────────────┘
```
- figure:
	- ![[Pasted image 20260208074521.png]]
##### iii.d.3 Extend Relationship
- Use Case <-> Use Case
- **Definition**: One use case **optionally** adds behavior to another.
- **Notation**: Dashed arrow with `<<extend>>`.    
- **Direction**: From extension to base use case.
- **Purpose**: Handle optional/exceptional behavior.
- example:
```
┌─────────────┐       <<extend>>    ┌─────────────┐
│ Place Order │◀────────────────────│ Apply       │
└─────────────┘                     │ Discount    │
                                    └─────────────┘
```
- figure:
	- ![[Pasted image 20260208075001.png]]
##### iii.d.4 Generalization 
- Actor <-> Actor or Use Case <-> Use Case
- **Definition**: Parent/child relationship where child inherits from parent.
- **Notation**: Solid line with hollow arrowhead pointing to parent.
###### d.4.A Actor Generalization
```
    ┌─────────┐
    │  User   │
    └─────────┘
        ▲
    ┌───┴─────┐
    │         │
┌───▼────┐ ┌──▼────┐
│Customer│ │Admin  │
└────────┘ └───────┘
```
###### d.4.B Use Case Generalization
```
    ┌─────────────┐
    │ Purchase    │
    │ Ticket      │
    └─────────────┘
        ▲
    ┌───┴────┐
    │        │
┌───▼────┐ ┌─▼──────┐
│Purchase│ │Purchase│
│Movie   │ │Concert │
│Ticket  │ │Ticket  │
└────────┘ └────────┘
```
### 3.C.iv Include vs Extend
| Aspect                        | Include (`<<include>>`)            | Extend (`<<extend>>`)       |
| ----------------------------- | ---------------------------------- | --------------------------- |
| **Optional?**                 | No (always executed)               | Yes (conditional)           |
| **Base complete without it?** | No                                 | Yes                         |
| **Direction**                 | Base → Included                    | Extension → Base            |
| **Purpose**                   | Common functionality               | Optional/exceptional        |
| **Execution**                 | Always                             | Only when condition true    |
| **Example**                   | Validate user in every transaction | Apply discount only for VIP |
### ### 3.C.v Documenting Use Cases
| Section               | Description                       |
| --------------------- | --------------------------------- |
| **Use Case Name**     | Verb phrase                       |
| **Actors**            | Who participates (initiator bold) |
| **Preconditions**     | What must be true before          |
| **Postconditions**    | What must be true after           |
| **Main Flow**         | Normal sequence of events         |
| **Alternative Flows** | Variations/exceptions             |
| **Purpose**           | Why this use case exists          |
Each use case should have a **description**:
Example:
```
Use Case: Withdraw Money
Actors: Customer (initiator), Bank System
Preconditions: 
  - ATM has cash
  - Network connection active
  - Customer has valid card
Main Flow:
  1. Customer inserts card
  2. System validates card
  3. Customer enters PIN
  4. System validates PIN
  5. Customer selects account
  6. Customer enters amount
  7. System checks balance
  8. System dispenses cash
  9. System prints receipt
  10. System returns card
Alternative Flows:
  - 2a. Invalid card → eject card
  - 4a. Wrong PIN → retry (max 3 attempts)
  - 7a. Insufficient funds → display error
Postconditions: 
  - Balance reduced by amount
  - Transaction recorded
```
### 3.C.vi Complete Example
1. ATM System
```
┌──────────────────────────────────────┐
│           ATM System                 │
│  ┌─────────────┐   ┌─────────────┐   │
│  │ Withdraw    │   │ Deposit     │   │
│  │ Money       │   │ Cash        │   │
│  └─────────────┘   └─────────────┘   │
│                                      │
│  ┌─────────────┐   ┌─────────────┐   │
│  │ Check       │   │ Transfer    │   │
│  │ Balance     │   │ Funds       │   │
│  └─────────────┘   └─────────────┘   │
│           │            │             │
│           └──────┬─────┘             │
│              <<include>>             │
│             ┌─────────────┐          │
│             │ Validate    │          │
│             │ User        │          │
│             └─────────────┘          │
└──────────────────────────────────────┘
         ▲              ▲
         │              │
    ┌────┴────┐    ┌────┴─────┐
    │ Customer│    │ Bank     │
    └─────────┘    │ System   │
                   └──────────┘
```
![[Pasted image 20260208080100.png]]
2. Library Management System
```
┌─────────────────────────────────────┐
│      Library Management System      │
│                                     │
│  ┌─────────────┐   ┌─────────────┐  │
│  │ Borrow Book │   │ Return Book │  │
│  └─────────────┘   └─────────────┘  │
│                                     │
│  ┌─────────────┐   ┌─────────────┐  │
│  │ Search      │   │ Reserve     │  │
│  │ Catalog     │   │ Book        │  │
│  └─────────────┘   └─────────────┘  │
│                                     │
│  ┌─────────────┐   ┌─────────────┐  │
│  │ Manage      │   │ Generate    │  │
│  │ Members     │   │ Reports     │  │
│  └─────────────┘   └─────────────┘  │
│         ▲              ▲            │
│         │              │            │
└─────────┼──────────────┼────────────┘
          │              │
    ┌─────┴─────┐   ┌────┴─────┐
    │ Member    │   │ Librarian│
    └───────────┘   └──────────┘
```
![[Pasted image 20260208080124.png]]
3. A coffee vending machine dispenses coffee to customers. Customers order coffee by selecting a recipe from a set of recipes. Customers pay using coins. Change is given back if any to the customer. The service staff loads ingredients into machine. The service staff can also add a recipe by indicating name of coffee, units of coffee powder, milk, sugar, water and chocolate to be added as well as the cost of coffee.
	- Actors:
		- Customer, Service staff
	- Use Cases:
		- Dispense coffee
		- Order
		- Pay coins
		- Payback
		- Load ingredients
		- Add recipe
	- Figure:
	  ![[Pasted image 20260208080507.png]]
4. Restaurant order system
	- figure:
	  ![[Pasted image 20260208080550.png]]
5. Banking Application
	- figure:
	  ![[Pasted image 20260208080733.png]]
### 3.C.vii Main Points
- Use case diagrams = **functional requirements** from **external view**.
- **3 main components**: Actors, Use Cases, System Boundary.
- **4 relationship types**: Association, Include, Extend, Generalization.
- **Include** = mandatory, **Extend** = optional/conditional.
- Use cases named with **verb phrases**.
- Actors are **external** to system.
- **System boundary** defines scope.
---
## 3.3.D Interaction Diagram
- shows how objects interact via messages to accomplish a task
- 2 types
	1. Sequence diagram -> Emphasizes time ordering
	2. Communication diagram -> Emphasizes structural relationships.
### 3.D.i Sequence Diagram
#### D.i.a Concept
- Shows **message exchange** between objects over **time**.
- Emphasizes **temporal order** (what happens when).
- Used to model dynamic behavior of use cases.
#### D.i.b Components
##### i.b.1 Object/Participants
- **Notation**: Rectangle with `objectName : ClassName` (underlined).
- Placed across top of diagram.
- system parts that interact with each other
- participants interact with each other by sending and receiving message
- object is represented as:
	- ![[Pasted image 20260208081102.png | 300]]
##### i.b.2 Lifeline
- **Notation**: Vertical dashed line below each object.
- Represents object's **existence over time**.
- most objects will be in existence for the duration of an interaction.
- So these objects are aligned at the top of diagram with their lifeline from top to bottom of diagram
-  figure:
	  ![[Pasted image 20260208081333.png]]
##### i.b.3 Activation Bar
- **Notation**: Tall thin rectangle on lifeline, can be marked by written message
	- the top of rectangle is aligned with start of the action
	- bottom is aligned with its completion
- Shows when object is **executing/active**.
- AKA **focus of control**.
- figure
	  ![[Pasted image 20260208081346.png]]
##### i.b.4 Messages
- **Notation**: Arrow from sender lifeline to receiver lifeline.
- flow in R->L or L->R direction
- used to show interaction between objects.
###### Types
| Type               | Notation                     | Description                    | Figure                                   |
| ------------------ | ---------------------------- | ------------------------------ | ---------------------------------------- |
| **Synchronous**    | →▸ (solid, filled arrow)     | Caller waits for response      | ![[Pasted image 20260208081631.png]]<br> |
| **Asynchronous**   | → (solid, open arrow)        | Caller continues execution     | <br>![[Pasted image 20260208081544.png]] |
| **Return**         | - - - > (dashed, open arrow) | Response to previous call      | ![[Pasted image 20260208081820.png]]     |
| **Self/Reflexive** | ↻                            | Object sends message to itself | ![[Pasted image 20260208081732.png]]     |
| **Create**         | → with `<<create>>`          | Creates new object             | ![[Pasted image 20260208081858.png]]     |
| **Destroy**        | → with `<<destroy>>` and X   | Terminates object              | ![[Pasted image 20260208082013.png]]     |
##### i.b.5 Time
- **Direction**: Top (start) to bottom (end).
- Represents **ordering**, not duration.
- describes the order in which interaction takes place
- time on sequence diagram starts at top of the page just below the object and then progress down the page
- figure:
	![[Pasted image 20260208082152.png]]
##### i.b.6 Combined Fragments (Control Structures)
- Condition:
	- syntax: \[expression or condition] message-label
	- the message is sent only if the condition is true
	- example: \[ user valid = "true" ] give access
- Iteration
	- syntax: * \[expression] message-label or *message-label
	- * \[expression] message-label is not standard syntax
	- message is sent many times to possibly multiple receiver objects.
	- figure:
		![[Pasted image 20260208082448.png]]
- the control mechanisms suffice only for modeling simple alternatives
##### i.b.7 Event
- created while sending/receiving message 
- when interaction takes place, events are called as built in blocks for messages and signals
- can be referred as smallest part of an interaction and event can occur at any given point in a time.
- figure:
	![[Pasted image 20260208082300.png]]
#### D.i.c Example
1. Order processing -> POS
   ![[Pasted image 20260208083551.png]]
2. Borrowing Book from library
   ![[Pasted image 20260208083616.png]]
3. ATM (Invalid Pin)
   ![[Pasted image 20260208083650.png]]
4. Login
   ![[Pasted image 20260208083703.png]]
5. Bus ticket reservation
   ![[Pasted image 20260208083724.png]]
6. Online shopping
   ![[Pasted image 20260208083743.png]]
### 3.D.ii Communication Diagram
#### D.ii.a Concept
- AKA **Collaboration Diagram**
- Shows **message exchange** between objects focusing on **structural relationships**.
- Objects can be placed anywhere (graph/network format).
	- no need to number messages
- Uses **sequence numbers** to show time ordering.
- used to show the time ordering among messages
- Notations:
  ![[Pasted image 20260208083956.png]]
#### D.ii.b Components
##### ii.b.1 Objects
- Same notation as sequence diagram: `objectName : ClassName` (underlined). 
- Connected by **links** (instances of associations).
##### ii.b.2 Links
- **Notation**: Solid line between objects.
- Instance of association
	- e.g., there is a link or path of navigation from a register to a sale, along which messages may flow, such as makePayment message
 - Represents connection path.
	 - indicates form of navigation and visibility between the objects is possible
- Can show **stereotypes** for visibility: `<<local>>`, `<<global>>`, `<<parameter>>`, `<<self>>`
	- figure:
	  ![[Pasted image 20260208085017.png]]
##### ii.b.3 Messages
- **Notation**: Arrow along link with **sequence number** and message name.
- Format: `sequenceNumber : messageName(parameters)`
- many messages may flow along a single link
	- a sequence number is added to show the sequential order of messages in the current thread of control
- figure:
	  ![[Pasted image 20260208085031.png]]
- Message to "self" or "this"
	- message can be sent from an object to itself.
		-  by a link to itself, with messages flowing along the link.
	- figure:
		![[Pasted image 20260208101452.png]]
- Conditional Messages:
	- shown by following a sequence number with a conditional clause in square brackets.
	- message is only sent if the clause evaluates to be true.
	- figure:
	  ![[Pasted image 20260208101952.png]]
- Mutually exclusive conditional patts
	- used if necessary to modify the sequence expressions with a conditional path letter.
	- first letter used is `a` by convention.
	- figure states that either 1a or 1b could execute after msg1.
	- both are sequence number 1 
	- note: subsequent nested messages are still consistently prepended with their outer message sequence.
	- figure:
	  ![[Pasted image 20260208102136.png]]
- Iteration or looping
	- if the details of the iteration clause are not important to the modeler, a simple '\*' can be used.
	- figure:
	  ![[Pasted image 20260208102221.png]]
###### Sequence Numbering Rules:
| Pattern    | Meaning                                |
| ---------- | -------------------------------------- |
| `1:`       | First message                          |
| `2:`       | Second message                         |
| `1.1:`     | First nested message within message 1  |
| `1.2:`     | Second nested message within message 1 |
| `1.1.1:`   | Deeper nesting                         |
| `2a:, 2b:` | Conditional alternatives               |
| `*1:`      | Iteration                              |
##### ii.b.4 Instances
- any message can be used to create an instance,
- convention to use a message named *create* for this purpose.
- if another message name is used, the message may be annotated with UML stereotype, like so:` <<create>>`
- the create message may include parameters, indicating the passing of initial values.
- UML property `{new}` may be optionally be added to the instance box to highlight the creation.
- figure:
	  ![[Pasted image 20260208101735.png]]
### D.ii.c Communication vs Sequence Diagram
| Aspect         | Sequence Diagram                 | Communication Diagram    |
| -------------- | -------------------------------- | ------------------------ |
| **Focus**      | Time ordering                    | Structural relationships |
| **Layout**     | Top-to-bottom                    | Graph/network (freeform) |
| **Objects**    | Along top                        | Anywhere                 |
| **Time**       | Vertical position                | Sequence numbers         |
| **Links**      | Implicit via lifelines           | Explicit lines           |
| **Complexity** | Better for simple flows          | Better for many objects  |
| **Space**      | Horizontal space for each object | Compact                  |
### D.ii.d Example:
  1. 
     ![[Pasted image 20260208084010.png]]
  2. collaboration diagram for bookRenew use case
	  ![[Pasted image 20260208084541.png]]
3. collaboration diagram for makePayment
	  ![[Pasted image 20260208084559.png]]
4. 
     ![[Pasted image 20260208102244.png]]
5. 
   ![[Pasted image 20260208102300.png]]
6. another one:
   ![[Pasted image 20260208102313.png]]
## 3.3.E Activity Diagram
### 3.E.i Concept
- **Activity diagram** = flowchart-like representation of **workflow** or **process**.
- Shows flow of control from one activity to another.
- Models **sequential and concurrent** activities.
- Used for business process modeling, use case details, algorithm flow.
### 3.E.ii Purpose
| Purpose              | Description                        |
| -------------------- | ---------------------------------- |
| **Model workflows**  | Business processes, operations     |
| **Detail use cases** | Show steps within a use case       |
| **Model algorithms** | Logic flow with decisions/loops    |
| **Show concurrency** | Parallel activities with fork/join |
### 3.E.iii Symbols
| Symbol              | Notation                             | Description                       |
| ------------------- | ------------------------------------ | --------------------------------- |
| **Initial State**   | ![[Pasted image 20260208102537.png]] | Start of activity flow            |
| **Activity/Action** | ![[Pasted image 20260208102905.png]] | Task or operation performed<br>   |
| **Flow/Edge**       | ![[Pasted image 20260208102622.png]] | Transition between activities     |
| **Decision**        | ![[Pasted image 20260208103010.png]] | Branch with conditions            |
| **Merge**           | ◇                                    | Join alternative flows            |
| **Fork**            | ![[Pasted image 20260208103304.png]] | Split into concurrent flows       |
| **Join**            | ![[Pasted image 20260208103340.png]] | Merge concurrent flows            |
| **Final State**     | ![[Pasted image 20260208103039.png]] | End of activity flow              |
| **Object Flow**     | ![[Pasted image 20260208102746.png]] | Object passing between activities |
| **Time Event**      | ![[Pasted image 20260208103438.png]] | Timer or delay                    |
| **Swimlanes**       |                                      |                                   |

1. Swimlanes
	- when modeling workflows of business processes, to partition the activity states on an activity diagram into groups, each group representing the business organization responsible for those activities
	- in UML, each group is called a swimlane, because, visually, each group is divided from its neighbor by a vertical solid line.
	- a swimlane specifies a locus of activities
	- each swimlane has a high-level responsibility for part of overall activity of an activity diagram, and each swimlane may eventually be implemented by one or more classes
	- in an activity diagram partitioned into swimlanes, every activity belongs to exactly one swimlane, but transitions may cross lanes.
### 3.E.iii Example
1. Activity diagram of borrowing a book from library
	- figure:
	  ![[Pasted image 20260208103525.png]]
2. Process order
	- description
		- Once the order is received, the activities split into two parallel sets of activities.
		- One side fills and sends the order while the other handles the billing.
		- On the Fill Order side, the method of delivery is decided conditionally.
		- Depending on the condition either the Overnight Delivery activity or the Regular Delivery activity is performed.
		- Finally the parallel activities combine to close the order.
	- Figure:
	  ![[Pasted image 20260208103853.png]]
3. Student Enrollment
	- Description
		- An applicant wants to enroll in the university.
		- The applicant hands a filled out copy of Enrollment Form.
		- The registrar inspects the forms.
		- The registrar determines that the forms have been filled out properly.
		- The registrar informs student to attend in university overview presentation.
		- The registrar helps the student to enroll in seminars
		- The registrar asks the student to pay for the initial tuition.
	- figure:
	  ![[Pasted image 20260208104004.png]]
#### 3.E.iv Activity vs Flowchart
| Aspect           | Activity Diagram      | Flowchart               |
| ---------------- | --------------------- | ----------------------- |
| **Scope**        | System/process level  | Algorithm/program level |
| **Concurrency**  | Supported (fork/join) | Limited                 |
| **Swimlanes**    | Yes (responsibility)  | No                      |
| **Object Flow**  | Yes                   | No                      |
| **UML Standard** | Yes                   | No                      |
## 3.3.F State Diagram
### 3.F.i Concept
- AKA **state machine** / **state chart** diagram
- Models the **behavior of a single object**, over its lifetime
- Show **states** an object can be and transitions between states in response to events.
- Particularly useful for **reactive objects** (objects that respond to events).
### 3.F.ii Purpose
| Purpose                    | Description                                          |
| -------------------------- | ---------------------------------------------------- |
| **Model object lifecycle** | Show all possible states of an object                |
| **Event-driven behavior**  | How object responds to events based on current state |
| **Complex behavior**       | Objects with many states and transitions             |
| **Real-time systems**      | Controllers, devices, protocols                      |
### 3.F.iii Components
1. States
	- Condition or situation during object's life when it satisfies some condition, performs some activity, or waits for an event.
	- state is denoted by a round cornered rectangle with the name of the state written inside it.
	- Figure:
		- ![[Pasted image 20260213202523.png]]
2. Initial State
	- Starting point of state machine.
	- Only one initial state.
3. Final State
	- End of object's lifetime.
	- May have multiple final states.
	- Figure:
		- ![[Pasted image 20260213202538.png]]
4. Transitions
	- Movement from one state to another in response to an event
	- Notation of arrow from source to target state.
	- a transition may have a trigger, a guard or an effect, as below figure:
		- ![[Pasted image 20260213202702.png]]
	- Event/Trigger
		- what causes transition
		- could be signal, event, change in some condition, or passage of time
		- e.g., `insertCard`
	- Guard
		- condition that must be true for the trigger to cause the transition
		- e.g., `[cardValid`
	- Action/Effect
		- what happen during transition.
		- e.g., `/readPIN`
5. State Actions
	- activities that occur within a state
		- entry: 
			- syntax: `entry / action`
			- On entering the state
		- exit:
			- syntax: `exit / action`
			- on leaving state
		- do:
			- syntax: `do / activity`
			- while in state (on going)
		- defer: 
			- syntax: `defer / event`
			- event that remain in the event pool ready for processing when the object transitions to another state.
	- For state name 'At work'
	- Actions:
		- Entry Activity: entry/unlock
		- Do activity: do/prepare materials
		- Defer: telephone rings/defer
		- Exit: exit / lock door
6. Self-Transitions
	- transition that returns to the same state
	- entry/exit actions execute again
		- ![[Pasted image 20260213203642.png]]
7. Compound States or Sub States
	- state containing nested states.
	- shows hierarchy and refinement
		- ![[Pasted image 20260213203342.png]]
	- the alternative way to show the same information is as follows:
		- ![[Pasted image 20260213203414.png]]
		- the notation in this figure indicates that the details of the Check PIN sub-machine are shown in separate diagram.
8. Terminate Pseudo-State
	- indicates object lifetime ends immediately
	- no exit actions executed.
		- ![[Pasted image 20260213203745.png]]
9. History States
	- remembers last active substate within a compound state.
	- Shallow History (H): remembers only top level substate
	- Deep History (H*): remembers nested substates as well.
		- ![[Pasted image 20260213203929.png]]
	- the example is a state machine belonging to a washing machine.
	- in the state machine, when a washing machine is running, it will progress from washing through rinsing to spinning
	- if there is a power cut, the washing machine will stop running and will go to 'power off' state
	- when power is restored, the running state is entered at the 'History State' symbol meaning that it should resume where it last left off.
10. Concurrent state machine
	- state divided into regions executing in parallel
	- uses fork/join notation
		- ![[Pasted image 20260213205139.png]]
	- notice the use of fork and join pseudo-states, rather than choice and merge pseud-states.
	- these symbols are used to synchronize the concurrent threads.
### 3.F.iii SMD Examples
1. Recruitment process
   - ![[Pasted image 20260213205032.png]]
1.  sub states or compounded states example.
	- ![[Pasted image 20260213205342.png]]
2. atm pin verification
	- ![[Pasted image 20260213205409.png]]
3. Statechart diagram for Digital Clock
	- ![[Pasted image 20260213205452.png]]
4. State diagram of a candy vending machine
	- ![[Pasted image 20260213205517.png]]
### State Diagram vs Activity Diagram

| Aspect          | State Diagram          | Activity Diagram      |
| --------------- | ---------------------- | --------------------- |
| **Focus**       | Single object's states | Process/workflow      |
| **Events**      | Triggers transitions   | Flow of control       |
| **States**      | Explicitly named       | Implicit (activities) |
| **Concurrency** | Concurrent states      | Fork/join             |
| **Best for**    | Reactive objects       | Business processes    |

---
## 3.3.G Component Diagram
### 3.G.i Concept
- **Component diagram** = shows **physical structure** of code/components in a system.
- Models **implementation view** of the system.
- Represents **components**, **interfaces**, and **relationships** between them.
- Focuses on **binary replaceable parts** of a system.
### 3.G.ii Purpose
| Purpose                           | Description                    |
| --------------------------------- | ------------------------------ |
| **Model source code**             | File structure, dependencies   |
| **Model executable releases**     | DLLs, EXEs, runtime components |
| **Model physical databases**      | Tables, schemas                |
| **Model component-based systems** | COM+, CORBA, EJB, etc.         |
### 3.G.iii Components
1. Component
	- Physical, replaceable part of system that conforms to and provides interfaces.
	- Notation of rectangle with two small protruding rectangles (tabs) on left side.
	- Characteristics of Components:
		- Physical (lives in world of bits)
		- Replaceable (collaborates with others)
		- Provides/requires interfaces
2. Component Names
	- each component has unique name (textual string)
	- Simple name: Just the name (e.g., `Login.dll`)
	- Path name: Package + name (e.g., `Security::Login.dll`)
	- a component is typically drawn showing only its name, as in figure below.
	- just with classes, we may draw components adorned with tagged values or with additional compartments to expose their details, as wee see in the figure.
	- figure:
		- ![[Pasted image 20260213212329.png]]
3. Interfaces
	- Are model elements that define sets of operations that other model elements
		- operations  used to specify a service of class or component
	- Components interact through interfaces:
		- Provided Interface:
			- Services component offers
			- Notation of Circle (ball) on component
		- Required Interface
			- Services component needs
			- Notation of Half-Circle (socket) on component
	- As figure below indicates, we can show the relationship between a component and its interfaces in one of two ways.
		- ![[Pasted image 20260213213517.png]]
4. Relationships

|Relationship|Notation|Description|
|---|---|---|
|**Dependency**|- - - →|One component uses another|
|**Realization**|- - - ▷|Component implements interface|
|**Association**|———|Structural connection|
5. Components vs Classes
![[Pasted image 20260213213108.png]]

| Aspect             | Component               | Class                           |
| ------------------ | ----------------------- | ------------------------------- |
| **Level**          | Physical                | Logical                         |
| **Location**       | Lives on nodes          | Abstract (no physical location) |
| **Replaceability** | Binary replaceable      | Source code replaceable         |
| **Interfaces**     | Only through interfaces | Direct operations               |
| **Implementation** | Implements classes      | Implemented by components       |
5. Kinds of Components

| Type                        | Description             | Examples                       |
| --------------------------- | ----------------------- | ------------------------------ |
| **Deployment Components**   | Executable system parts | DLLs, EXEs, JARs               |
| **Work Product Components** | Development artifacts   | Source files, data files       |
| **Execution Components**    | Created at runtime      | COM+ objects, Enterprise Beans |
6. Binary Replaceability
	- We can create a system out of components and then evolve that system by adding new components and replacing old ones, without rebuilding the system.
	- Interfaces are the key to making this happen. 
	- When we specify an interface, we can drop into the executable system any component that conforms to or provides that interface.
	- We can extend the system by making the components provide new services through other interfaces, which, in turn, other components can discover and use.
	- A component is a physical and replaceable part of a system that conforms to and provide the realization of a set of interfaces.
	- A component may be reused across many system. 
	- Therefore, a component is a fundamental building block on which systems can be designed and composed.
	- This definition is a recursive, a system at one level of abstraction may simply be a component at a higher level of abstraction.
### 3.G.iv Common Uses of Component Diagram
#### G.iii.a Modeling Source Code
- Track file dependencies
- Manage builds
- Version control
#### G.iii.b Modeling Executable Releases
- Show runtime deployment units
- Manage dependencies between binaries
- Plan updates and patches
#### G.iii.c Modeling Physical Databases
- Tables as components
- Stored procedures
- Database schemas
#### G.iii.d Modeling Adaptable Systems
- Plug-in architectures
- Dynamic loading
- Component replacement
### 3.3.G.v Component Diagram vs Deployment Diagram
| Aspect            | Component Diagram          | Deployment Diagram         |
| ----------------- | -------------------------- | -------------------------- |
| **Focus**         | Software components        | Hardware nodes             |
| **Shows**         | Code structure, interfaces | Physical deployment        |
| **Elements**      | Components, interfaces     | Nodes, devices             |
| **Relationships** | Dependencies, realizations | Associations, dependencies |
| **Level**         | Implementation view        | Deployment view            |
### 3.G.vi Modeling Examples
1. source code:
	- figure:
		- ![[Pasted image 20260214100901.png]]
	- this header file (signal.h) is used by two other files (interp.cpp and signal.cpp), both of which are bodies.
	- one of these files (interp.cpp) has a compilation depemdency to another header (irq/h); in turn, device.cpp has a compilation dependency to interp.cpp
	- given this component diagram, its easy to trace the impact of changes.
	- for this example, changing the source code file signal.h will require the recompilation of three other files: signal.cpp, interp.cpp and trasitively, device.cpp
2. Adaptable systems
	- If we want to show the details of each database, we can render them in their canonical form, a component stereotyped as a database.
3. Complete E-Commerce System
```
┌──────────────────────────────────────────┐
│            Client Tier                   │
│  ┌─────────────────┐                     │
│  │ <<component>>   │                     │
│  │ Browser         │                     │
│  │ (HTML/JS/CSS)   │                     │
│  └─────────────────┘                     │
└──────────────────────────────────────────┘
                    │ HTTP/HTTPS
                    ▼
┌──────────────────────────────────────────┐
│            Web Tier                      │
│  ┌─────────────────┐                     │
│  │ <<component>>   │                     │
│  │ WebServer       │                     │
│  │ (Apache/Tomcat) │                     │
│  └─────────────────┘                     │
└──────────────────────────────────────────┘
                    │
                    ▼
┌──────────────────────────────────────────┐
│          Business Tier                   │
│  ┌─────────────────┐ ┌─────────────────┐ │
│  │ <<component>>   │ │ <<component>>   │ │
│  │ OrderService    │ │ PaymentService  │ │
│  │ (EJB)           │ │ (EJB)           │ │
│  └─────────────────┘ └─────────────────┘ │
│  ┌─────────────────┐ ┌─────────────────┐ │
│  │ <<component>>   │ │ <<component>>   │ │
│  │ InventoryService│ │ UserService     │ │
│  │ (EJB)           │ │ (EJB)           │ │
│  └─────────────────┘ └─────────────────┘ │
└──────────────────────────────────────────┘
                    │ JDBC/JPA
                    ▼
┌──────────────────────────────────────────┐
│          Data Tier                       │
│  ┌─────────────────┐                     │
│  │ <<component>>   │                     │
│  │ Database        │                     │
│  │ (Oracle/MySQL)  │                     │
│  └─────────────────┘                     │
└──────────────────────────────────────────┘
```

## 3.3.H Deployment Diagram
### 3.H.i Concept
- **Deployment diagram** = shows the **physical architecture** of hardware and software in a system.
- Models the **deployment view** of a system.
- Represents **nodes**, **components**, and their **relationships**.
- Shows **where** software components run on hardware.
###  3.H.ii Purpose
| Purpose                            | Description                                  |
| ---------------------------------- | -------------------------------------------- |
| **Model hardware topology**        | Processors, devices, connections             |
| **Show component deployment**      | Which software runs on which hardware        |
| **Plan system distribution**       | Client/server, embedded, distributed systems |
| **Analyze performance**            | Network bandwidth, processing load           |
| **Document physical architecture** | Installation, configuration                  |
### 3.H.iii Components
1. **Node**
	- a physical element that exists at run time, represents a computation resource
	- generally has some memory and processing capability
	- types:
		- Processor:
			- Has processing capability
			- e.g., Server, PC, embedded CPU
		- Device:
			- Hardware with no processing
			- e.g., Printer, sensor, modem
	- used to model the topology of the hardware on which our system executes.
	- graphically a node is rendered as a cube.
2. **Names**
	- is a textual string.
	- must be unique within its enclosing package to distinguish other nodes.
	- types:
		- Simple Name:
			- Just the name
			- e.g., `WebServer`
		- Path Name:
			- Package + name
			- e.g., `Production::Webserver`
	- Figure:
		- ![[Pasted image 20260214104447.png]]
	- just as with classes, we may draw nodes adorned with tagged values or with additional compartments to expose their details.
3. **Component on Nodes**
	- Components are placed inside nodes where they execute
```
┌─────────────────────────┐
│      WebServer          │
│  ┌─────────────────┐    │
│  │  <<component>>  │    │
│  │  WebApp.war     │    │
│  └─────────────────┘    │
│  ┌─────────────────┐    │
│  │  <<component>>  │    │
│  │  AuthModule.dll │    │
│  └─────────────────┘    │
└─────────────────────────┘
```
4. Communication Paths
	- Definition: Association between nodes showing communication
	- Notation of solid line between nodes
	- Can show protocol or network type.
```
┌─────────────┐     HTTP      ┌─────────────┐
│ WebServer   │───────────────│ ClientPC    │
└─────────────┘               └─────────────┘
```
### 3.H.iv Common uses
1. **To model embedded systems**
	- Hardware + software integration
	- Sensor, actuators, contropllers
	- Real-time constraints
		- example
			- ![[Pasted image 20260214105430.png]]
		- we'll find one node (pentium motherboard) stereotyped as a processor. surrounding this node are eight devices, each stereotyped as a device and rendered with an icon thaht offers a clear visual cue to its real world equivalent.
2. **Model client/server systems**
	- Client nodes, server nodes
	- network connections
	- load balancing, failover
		- example:
			- ![[Pasted image 20260214105525.png]]
3. **Model fully distributed systems**
	- Multiple server tiers
	- Geographic distribution
	- Replication, caching
		- example:
			- ![[Pasted image 20260214105545.png]]
4. **Model System Topology**
	- Network Architecture
	- Hardware specifications
	- Communication Protocols
### 3.H.v Examples
#### H.iv.a Simple Client-Server System
```
┌─────────────────────────┐      ┌─────────────────────────┐
│      ClientPC           │      │      DatabaseServer     │
│  ┌─────────────────┐    │      │  ┌─────────────────┐    │
│  │  <<component>>  │    │      │  │  <<component>>  │    │
│  │  Browser        │    │      │  │  Oracle 19c     │    │
│  └─────────────────┘    │      │  └─────────────────┘    │
│                         │      │                         │
│  ┌─────────────────┐    │      │  ┌─────────────────┐    │
│  │  <<component>>  │    │      │  │  <<component>>  │    │
│  │  VPN Client     │    │      │  │  Backup Agent   │    │
│  └─────────────────┘    │      │  └─────────────────┘    │
└─────────────────────────┘      └─────────────────────────┘
            │                                    │
            │          HTTPS (Internet)          │
            └────────────────────────────────────┘
```
#### H.iv.b Three-Tier Architecture
```
┌─────────────────┐
│  Client Tier    │
│  ┌───────────┐  │
│  │ PC        │  │
│  │ Browser   │  │
│  └───────────┘  │
└────────┬────────┘
         │ HTTPS
         ▼
┌─────────────────┐
│  Web Tier       │
│  ┌───────────┐  │
│  │ WebServer │  │
│  │ Tomcat    │  │
│  │ WebApp.war│  │
│  └───────────┘  │
└────────┬────────┘
         │ RMI/IIOP
         ▼
┌─────────────────┐
│  Business Tier  │
│  ┌───────────┐  │
│  │ AppServer │  │
│  │ JBoss/EJB │  │
│  │ Orders.jar│  │
│  │ Payment.jar│ │
│  └───────────┘  │
└────────┬────────┘
         │ JDBC
         ▼
┌─────────────────┐
│  Data Tier      │
│  ┌───────────┐  │
│  │ Database  │  │
│  │ Server    │  │
│  │ MySQL     │  │
│  └───────────┘  │
└─────────────────┘
```
#### H.iv.c: Embedded System
```
┌───────────────────────────────────────┐
│  Factory Floor                        │
│                                       │
│  ┌─────────────────┐                  │
│  │  Control Room   │                  │
│  │  ┌───────────┐  │                  │
│  │  │ HMI PC    │  │                  │
│  │  │ SCADA     │  │                  │
│  │  └───────────┘  │                  │
│  └────────┬────────┘                  │
│           │ Ethernet                  │
│           ▼                           │
│  ┌─────────────────┐                  │
│  │  PLC Rack       │                  │
│  │  ┌───────────┐  │  ┌───────────┐   │
│  │  │ CPU Module│  │──│ I/O Module│   │
│  │  │ Control   │  │  │ Sensors   │   │
│  │  │ Logic     │  │  └───────────┘   │
│  │  └───────────┘  │                  │
│  │  ┌───────────┐  │  ┌───────────┐   │
│  │  │ Comm      │  │──│ Motor     │   │
│  │  │ Module    │  │  │ Driver    │   │
│  │  └───────────┘  │  └───────────┘   │
│  └─────────────────┘                  │
│                                       │
│  ┌─────────────────┐                  │
│  │  Sensor Network │                  │
│  │  ┌───────────┐  │  ┌───────────┐   │
│  │  │ Temp      │  │  │ Pressure  │   │
│  │  │ Sensor    │  │  │ Sensor    │   │
│  │  └───────────┘  │  └───────────┘   │
│  │  ┌───────────┐  │                  │
│  │  │ Proximity │  │                  │
│  │  │ Sensor    │  │                  │
│  │  └───────────┘  │                  │
│  └─────────────────┘                  │
└───────────────────────────────────────┘
```
#### H.iv.d Mobile/Cloud Application
```
┌──────────────────┐
│  Mobile Device   │
│  ┌────────────┐  │
│  │ iOS/Android│  │
│  │ Mobile App │  │
│  │ Offline    │  │
│  │ Cache      │  │
│  └────────────┘  │
└────────┬─────────┘
         │ 4G/WiFi
         ▼
┌─────────────────┐
│  CDN            │
│  ┌───────────┐  │
│  │ Edge      │  │
│  │ Server    │  │
│  │ Static    │  │
│  │ Content   │  │
│  └───────────┘  │
└────────┬────────┘
         │
         ▼
┌─────────────────────────────────────┐
│  Cloud Provider (AWS/Azure)         │
│  ┌─────────────────────────────┐    │
│  │ Load Balancer               │    │
│  └─────────────┬───────────────┘    │
│                │                    │
│  ┌─────────────┴───────────────┐    │
│  │ Web Server Farm             │    │
│  │ ┌─────────┐ ┌─────────┐     │    │
│  │ │ EC2-1   │ │ EC2-2   │     │    │
│  │ │ Node.js │ │ Node.js │     │    │
│  │ └─────────┘ └─────────┘     │    │
│  └─────────────┬───────────────┘    │
│                │                    │
│  ┌─────────────┴───────────────┐    │
│  │ Database Cluster            │    │
│  │ ┌─────────┐ ┌─────────┐     │    │
│  │ │ Primary │ │ Replica │     │    │
│  │ │ MongoDB │ │ MongoDB │     │    │
│  │ └─────────┘ └─────────┘     │    │
│  └─────────────────────────────┘    │
│                                     │
│  ┌─────────────────────────────┐    │
│  │ Storage                     │    │
│  │ S3 Bucket / Images          │    │
│  └─────────────────────────────┘    │
└─────────────────────────────────────┘
```
#### H.iv.e With Node Stereotypes
```
┌─────────────────────────┐
│ <<processor>>           │
│   ApplicationServer     │
│   {OS = Linux}          │
│   {vendor = Dell}       │
│   {cores = 16}          │
│   {ram = 64GB}          │
│                         │
│   ┌─────────────────┐   │
│   │  app.war        │   │
│   └─────────────────┘   │
└─────────────────────────┘
            │
            │ Gigabit Ethernet
            │
┌─────────────────────────┐
│ <<device>>              │
│   NetworkAttachedStorage│
│   {capacity = 10TB}     │
│   {protocol = NFS}      │
│                         │
│   ┌─────────────────┐   │
│   │  backup.dat     │   │
│   └─────────────────┘   │
└─────────────────────────┘
```
#### Example 6: With Communication Protocols
```
┌─────────────┐              ┌─────────────┐
│  WebServer  │  <<HTTP>>    │  Client     │
│  Port: 80   │──────────────│  Browser    │
│  HTTPS: 443 │              └─────────────┘
└─────────────┘
      │
      │ <<RMI>> 1099
      │
      ▼
┌─────────────┐    <<JDBC>> 3306     ┌─────────────┐
│ AppServer   │──────────────────────│ Database    │
│ Port: 8080  │                      │ Port: 3306  │
└─────────────┘                      └─────────────┘
      │
      │ <<JMS>>
      │
      ▼
┌─────────────┐
│ MessageQueue│
│ ActiveMQ    │
└─────────────┘
```
### 3.H.vi Component vs Deployment
|Aspect|Component Diagram|Deployment Diagram|
|---|---|---|
|**Focus**|Software components|Hardware nodes|
|**Elements**|Components, interfaces|Nodes, devices, components on nodes|
|**Shows**|Code structure, dependencies|Physical deployment|
|**Relationships**|Dependencies, realizations|Communication paths|
|**Level**|Implementation view|Deployment view|
|**Question answered**|_What are the parts?_|_Where do they run?_|
## 3.3.I Summary
|Diagram|View|Focus|
|---|---|---|
|**Class Diagram**|Logical|Static structure|
|**Object Diagram**|Logical|Instances at a moment|
|**Use Case Diagram**|Use Case|Functional requirements|
|**Sequence Diagram**|Dynamic|Time-ordered messages|
|**Communication Diagram**|Dynamic|Message + structure|
|**Activity Diagram**|Dynamic|Workflow/process|
|**State Diagram**|Dynamic|Object lifecycle|
|**Component Diagram**|Implementation|Physical code structure|
|**Deployment Diagram**|Deployment|Hardware topology|
# 3.4 Advanced Classes
### 3.4.A Overview
- Beyond basic class notation (name, attributes, operations), UML provides **advanced class features** for precise modeling.
- Used when standard class notation isn't sufficient for complex scenarios.
### 3.4.B Advanced Class Features
#### 1. **Class Multiplicity**
- **Definition**: Number of instances a class may have.
- **Notation**: Multiplicity expression in **upper-right corner** of class rectangle.
- **Purpose**: Specify cardinality constraints at class level.
```
┌──────────────────┐ 1
│ NetworkController│
├──────────────────┤
│ - instanceId     │
│ + getInstance()  │
└──────────────────┘
┌─────────────────┐ 0..3
│   ControlRod    │
├─────────────────┤
│ - position      │
│ + raise()       │
└─────────────────┘
```

|Multiplicity|Meaning|
|---|---|
|`1`|Exactly one (singleton)|
|`0..1`|Zero or one|
|`*`|Many (unbounded)|
|`1..*`|One or more|
|`3`|Exactly three|
|`2..5`|Two to five|
#### 2. **Abstract Class**
- **Definition**: Class that **cannot be instantiated**; used only as parent.
- **Notation**: Class name in _italics_ OR `{abstract}` below name.
- **Purpose**: Provide common interface/behavior for subclasses.
```
┌─────────────────┐
│   *Shape*       │  ← italics
├─────────────────┤
│ + area() *      │  ← abstract method in italics
│ + draw() *      │
└─────────────────┘
        ▲
        │
 ┌──────┴─────────┐
 │                │
┌▼─────┐       ┌──▼───┐
│Circle│       │Square│
└──────┘       └──────┘
```

#### 3. **Root, Leaf, and Polymorphic Elements**
| Type                      | Notation  | Meaning                               |
| ------------------------- | --------- | ------------------------------------- |
| **Root Class**            | `{root}`  | No ancestors (top of hierarchy)       |
| **Leaf Class**            | `{leaf}`  | No descendants (cannot be subclassed) |
| **Polymorphic Operation** | _italics_ | Can be overridden in subclasses       |
```
┌─────────────────┐ {root}
│   Vehicle       │
├─────────────────┤
│ + move() *      │ ← polymorphic
└─────────────────┘
        ▲
        │
 ┌──────┴────────┐
 │               │
┌▼────┐       ┌──▼──┐ {leaf}
│ Car │       │ Bike│ ← cannot be subclassed
└─────┘       └─────┘
```
#### 4. **Active Class**
- **Definition**: Class whose instances **own a thread of control** and can initiate activities.
- **Notation**: Thick border on class rectangle.
- **Purpose**: Model concurrent/autonomous objects.
```
┌═════════════┐
║   Sensor    ║  ← thick border
║   Monitor   ║
├═════════════┤
║ - threshold ║
├═════════════┤
║ + run()     ║
║ + alert()   ║
└═════════════┘
```
#### 5. **Parameterized Class (Template)
- **Definition**: Class with **type parameters** for generic programming.
- **Notation**: Dotted rectangle in upper-right corner with parameters.
- **Purpose**: Reusable class definitions.
```
┌─────────────────┐
│     List<T>     │
├─────────────────┤
│ - items: T[]    │
├─────────────────┤
│ + add(item: T)  │
│ + get(index): T │
└─────────────────┘
// Instantiated as:
┌─────────────────┐
│ List<Student>   │
└─────────────────┘
```
#### 6. **Utility Class**
- **Definition**: Class with only **class-scoped features** (static methods/attributes).
- **Notation**: `«utility»` stereotype.
- **Purpose**: Group related functions; no instances.
```
┌─────────────────┐
│ «utility»       │
│ MathUtils       │
├─────────────────┤
│ + PI: double    │
├─────────────────┤
│ + sin(x): double│
│ + cos(x): double│
└─────────────────┘
```
#### 7. **Metaclass**
- **Definition**: Class whose instances are **classes**.
- **Notation**: `«metaclass»` stereotype.
- **Purpose**: Model class-of-class relationships (e.g., in modeling tools).
```
┌─────────────────┐
│ «metaclass»     │
│    Class        │
├─────────────────┤
│ - name: String  │
│ - attributes    │
└─────────────────┘
        │
        │ instanceOf
        ▼
┌─────────────────┐
│   Student       │ ← this is a class (instance of Class)
└─────────────────┘
```
### 3.4.C Advanced Attribute Features
#### 1. **Attribute Multiplicity**
- **Definition**: How many values an attribute can hold.
- **Notation**: `[min..max]` after type.
```
┌─────────────────┐
│    Student      │
├─────────────────┤
│ - name: String[1]    ← exactly one
│ - phone: String[0..*] ← zero or more
│ - grades: int[5]      ← exactly five
└─────────────────┘
```
#### 2. **Derived Attribute**
- **Definition**: Attribute whose value can be **computed** from others.
- **Notation**: `/` before attribute name.
```
┌─────────────────┐
│    Person       │
├─────────────────┤
│ - birthDate: Date
│ - /age: int     ← computed from birthDate
└─────────────────┘
```
#### 3. **Attribute Properties**
| Property     | Meaning                            | Notation     |
| ------------ | ---------------------------------- | ------------ |
| **readOnly** | Cannot change after initialization | `{readOnly}` |
| **unique**   | Value must be unique               | `{unique}`   |
| **ordered**  | Elements have order                | `{ordered}`  |
| **bag**      | Unordered collection               | `{bag}`      |
```
┌─────────────────┐
│    Course       │
├─────────────────┤
│ - courseId: String {unique, readOnly}
│ - students: Student[*] {ordered}
│ - tags: String[*] {bag}
└─────────────────┘
```
### 3.4.D Advanced Operation Features
#### 1. **Query Operation**
- **Definition**: Operation that **doesn't modify** the object state.
- **Notation**: `{query}` property.
```
┌─────────────────┐
│    BankAccount  │
├─────────────────┤
│ - balance: Money│
├─────────────────┤
│ + getBalance(): Money {query}
│ + calculateInterest(): Money {query}
│ + deposit(amount: Money)  ← not a query
└─────────────────┘
```
#### 2. **Operation Concurrency**
| Stereotype     | Meaning                             |
| -------------- | ----------------------------------- |
| `{sequential}` | Must coordinate access              |
| `{guarded}`    | Multiple calls safe                 |
| `{concurrent}` | Multiple simultaneous calls allowed |
```
┌─────────────────┐
│    Printer      │
├─────────────────┤
│ + print(doc) {guarded}
│ + cancel() {sequential}
└─────────────────┘
```
### 3.4.E Visibility Beyond Basic
| Visibility    | Symbol | Scope        | Meaning                             |
| ------------- | ------ | ------------ | ----------------------------------- |
| **Public**    | `+`    | Any          | Accessible to all                   |
| **Protected** | `#`    | Subclasses   | Accessible in inheritance hierarchy |
| **Private**   | `-`    | Same class   | No external access                  |
| **Package**   | `~`    | Same package | Accessible within package           |
```
┌─────────────────┐
│    Employee     │
├─────────────────┤
│ + name: String  │  ← public
│ # ssn: String   │  ← protected
│ - salary: Money │  ← private
│ ~ dept: String  │  ← package
├─────────────────┤
│ + work()        │
│ # getSSN()      │
│ - calculateTax()│
└─────────────────┘
```
### 3.4.F Advanced Class Relationships Summary
| Feature                 | Purpose               | Example                       |
| ----------------------- | --------------------- | ----------------------------- |
| **Class Multiplicity**  | Limit instances       | Singleton (1), ControlRod (3) |
| **Abstract Class**      | Common interface      | Shape                         |
| **Root/Leaf**           | Hierarchy constraints | Vehicle {root}, Bike {leaf}   |
| **Active Class**        | Concurrent objects    | SensorMonitor                 |
| **Parameterized Class** | Generics/templates    | List<T>                       |
| **Utility Class**       | Static methods        | MathUtils                     |
| **Metaclass**           | Class-of-classes      | Class (in modeling tools)     |
# 3.5 Advanced Relationship
### 3.5.A Overview
- Beyond basic relationships (dependency, association, generalization), UML provides **advanced relationships** for more precise modeling.
- Used when standard relationships don't capture specific semantics.
### 3.5.B Types of Advanced Relationships

#### 1. **Derived Association**
- **Definition**: Association that can be **computed** from other associations.
- **Notation**: `/` (slash) before association name.
- **Purpose**: Show redundancy explicitly; avoid duplication.
```
┌─────────┐          ┌─────────┐
│ Person  │          │ Company │
└─────────┘          └─────────┘
     │                     │
     │ /employer           │
     │ (derived from       │
     │  worksFor)          │
     └─────────────────────┘
     
     ┌─────────┐
     │ WorksFor│
     └─────────┘
```
#### 2. **Qualified Association**
- **Definition**: Association with a **qualifier** that selects among multiple target objects.
- **Notation**: Small rectangle on association end (qualifier).
- **Purpose**: Reduce multiplicity; act like dictionary/hash lookup.
```
┌─────────┐   ┌─────┐   ┌─────────┐
│  Bank   │   │account│   │ Account │
│         │◀──│number │──▶│         │
└─────────┘   └─────┘   └─────────┘
   (1)         (qualifier)   (0..1)
   
Without qualifier: Bank (1) ──── (0..*) Account
With qualifier:    Bank (1) ─[accNo]─ (0..1) Account
```
#### 3. **Association Class**
- **Definition**: Association that has **attributes/operations** of its own.
- **Notation**: Class attached to association with dashed line.
- **Purpose**: Model properties of the relationship itself    
```
┌─────────┐                    ┌─────────┐
│ Person  │────────────────────│ Company │
└─────────┘                    └─────────┘
               │
               │
         ┌─────▼─────┐
         │ Employment│
         ├───────────┤
         │ startDate │
         │ salary    │
         │ jobTitle  │
         └───────────┘
```
#### 4. **Composition with Shared vs Exclusive Ownership**
- **Shared Composition**: Part can belong to multiple wholes (rare).
- **Exclusive Composition**: Part belongs to exactly one whole (standard).
```
┌─────────┐          ┌─────────┐
│ Window  │◆─────────│ Frame   │ (exclusive - filled diamond)
└─────────┘          └─────────┘
┌─────────┐          ┌─────────┐
│ Room    │◇─────────│ Wall    │ (shared - hollow diamond)
└─────────┘          └─────────┘
```
#### 5. **Powertype**
- **Definition**: Class whose instances are **subclasses** of another class.
- **Notation**: Dependency with `<<powertype>>` stereotype.
```
┌─────────┐     <<powertype>>   ┌─────────┐
│ Animal  │────────────────────▶│ Species │
└─────────┘                      └─────────┘
     ▲                                ▲
     │                                │
     │ instances are                  │ instances are
     │ subclasses                     │ classification
┌────┴────┐                          │ criteria
│Mammal   │───────────────────────────┘
│Bird     │
│Reptile  │
└─────────┘
```
#### 6. **Interface Realization with Ball/Socket**
- More precise than basic realization:
    - **Provided Interface**: Ball (○) - services offered
    - **Required Interface**: Socket (⊂) - services needed
    - **Assembly Connector**: Ball connects to socket
```
┌────────────┐    ○─⊂      ┌────────────┐
│ ComponentA │─────────────│ ComponentB │
│ (requires) │  (provides) │            │
└────────────┘             └────────────┘
```
### 3.5.C Advanced Relationship Summary
| Relationship          | Notation                   | Purpose                          | Example                              |
| --------------------- | -------------------------- | -------------------------------- | ------------------------------------ |
| Derived Association   | `/name`                    | Computed value                   | `age` from `birthDate`               |
| Qualified Association | [qualifier]                | Reduce multiplicity              | Account number selects account       |
| Association Class     | Class + dashed line        | Relationship with properties     | Employment (salary, startDate)       |
| Composition Types     | ◆ (exclusive) / ◇ (shared) | Ownership semantics              | Window-Frame vs Room-Wall            |
| Powertype             | `<<powertype>>`            | Type whose instances are classes | Species classifies Animal subclasses |
| Interface Assembly    | ○─⊂                        | Component wiring                 | Plug-in architecture                 |
### 3.5.D When to Use Advanced Relationships
| Scenario                      | Advanced Relationship |
| ----------------------------- | --------------------- |
| Relationship has its own data | Association Class     |
| Need to reduce multiplicity   | Qualified Association |
| Show redundancy explicitly    | Derived Association   |
| Part sharing semantics        | Shared Composition    |
| Classifies subclasses         | Powertype             |
| Component-based wiring        | Interface Assembly    |
# 3.6 Interface
### 3.6.A Concept
- **Interface** = collection of **operations** that specify a **service** of a class or component.
- **No implementation**, only declaration.
- Defines a **contract** between provider and consumer.
- Supports **information hiding** and **loose coupling**.
### 3.6.B Interface Notation
#### 1. **Class/Expanded Notation**
```
┌─────────────────┐
│ «interface»     │
│    IOrder       │
├─────────────────┤
│ + placeOrder()  │
│ + cancelOrder() │
│ + trackOrder()  │
└─────────────────┘
```
#### 2. **Ball/Lollipop Notation (Provided Interface)**
 ```
    ┌─────────┐
    │ Order   │───○ IOrder
    │ Service │
    └─────────┘
 ```
- Ball (○) = provided interface (services offered)
#### 3. **Socket Notation (Required Interface)**
    ┌─────────┐
    │ Payment │───⊂ IPayment
    │ Client  │
    └─────────┘
- Socket (⊂) = required interface (services needed)
#### 4. **Ball-and-Socket Assembly**
```
┌─────────┐    ○───⊂    ┌─────────┐
│ ComponentA │───────────│ ComponentB │
│ (requires) │           │ (provides) │
└─────────┘               └─────────┘
```
### 3.6.C Interface Relationships
#### 1. **Realization** (Class → Interface)
- Class **implements** interface operations.
- Notation: Dashed line with hollow triangle arrowhead.
```
┌─────────┐        - - - ▷    ┌─────────────────┐
│ Order   │───────────────────▶│ «interface»     │
│ Service │                    │    IOrder       │
└─────────┘                    └─────────────────┘
```
#### 2. **Usage/Dependency** (Client → Interface)
- Client **uses** interface.
- Notation: Dashed arrow (→).
```
┌─────────┐        - - - →    ┌─────────────────┐
│ Payment │───────────────────▶│ «interface»     │
│ Client  │                    │    IPayment     │
└─────────┘                    └─────────────────┘
```
#### 3. **Interface Inheritance**
- Interface can **extend** another interface.
- Notation: Solid line with hollow triangle (like class inheritance).
```
    ┌─────────────────┐
    │ «interface»     │
    │   IBasic        │
    └─────────────────┘
            ▲
            │
    ┌───────┴───────┐
    │               │
┌───▼───┐       ┌───▼───┐
│IAdvanced│       │IExtended│
└────────┘       └────────┘
```
### 3.6.D Provided vs Required Interfaces
| Aspect          | Provided Interface | Required Interface |
| --------------- | ------------------ | ------------------ |
| **Definition**  | Services offered   | Services needed    |
| **Notation**    | Ball (○)           | Socket (⊂)         |
| **Direction**   | Outgoing           | Incoming           |
| **Role**        | Supplier           | Consumer           |
| **Also called** | Export interface   | Import interface   |
```
┌─────────────────────────────────┐
│           WebServer             │
│                                 │
│  ┌─○ IHttp (provided)           │
│  │                              │
│  └─○ IHttps (provided)          │
│                                 │
│  ┌─⊂ ILogger (required)         │
│  │                              │
│  └─⊂ IAuth (required)           │
└─────────────────────────────────┘
```
### 3.6.E Interface vs Abstract Class
| Aspect                   | Interface                      | Abstract Class                  |
| ------------------------ | ------------------------------ | ------------------------------- |
| **Implementation**       | No implementation              | Can have partial implementation |
| **Multiple inheritance** | Yes (class can implement many) | No (single inheritance)         |
| **Attributes**           | Only constants (static final)  | Can have instance variables     |
| **Constructors**         | No                             | Yes                             |
| **Methods**              | All abstract (by default)      | Mix of abstract/concrete        |
| **When to use**          | Capability/contract            | Common base with shared code    |
### 3.6.F Interface Examples
#### Example 1: Multiple Interfaces
```
┌─────────────────┐
│   «interface»   │
│    IPrint       │
├─────────────────┤
│ + print()       │
└─────────────────┘
        ▲
        │
┌───────┴─────────────────┐
│                         │
┌▼─────────┐     ┌────────▼───┐
│«interface»│     │«interface» │
│  IScan    │     │  IFax      │
├───────────┤     ├────────────┤
│ + scan()  │     │ + fax()    │
└───────────┘     └────────────┘
        ▲                 ▲
        └───────┬─────────┘
                │
        ┌───────▼─────────┐
        │   AllInOnePrinter│
        │   (implements    │
        │   IPrint, IScan, │
        │   IFax)          │
        └─────────────────┘
```
#### Example 2: Component with Interfaces
```
┌─────────────────────────────────┐
│       OnlineStoreSystem         │
│                                 │
│  ┌─────────────────────────┐    │
│  │     OrderComponent      │    │
│  │  ┌─○ IOrder             │    │
│  │  └─⊂ IPayment           │    │
│  └─────────────────────────┘    │
│            │                    │
│            │ uses                │
│            ▼                    │
│  ┌─────────────────────────┐    │
│  │    PaymentComponent     │    │
│  │  ┌─○ IPayment           │    │
│  │  └─⊂ IInventory         │    │
│  └─────────────────────────┘    │
│                                 │
└─────────────────────────────────┘
```
#### Example 3: Interface Segregation
```
// Bad: Fat interface
┌─────────────────┐
│ «interface»     │
│   IWorker       │
├─────────────────┤
│ + work()        │
│ + eat()         │
│ + sleep()       │
│ + manage()      │
└─────────────────┘
// Better: Segregated interfaces
┌─────────────────┐   ┌─────────────────┐
│ «interface»     │   │ «interface»     │
│   IWorkable     │   │   IEatable      │
├─────────────────┤   ├─────────────────┤
│ + work()        │   │ + eat()         │
└─────────────────┘   └─────────────────┘
┌─────────────────┐   ┌─────────────────┐
│ «interface»     │   │ «interface»     │
│   ISleepable    │   │   IManageable   │
├─────────────────┤   ├─────────────────┤
│ + sleep()       │   │ + manage()      │
└─────────────────┘   └─────────────────┘
┌─────────────────┐
│    Robot        │   (implements IWorkable only)
└─────────────────┘
┌─────────────────┐
│    Human        │   (implements IWorkable, IEatable, ISleepable)
└─────────────────┘
┌─────────────────┐
│    Manager      │   (implements IWorkable, IManageable)
└─────────────────┘
```

### 3.6.G Interface in Component-Based Development
| Concept                   | Role of Interface                                           |
| ------------------------- | ----------------------------------------------------------- |
| **Binary Replaceability** | Components can be swapped if they implement same interfaces |
| **Plug-in Architecture**  | New features added by implementing interfaces               |
| **Contract-Based Design** | Interface defines exact contract between provider/consumer  |
| **Versioning**            | New interface versions allow evolution                      |
| **Testing**               | Mock implementations for testing                            |
# 3.8 Interactions
### 3.8.A Concept
- **Interaction** = behavior comprising a set of **messages exchanged** among a set of **objects** within a context to accomplish a purpose.
- Captures **dynamic behavior** of collaborating objects.
- Represented by **interaction diagrams** (Sequence, Communication).
### 3.8.B Elements of Interaction
#### 1. **Object**
- Instance of a class participating in interaction.
- Notation: `objectName : ClassName` (underlined).
#### 2. **Message**
- Communication between objects conveying information with expectation of activity.
- Can be: operation call, signal, creation, destruction.
#### 3. **Link**
- Connection path between objects along which messages flow.
- Instance of an association.
#### 4. **Lifeline**
- Represents object's existence over time.
#### 5. **Activation**
- Period during which object is performing an action.
### 3.8.C Types of Interactions
| Type                        | Description         | Diagram                     |
| --------------------------- | ------------------- | --------------------------- |
| **Simple Interaction**      | Linear sequence     | Sequence Diagram            |
| **Conditional Interaction** | Alternative paths   | Sequence (alt fragment)     |
| **Iterative Interaction**   | Loops/repetition    | Sequence (loop fragment)    |
| **Concurrent Interaction**  | Parallel activities | Sequence (par fragment)     |
| **Structured Interaction**  | Nested/combined     | Any with combined fragments |
### 3.8.D Message Types
| Message Type       | Notation               | Description      |
| ------------------ | ---------------------- | ---------------- |
| **Synchronous**    | →▸ (solid, filled)     | Caller waits     |
| **Asynchronous**   | → (solid, open)        | Caller continues |
| **Return**         | - - - > (dashed)       | Response         |
| **Create**         | → with «create»        | New object       |
| **Destroy**        | → with «destroy» and X | Terminate object |
| **Self/Reflexive** | ↻                      | Message to self  |
### 3.8.E Interaction Contexts
#### 1. **Within an Operation**
- Messages inside a single method.
#### 2. **Within a Class**
- All interactions involving instances of a class
#### 3. **Within a Component**
- Internal collaboration of component parts.
#### 4. **Within a Use Case**
- Realization of a use case scenario
#### 5. **Within a System**
- Overall system behavior.
### 3.8.F Combined Fragments (Revisited)
| Fragment            | Purpose                           | Syntax            |
| ------------------- | --------------------------------- | ----------------- |
| **alt**             | Alternative paths (if-else)       | `alt [condition]` |
| **opt**             | Optional path                     | `opt [condition]` |
| **loop**            | Repetition                        | `loop [min,max]`  |
| **par**             | Parallel execution                | `par`             |
| **critical**        | Atomic region                     | `critical`        |
| **ignore/consider** | Ignore/consider specific messages | `ignore {event}`  |
| **assert**          | Assert condition                  | `assert`          |
| **neg**             | Invalid/negative scenario         | `neg`             |
### 3.8.G Interaction Examples

#### Example 1: Simple Interaction (Sequence)
```
┌─────┐         ┌─────┐         ┌─────┐
│:User│         │:ATM │         │:Bank│
└──┬──┘         └──┬──┘         └──┬──┘
   │                │                │
   │ insertCard()   │                │
   │───────────────>│                │
   │                │ validate()     │
   │                │───────────────>│
   │                │                │
   │                │     valid      │
   │                │<───────────────│
   │   ready        │                │
   │<───────────────│                │
   │                │                │
```
#### Example 2: Complex Interaction with Combined Fragments
```
┌─────┐         ┌─────┐         ┌─────┐
│:User│         │:ATM │         │:Bank│
└──┬──┘         └──┬──┘         └──┬──┘
   │                │                │
   │ enterPIN()     │                │
   │───────────────>│                │
   │                │                │
   loop [max 3]     │                │
   │                │ validatePIN()  │
   │                │───────────────>│
   │                │                │
   │                │     result     │
   │                │<───────────────│
   │                │                │
   alt [valid]      │                │
   │                │ showMenu()     │
   │<───────────────│                │
   │                │                │
   [else]           │                │
   │  invalidPIN    │                │
   │<───────────────│                │
   end alt          │                │
   end loop         │                │
   │                │                │
   opt [cardTrapped]│                │
   │                │ trapCard()     │
   │                │───────────────>│
   │                │                │
   end opt          │                │
   │                │                │
```
### 3.8.H Interaction vs Other Concepts
| Concept           | Relationship to Interaction                              |
| ----------------- | -------------------------------------------------------- |
| **Collaboration** | Society of objects working together (structure)          |
| **Interaction**   | Behavior of collaboration (dynamics)                     |
| **Use Case**      | Defines goal; interaction realizes it                    |
| **Operation**     | Single service; interaction may span multiple operations |
# 3.9 Use Cases
### 3.9.A Concept
- **Use case** = description of a sequence of actions a system performs that yields an **observable result of value** to an actor.
- Captures **functional requirements** from user perspective.
- Answers: _What does the system do?_ (not how).
### 3.9.B Use Case Components
#### 1. Use Case Name
- **Verb phrase** (e.g., "Withdraw Money", "Register Student")
- Should be **unique** and **descriptive**
#### 2. Actor
- **Primary Actor**: Initiates use case, gets value
- **Secondary Actor**: Participates but doesn't initiate
- **Supporting Actor**: Provides service (e.g., payment system)
#### 3. Flow of Events
- **Basic Flow**: Normal, happy path
- **Alternative Flows**: Variations, exceptions
#### 4. Precondition
- What must be true **before** use case begins
#### 5. Postconditions
- What must be true **after** use case completes successfully
### 3.9.C Use Case Template
| Section               | Description       | Example (Withdraw Money)                                                              |
| --------------------- | ----------------- | ------------------------------------------------------------------------------------- |
| **Use Case Name**     | Verb phrase       | Withdraw Money                                                                        |
| **Primary Actor**     | Who initiates     | Customer                                                                              |
| **Secondary Actors**  | Others involved   | Bank System                                                                           |
| **Preconditions**     | What must be true | ATM has cash, network OK, customer has card                                           |
| **Basic Flow**        | Normal sequence   | 1. Customer inserts card  <br>2. System validates card  <br>3. Customer enters PIN... |
| **Alternative Flows** | Exceptions        | Invalid card, wrong PIN, insufficient funds                                           |
| **Postconditions**    | What changes      | Balance reduced, transaction recorded                                                 |
### 3.9.D Writing Good Use Cases
#### Guidelines:
1. **Focus on user goals**, not system internals
2. Use **active voice** ("Customer enters PIN" not "PIN is entered")
3. Keep **technology independent**
4. Each step should be **atomic** (single action)
5. Show **value** to actor
#### Common Mistakes
- Too detailed (design-level)
- Too vague (missing steps)
- Mixed with non-functional requirements
- No clear actor goal
### 3.9.E Use Case Relationships (Detailed)
#### 1. **Include Relationship** (`<<include>>`)
- **Definition**: Base use case **always includes** behavior of included use case.
- **Purpose**: Reuse common functionality across multiple use cases.
- **Direction**: Base → Include
```
┌─────────────┐    <<include>>    ┌─────────────┐
│ Place Order │────────────────G─▶│ Validate    │
└─────────────┘                   │ User        │
                                  └─────────────┘
┌─────────────┐    <<include>>    ┌─────────────┐
│ Track Order │──────────────────▶│ Validate    │
└─────────────┘                   │ User        │
                                  └─────────────┘
```

#### 2. **Extend Relationship** (`<<extend>>`)
- **Definition**: Extension use case **optionally adds** behavior to base use case.
- **Purpose**: Handle optional/exceptional behavior.
- **Direction**: Extension → Base
- **Extension points**: Where behavior can be inserted
```
┌─────────────┐    <<extend>>    ┌─────────────┐
│ Place Order │◀─────────────────│ Apply       │
│ [if VIP]    │                  │ Discount    │
└─────────────┘                  └─────────────┘
     ▲
     │ extension point: after validation
```
#### 3. **Generalization**
- **Definition**: Child use case inherits from parent, may override/add steps.
 - **Purpose**: Common behavior with specialization.
```
    ┌─────────────┐
    │ Purchase    │
    │ Ticket      │
    └─────────────┘
         ▲
    ┌────┴─────┐
    │          │
┌───▼────┐ ┌───▼────┐
│Purchase│ │Purchase│
│Movie   │ │Concert │
│Ticket  │ │Ticket  │
└────────┘ └────────┘
```
### 3.9.F Include vs Extend vs Generalization
| Aspect                     | Include              | Extend               | Generalization               |
| -------------------------- | -------------------- | -------------------- | ---------------------------- |
| **Mandatory?**             | Yes                  | No (optional)        | Depends                      |
| **Direction**              | Base → Included      | Extension → Base     | Child → Parent               |
| **Base complete without?** | No                   | Yes                  | Yes (but less specific)      |
| **Purpose**                | Common functionality | Optional/exceptional | Specialization               |
| **Execution**              | Always               | When condition true  | Substituted                  |
| **Example**                | Validate user        | Apply discount       | MovieTicket vs ConcertTicket |
### 3.9.G Use Case Levels
| Level             | Scope            | Example                   |
| ----------------- | ---------------- | ------------------------- |
| **Summary/Cloud** | Business process | "Manage Customer Account" |
| **User Goal**     | Single user goal | "Withdraw Money"          |
| *Subfunction**    | Reusable piece   | "Validate PIN"            |
### 3.9.H Use Case Formats
#### 1. **Brief Format**
- One paragraph summary
- For simple use cases or early analysis
#### 2. **Casual Format**
- Several paragraphs
- Includes basic flow and some alternatives
#### 3. **Fully Dressed Format**
- Complete template with all sections
- For critical, complex use cases
### 3.9.I Complete Example: "Borrow Book" (Fully Dressed)
```
USE CASE: Borrow Book
ACTORS:
  - Primary: Library Member
  - Secondary: Librarian, Library System
PRECONDITIONS:
  - Member has valid library card
  - Book is available in catalog
  - Member has no overdue books or fines
BASIC FLOW:
  1. Member presents library card to librarian
  2. Librarian scans card
  3. System validates member status
  4. Member provides book details
  5. Librarian scans book barcode
  6. System checks book availability
  7. System records loan
  8. System updates book status to "Checked Out"
  9. System prints due date receipt
  10. Librarian gives receipt and book to member
ALTERNATIVE FLOWS:
  
  3a. Member has overdue books:
      3a1. System displays overdue books
      3a2. Member returns books before continuing
      
  3b. Member has unpaid fines:
      3b1. System displays fine amount
      3b2. Member pays fines (use case: Pay Fine)
      3b3. Return to step 4
      
  6a. Book not available:
      6a1. System shows "Book Checked Out"
      6a2. System offers reservation option
      6a3. Member may reserve (use case: Reserve Book)
      6a4. Use case ends
  6b. Book is reference-only:
      6b1. System shows "Reference Only - 2 hour loan"
      6b2. Librarian confirms special loan terms
      6b3. Continue to step 7 with 2-hour limit
POSTCONDITIONS:
  - Book status = "Checked Out"
  - Loan record created with due date
  - Member's borrowed count incremented
  - Book removed from available list
```
### 3.9.J Use Cases in OOAD
| Phase            | Use Case Role                        |
| ---------------- | ------------------------------------ |
| **Requirements** | Capture functional requirements      |
| **Analysis**     | Identify objects from use case steps |
| **Design**       | Design realization of use cases      |
| **Testing**      | Basis for test cases                 |
