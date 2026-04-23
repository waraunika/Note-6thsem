# 1 Chapter
# 2 Chapter 2
## 2.1 Fundamental Concepts of Object Orientation
### 2.1.1 Class
- Blueprint of template that describes characteristics and behavior of similar objects
### 2.1.2 Objects
- Identifiable entity with characteristics (attributes) and behavior (operations).
- Instance of a class
### 2.1.3 Inheritance
- Ability to create new class from existing class
- inherit all non-private features
- promotes reusability and reliability
### 2.1.4 Polymorphism
- ability to make more than one form
- poly = many
- morphe = forms
- achieved through function overloading, function overriding, templates
#### 2.1.4.1 Types
1. Compile Time Polymorphism
	1. Determined at compilation
	2. Mechanism of function overloading, operator overloading
	3. fast speed
	4. less flexibility
2. Run Time Polymorphism
	1. Determined at execution
	2. mechanism of virtual function, pointers
	3. slower speed
	4. more flexibility
```c++
void draw(Circle c);
void draw(Square s); // compile time polymorphism, overloading

class Shape { virtual void draw(); }
class Circle : public Shape { void draw(); } // run time polymorphism
```
### 2.1.5 Encapsulation
- binding functions and data together hiding data from unauthorized access
- is used for data hiding, exposing only relevant details
### 2.1.6 Data abstraction
- representing essential features without including background details
- purpose is to use complex objects without knowing internal workings
### 2.1.7 Adv of OOSD
1. Less Maintenance: Modular structure makes changes easier
2. Code Reusability: Inheritaance allows re use across projects
3. Faster development: re use reduces development time
4. improved reliability: tested components reused
5. real-world modeling: natural representaation of problem domain
6. Better Abstraction: Complexity hidden at object level
7. Reduced Transition Complexity: Smoother movement between development phases
### 2.1.8 OOS vs Procedural OS

| Aspect                | OOS                               | POS                               |
| --------------------- | --------------------------------- | --------------------------------- |
| Focus                 | Data and operations together      | Functions (operations)            |
| Modularity            | Objects encapsulate data          | Functions operate on globaal data |
| Data Security         | Data hiding through encapsulation | data accessible globally          |
| Reusability           | High inheritance, composition     | low, copy-paste code              |
| real world mapping    | natural                           | artificial                        |
| complexity management | better abstraction                | limited abstraction               |
## 2.2 Object Oriented System Development
### 2.2.1 Development Cycle
- Applies object orientation across all development activities
	- analysis
	- design
	- programming
	- testing
	- maintenance
- requires more time in early phases (requirements, analysis, design)
- about 25% of development time before coding begins
### 2.2.2 Transformations in OOD
1. Analysis
	1. takes user needs
	2. outputs system requirements, responsiblities
	3. focuses on what the system should do
2. Design
	1. Takes the problem statement
	2. outputs the detailed design, architecture, test plans
	3. focuses on how to build the system
3. Implementation
	1. takes Detailed Design
	2. outputs operational system and deployment
	3. building the solution
### 2.2.3 OO Analysis
- Investigation of the problem and requirements rather than finding a solution
- Key questions in OOA:
	- what will my program do?
	- what will the classes be?
	- what will each class be responsible for
- OOA Activities
	- finding objects
	- organizing objects
	- describing how objects interact
	- defining ooperations of objects
	- defining objects internally
### 2.2.4 Identifying Elements in Object Model
#### 2.2.4.1 Identifying Objects and Classes
##### 2.2.4.1.1 Grammatical Parse Method
1. Underline each noun or noun clause in problem statement
2. Enter in a table
3. Note Synonyms
4. Filter using selection criteria
##### 2.2.4.1.2 Categories of Objects to look for:
| Category             | Description                                             | Example                           |
| -------------------- | ------------------------------------------------------- | --------------------------------- |
| External entities    | systems/devices/people that produce/consume information | sensors, user, other systems      |
| Things               | reports, displays, signals                              | Alarm, receipt, status display    |
| Occurrences/Events   | Actions within system operation                         | Sensor event, transaction         |
| Roles                | People interacting with system                          | manager, homeowner, operator      |
| Organizational Units | relevant groups                                         | division, monitoring service      |
| plces                | context of problem                                      | manufacturing floor, loading dock |
| structures           | classes of objects                                      | four-wheel vehicle                |
#### 2.2.4.2 Selection Criteria for Objects
1. Retained Information
	- information must be remembered for system to function
2. Needed Services
	- identifiable operations that change attribute
3. Multiple Attribute
	- single-attribute objects may be better as attribute
4. Common Attributes
	- Attributes apply to all occurences
5. Essential Requirements
	- External entitites essential to solution
Potential object should satisfy most/aaall of these
## 2.3 Specifying the Attributes
- attributes define thee object in problem context
- How to study attributes
	- Study processing narrative
	- Identifiable data items that belong to the object
	- Ask: what data fully defines this object in problem context
### 2.3.1 Visibility in OOD
| Visbility | Symbol | Scope         | Description                             |
| --------- | ------ | ------------- | --------------------------------------- |
| Public    | `+`    | Any           | Accessible to all classes               |
| Privaate  | `-`    | Same class    | Accessible only within class            |
| Protected | `#`    | subclass      | accessible within inheritance hierarchy |
| Packaage  | `~`    | Same packaage | Accessible within same package          |
### 2.3.2 Types of Visibility
1. Attribute Visibility
	- Determines which classes can access an attribute
	- private attributes: encapsulated, accessed only through methods
	- public attributes: directly accessible (less secure)
- Parameter Vsibility:
	- Variables passed to methods as parameters
	- Scope: exist only during method execution
	- Example: in `calculate(length, breadth)`, `length` and `width` have parameter visbility
- Global Visibility
	- Vaariables accessible throughout the program
	- risk: may violate encapsulation principles
	- better alternative: use class level (static) attributes with controlled access
	- aaavoid in oop
```c++
class BankAccount{
	private:                       // private visbility
		double balance;
		
	public:                        // public visibility
		void deposit(double amt) {   // paarameter visibility
			balance += amt;
		}
};

double globalTaxRate = 0.15;     // global visibility
```
### 2.3.3 Association Visibility
- how objects can navigate to related objects via associations
- types
	- navigable (-> ) one way access
	- bidirectional ( <->) both objects can access each other
	- non-navigable (--) no direct access (access through other means)
## 2.4 Defining Operations
Three categories of operations
- Manipulation
	- add, delete modify, select data
	- `addSensor()`, `deleteEvent()`
- Computation
	- Perform Calculation
	- `calculateFine()`, `computeTotal()`
	- Detect events or conditions
	- `checkSensor()`, `monitorAlarm()`
### 2.4.1 How to find operations
1. Study processing narrative
2. Isolate verbs (grammatical parse)
3. Connect verbs to specific objects
4. Consider communication between objects
## 2.5 CRC Cards
### 2.5.1 Concept
- Class Responsibility Collaboration Cards
- Index cards used for OOAD
- purpose: brainstorming, identifying classes, their responsibilities and collaboration
### 2.5.2 Components
- Class: Name of the class (noun from problem domain)
- responsibilities (what the class knows (attributes) and does (operations))
- collaborations: other classes needed to fulfill responsibility
### 2.5.3 Importance
- branstorming
	- collaborative identification of classes
- simplicity
	- low-tech, easy to modify
- focus
	- forcec focus on responsibility, not implementation
- Communication
	- visual tool for team discussions
- Iterative
	- easy to refine and reorganize
### 2.5.4 Example for library system
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
## 2.6 OO vs Conventional Approach
### 2.6.1 Key differences

| Aspect        | Conventional Design          | OO design                                      |
| ------------- | ---------------------------- | ---------------------------------------------- |
| Primary unit  | functions/modules            | objects                                        |
| data handling | data separate from fucntions | data + functions are binded                    |
| encapsulation | limited (global data)        | strong  (data hiding)                          |
| inheritance   | inheritance is not supported | inheritance supported                          |
| reusability   | reusability limited          | reusability high (via inheritance/composition) |
| Change impact | ripple effects               | localized                                      |
| maintenace    | more difficult               | easier                                         |
### 2.6.2 Encapsulation & Inheritance: OO vs Conventional
| Feature           | Conventional                | OO                         | Explanation                          |
| ----------------- | --------------------------- | -------------------------- | ------------------------------------ |
| **Encapsulation** | Data global or module-level | Data hidden within objects | OO protects data integrity           |
| **Inheritance**   | Not available               | Classes can inherit        | OO enables reuse without duplication |
### 2.6.3 OO Design Cycle vs Conventional

| Phase          | Conventional                         | OO                                    |
| -------------- | ------------------------------------ | ------------------------------------- |
| Analysis       | Focus on function                    | focus on objects and responsibilities |
| design         | data flow diagrams, structure charts | class diagrams, interaction diagrams  |
| implementation | functions operating on data          | objects sending message               |
| testing        | unit, integration, system            | class testing, inter-class testing    |
| transition     | distinct phase boundaries            | smoother transitions between phases   |
## 2.7 Requirement Elicitation in OOA
- Process:
	1. Identify stakeholders: users, domain experts, clients
	2. gather requirements: interviews, workshops, observation
	3. analyze domain: understand problem domain terminology
	4. identify objects: extract nouns from requirements
	5. capture interactions from user perspective
	6. validate: confirm understanding with stakeholders
# 3 Chapter
# 4 Chapter
## 4.1 Iterative Development
### 4.1.1 Concept
- Iterative development = cyclical process where you make and test incremental adjustments
- Popular in: Agile, Scrum, Software development, Design, research
### 4.1.2 Iterative Development Process

| Stage                   | Activities                                                                   |
| ----------------------- | ---------------------------------------------------------------------------- |
| Planning & Requirements | Map initial requirements                                                     |
|                         | gather documents                                                             |
|                         | create timeline for first cycle                                              |
| Analysis and design     | Create working architecture, schematic, or algorithm satisfying requirements |
| Implementation          | Develop functionality and design to meet specifications                      |
| Testing                 | Identify whats not working                                                   |
|                         | stakeholders, users provide feedback                                         |
| Evaluation and review   | Compare iteration with requirements and expectations                         |
### 4.1.3 Benefits of Iterative Development
- Flexibility: Adapt to new needs and unexpected issues
- Continuous Improvement: Each cycle refines the product
- Early feedback: Users see working product early
- Risk reduction: Problems are identified and resolved incrementally
## 4.2 Unified Processes
### 4.2.1 Concept
- UP = iterative and incremental software development process for building object oriented systems
- also known as rational unified process (RUP)
- provides disciplined approach to assign tasks and responsibilities in development organization
### 4.2.2 Why use UP?
- Iterative:
	- reduces unexpected costs
	- prevents resource wastage
- structured:
	- provides framework for OOA/D
- Flexible:
	- Can be applied in lightweight/agile approach with XP, Scrum
- UML/friendly
	- well suited for UML based modeling
### 4.2.3 Goal
- Ensure poduction of high quality software
- that meets end-user needs
- within predictable schedule and budget
### 4.2.4 Phases
```
┌───────────────────────────────────────────────────────────────────────┐
│                    UNIFIED PROCESS PHASES                             │
├──────────────┬──────────────────┬──────────────┬──────────────────────┤
│  INCEPTION   │ ELABORATION      │CONSTRUCTION  │     TRANSITION       │
├──────────────┼──────────────────┼──────────────┼──────────────────────┤
│ • Vision     │ • Analysis       │ • Coding     │ • Beta testing       │
│ • Scope      │ • Design         │ • Testing    │ • Deployment         │
│ • Feasibility│ • Architecture   │ • Integration│ • User feedback      │
│ • Risk ID    │ • Risk resolution│ • Refactoring│ • Bug fixes          │
└──────────────┴──────────────────┴──────────────┴──────────────────────┘
```
#### 4.2.4.1 Inception
- Activities and Description
	- Business Model
		- Develop initial business model
	- Requirements
		- Identify customer requirements
	- Communication
		- with customers and team members
	- Scope
		- Identify project scope and size
	- Feasibility
		- Perform feasibility study (technical, economic, operational)
	- Risk
		- Identify initial project risks
	- Planning:
		- Create project plan and goals
- Purpose
	- Develop idea into vision of end product
- Objectives:
	- concurrence on project scope and estimates
	- understanding of requirements
	- 10-20% of use cases analyzed
#### 4.2.4.2 Elaboration
- Activities and description
	- Refine Vision
		- More detail from inception
	- Architecture
		- Establish baseline architecture
	- Risk Resolution
		- Identify and address high risks
	- Requirements
		- Identify most requirements, refine scope
	- Estimates
		- Creaaate more realistic estimates
- Types of Risk Addressed
	- Requirements Risk
		- unclear or changing requirements
	- Technological Risk
		- New/Unfamiliar technology
	- Skill Risk
		- Team skill gaps
	- Political Risk
		- Stakeholder conflicts, organizationaal issues
- Purpose:
	- describe in detail
	- refine vision
	- establish baseline architecture
- Objectives at end of elaboration
	- use case model complete (80-90%)
	- non-functional requirements elaborated
	- software architecture described
	- revised risk list
	- preliminary user manual (optional)
#### 4.2.4.3 Construction
- Activities and description
	- Coding
		- Implementation of all omponents
	- Testing
		- Unit, integration, system testing
		- except beta testing
	- Integration
		- components integrated
	- Refactoring
		- Done after each iteration
	- Resource Management
		- Optimize cost, schedule, quality
- Purpose:
	- Develop and complete project
	- iterative implementation of remaining elements
- Objectives
	- product stable and mature for release
	- actual vs planned expenditure acceptable
	- all features tested
#### 4.2.4.4 Transition
- Activities and Description
	- Beta Testing
		- user acceptance testing in real environment
	- bug fixing:
		- remove defects based on feedback
	- deployment
		- releaase to production
	- optimization
		- performance tuning
	- releases
		- new releaases as needed
- purpose:
	- transition from development environment to production
- objectives:
	- customer satisfaction
	- stakeholder concurrence on deployment baselines
	- final product baseline achieved cost effectively
#### 4.2.4.5 Summary

| phase        | Focus                               | Key Outputs                                          | Risk Level  |
| ------------ | ----------------------------------- | ---------------------------------------------------- | ----------- |
| Inception    | Vision, scope, feasibility          | Projectt plaan, initial requirements, risk list      | HIGH        |
| Elaboration  | Architecture, detailed requirements | use case model, architecture baseline, refined risks | Medium-high |
| Construction | Coding, testing, integration        | Operational product, test results                    | Medium      |
| Transition   | Deployment, user acceptance         | Released product, user feedback                      | low         |
## 4.3 UP Disciplines
discipline = set of activities, and related artifacts in one subject areas
### 4.3.1 Overview

| Discipline                          | Purpose                             | Key Activities                                                                                                |
| ----------------------------------- | ----------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| Business Modeling                   | Understand business environment     | Understand surroundings, create system vision, create business models                                         |
| Requirements                        | Document business requirements      | Gather detailed info, define functional/non-funcitional requirements, develop UI dialogs, evaluate with users |
| Design                              | Design system based on requirements | Design architecture, use case realization, database, UI, security                                             |
| Implementation                      | Build/acquire system components     | Build software components, acquire components, integrate                                                      |
| Testing                             | Verify quality                      | Unit testing, integration testing, usability testing, acceptance testing                                      |
| Deployment                          | Make system operational             | Acquire hardware, package/install, train users, convert data                                                  |
| Project Management                  | Manage Project                      | Finalize scope, develop schedule, identify risks, monitor plan                                                |
| Configuration and Change Management | Control changes                     | Develop change control procedures, manage models and components                                               |
| Environment                         | Support development                 | Select tools, tailor UP process, provide technical support                                                    |
### 4.3.2 Detail
#### 4.3.2.1 Business Modeling
- purpose: understand business context
- artifacts: vision document, business models
- artifacts
	- understand surroundings
	- create system vision
	- create business models (use cases, domain models)
#### 4.3.2.2 Requirements
- Purpose: Document what system should do
- Maps to: traditional system analysis
- Activities:
	- Gather deailed information
	- define functional and non-functional requirements
	- develop user interface dialogs
	- evaluate requirements with users
#### 4.3.2.3 Design
- Purpose: how system will be built
- Activities:
	- design support services architecture and deployment environment
	- design use case realization (interaction diagrams)
	- design database
	- design system and user interfaces
	- design system security and controls
#### 4.3.2.4 Implementation
- Purpose: Build or acquire components
- Activities:
	- Build software components (coding)
	- acquire software compoennts (third party)
	- integrate software components
#### 4.3.2.5 Testing
- Purpose: Ensure quality
- Activities:
	- Define and conduct unit testing
	- define and conduct integration testing
	- .... usability testing
	- ... user acceptance testing
#### 4.3.2.6 Deployment
- Make system operational
- package and install components
- train users
- convert and initialize data
#### 4.3.2.7 Project Management
- Support all activities (most important support discipline)
- Activities:
	- finalize system and project scope
	- develop project and iteration schedule
	- identify project risks and confirm feasibility
	- monitor and control 
		- project plan
		- communications
		- risks and outstanding issues
#### 4.3.2.8 Configuration and change management
- purpose: control changes to artifacts
- artifacts managed: requirements, design, source code, executables
- activities:
	- develop change control procedures
	- manage models and software components
#### 4.3.2.9 Environment
- purpose: provide development infrastructure
- includes facilities workspace and communication forums
- activities
	- tailor UP development process
	- provide technical support services
### 4.3.3 UP Adv and Challenges
#### 4.3.3.1 Adv
- Iterative:;
	- early risk identification, continuous improvement
- Flexible
	- can be tailored for lightweight agile projects
- Well structured
	- clear phases and disciplines
- UML-integrated
	- seamless with object oriented modeling
- Predictable
	- better schedule and cost estimation
- quality-focused
	- testing integrated throughout
#### 4.3.3.2 Challenges
- Complexity
	- Full UP may be heavy for small projects
- Overhead
	- Documentation and process overhead
- Learning Curve
	- Requires understanding of disciplines
- Customization needed
	- Must be tailored for specific projects
# 5 Chapter 5 Object Oriented Design
## 5.1 Concepts
### 5.1.1 OOA vs OOD

| Aspect    | OOA                                                       | OOD                                                                   |
| --------- | --------------------------------------------------------- | --------------------------------------------------------------------- |
| Focus     | Finding and describing objects/concepts in problem domain | Defining software objects nd their collaborations                     |
| Questions | What does the system need?                                | How will the system be built?                                         |
| Example   | Book, Library, Librarian as a Concept                     | Book software object with `title` attribute and `getChapter()` method |
| Output    | Conceptual Model, requirements                            | Architecture, detailed design                                         |
### 5.1.2 Characteristics of OOD
- Objects as abstractions
	- objects represent real-world or system entities and manage themselves
- Encapsulation
	- Objects are independent with encapsulated state and representation
- Service Oriented
	- System functionality expressed in terms of object services
- Message Passing
	- Communication between objects through messages
- Distribution
	- Objects may be distributed, execute sequentially or in parallel
## 5.2 Booch method for OOD
### 5.2.1 Overview
- widely used OOAD methodology
- Notation superseded by UML (combined with OMT and OOSE)
- Methodology incorporated into Rational Unified Process
### 5.2.2 Diagrams in Booch Method
1. Design Level
	1. Class diagram
	2. Object Diagram
	3. State transition diagram
	4. Interaction diagram
2. Implementation Level
	1. Module diagram
	2. Process Diagram
### 5.2.3 Micro Development Process
- Daily activity of individual developer or small team
- analysis and design phases intentionally blurred
- Steps
	- Identify classes and objects at a given level of abstraction
	- identify semantics of these classes and objects
	- identify relationships among these classes and objects
	- specify interface, then implementation of these classes and objects
### 5.2.4 Macro Development Process
- higher level process focusing on risk and architectural vision
- Activity Cycle
	- Conceptualization
		- Establish core requirements
	- Analysis
		- Develop model of desired behavior
	- Deisgn
		- create an achitecture
	- Evolution
		- implementation
	- Maintenance
		- Evolution after delivery
### 5.2.5 Micro vs Macro

| Aspect   | Micro                       | macro                            |
| -------- | --------------------------- | -------------------------------- |
| Scope    | Daily individual/small team | overall project life cycle       |
| Focus    | class / object details      | risk and architecture            |
| duration | short cycles                | long-term phases                 |
| blurring | a/d intentionally blurred   | clear phase distinction          |
| output   | class specifications        | project milestones, architecture |
## 5.3 Coad-Yourdon Method
### 5.3.1 Overview
- primary strength in system analysis
- Describes static characteristics
- Addresses both application and infrastructure
### 5.3.2 SOSAS Steps
1. Subjects
	- Data flow diagram for objects
2. Objects
	- identify object classes and class hierarchies
3. Structures
	- classification structures (inheritance) and composition structures (other connections)
4. Attributes
	- identify attributes of each class
5. Services
	- identify all behaviors/methods for each class
### 5.3.3 Four Major Components
1. Problem Domain Component
	- Direct OO representation of the real world business entities.
	- Contents:
		- classes derived from requirements
		- e.g., in a library system: `Book`, `Member`, `Loan`, `Fine`
	- These objects have attributes and behaviors that directly model the problem.
	- example method: `Loan.calculateOverdueFine(days)`.
2. Human Interaction Component
	- The user interface and how users communicate with problem domain objects
	- Contents:
		- Windows, dialogs, menus, reports, input forms, etc.
		- Also, UI-specific classes (e.g., `LoanFormController`, `ButtonHandler`).
	- separate UI logic from business logic (model-view-controller pattern). define event handling and navigation flow
	- example: a `BookSearchDialog` class that takes user search text and calls `Book.findByTitle()` from PDC
3. Task Management Component
	- Handles concurrent activities, scheduling, coordination of tasks (processes, threads).
	- contents: 
		- classes that represent independent tasks, task initialization/suspension/resumption logic.
		- includes event handling and inter-task communication.
	- needed for real time systems, multi-user systems, or any system with background processing (printing, network polling, batch updates)
	- example: A `PrintQueueManager` task that runs separately from UI, or a `HeartbeatMonitor` thread
4. Data Management Component
	- Handles persistent storage and retrieval of objects (database, file system).
	- Contents:
		- classes that map in-memory objects to database tables or flat files includes SQL logic, file I/O, object serialization.
	- Design activity: Decide how objects become persistent, via ORm or custom code
	- Example: A `BookDataManager` with `save(Book b)`, `findByISBN(isbn)`, `delete(Book b)` that executes SQL statements.
### 5.3.4 General/UML-based components
- design model is not single diagram but a set of interconnected models representing different aspects of teh system.
- based on uml:
1. Static/Structural Components
	- the what
	- class diagram:
		- the core.
		- shows classes, attributes, methods and relationships
			- association, inheritance, aggregation, composition
	- Object diagram:
		- snapshot of class instances at a specific moment in time
	- Package Diagram:
		- Organizes classes into logical groups (layers/modules) to manage complexity
	- Component diagram:
		- shows how physical software components (`.jar`, `.dll`, `.exe`) all depend on each other
2. Dynamic/Behavioral Components
	- the how
	- Sequence Diagram
		- shows object interactions over time (message passing) for a single use case scenario
		- critical for detailed design
	- Communication (Collaboration) Diagram
		- like sequence but focuses on object links, not time
	- Activity Diagram
		- models workflows, parallel processing, and decision logic (like flowchart for OO)
	- State Machine Diagram
		- shows an object's life cycle, how its state changes in response to events
		- e.g., `Order` from `New -> Paid -> Shipped -> Delivered`
3. Interaction/Use case Components
	- the why
	- Use Case Diagram:
		- high level functional requirements
		- actors and their goals
	- User Interface Prototype/Storyboard
		- not pure UML, but part of the design model describing human interaction
4. Architectural Components
	- high level organization
	- Coad-Yourdon fits here
	- Presentation layer
		- UI
		- handles user interaction
	- Business Logic Layer
		- Domain
		- core objects
		- e.g., `Student`, `Course`, `Invoice`.
	- Persistence Layer
		- Delta
		- ORM, database access
	- Cross-cutting components
		- Logging, security, exception handling.
## 5.4 Relation between OOA and OOD
![[Pasted image 20260401143130.png]]
Transformations:
- Use Cases -> Subsystem Design
- Object Behavior Model -> subsystem design
- CRC index cards -> class and object design
- Attributes, Operations, Collaborators -> class and object design
- Object relationship model -> message design
- Attributes, Operations, Collaborators -> responsibilities design
### 5.4.1 Relationship
OOA:
- focuses on
	- understanding problem domain, identifying concepts
- outputs
	- requirements, conceptual classes
OOD:
- focuses on:
	- defining software objects and their collaborations
- outputs:
	- architecture, detailed design
OOP:
- focuses on:
	- implementing design in code
- outputs
	- executable software
### 5.4.2 Layers in Design Model
in pyradimal structure, from bottom to top
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
1. Subsystem layer:
	- contains a representation of each of thee subsystem that enables the software to achieve its customer defined requirements and to implement the technical infrastructure that supports customer requirements
2. the class and object layer
	- this layer contains a hierarchy of classes which enable the system to be created using generalizations and increasingly more targeted specializations
	- this layer also represents each object
3. Message layer
	- the layer contains the design details, which enables each object to communicate with its collaborators
	- this layer establishes the internal and external interfaces for the system
4. The responsibilities layer
	- this layer contains the data structure and algorithmic design for all operations and attributes for each object.
## 5.5 System Design Process
### 5.5.1 Concept
- system design develops architectural detail
- required to build a system or product
- defining modules, architecture, components, interfaces and thee data
- based on specified requirements
### 5.5.2 System Design Activities
1. partition analysis model
	- divide into cohesive subsystems
2. identify concurrency
	- determine inherent concurrency from problem
3. allocate subsystems
	- assign to processors and tasks
4. design user interface
	- develop UI architecture
5. design data management
	- choose strategy for storage/retrieval
6. identify global resources
	- determine control mechanisms for resource
7. design control mechanism
	- define system control flow
8. handle boundary conditions
	- consider initialization, termination, failure
9. review trade offs
	- evaluate design alternatives
## 5.6 Partition the Analysis Model
### 5.6.1 Subsystems
- definition: cohesive colelction of classes, relationships, and behavior packaged together
- characterized by: responsibilities (services they provide)
- interface: well-defined interface for external communication
### 5.6.2 Subsystem Characteristics
- cohesion
	- elements share common property or function
- encapsulation
	- classes collaborate mainly within subsystem
- small number
	- keep number of subsystems manageable
- internal partitioning
	- can be further divided to reduce complexity
- Communication
	- peer to peer or client-server between subsystems
## 5.7 Concurrency and Subsystem allocation
### 5.7.1 Identifying inherent concurrency
- two objects are inherently concurrent if they react to events simultaneously without interacting
- example: CPU and speaker must operate concurrently
### 5.7.2 Concurrency Option
1. Allocate to independent processors
	- use when high performance, physical distribution required
2. Allocate to same processor with OS support
	- use when cost effective, less overhead
### 5.7.3 Decision Factor
- Performance requirements
- cost constraints
- interprocessor communication overhead
## 5.8 Task management
### 5.8.1 Task Characteristics
- initiation
	- event-driven or clock-driven
	- both activated by interrutps
- priorrity
	- high priority tasks get immediate resource access
- criticality
	- high criticality tasks continue even in degraded mode
### 5.8.2 Task Template
- Task Name
	- name of the object
- Description
	- narrative describing prupose
- Priority
	- low, medium, high
- services
	- list of operation responsibilities
- coordinated by
	- how object behavior is invoked
- communicaated via
	- inputs/output data values relevant to ask
## 5.9 Data Management Component
### 5.9.1 Areas of Concern
1. Management of critical application data
2. Infrastructure for storage and retrieval of obejcts
### 5.9.2 Design Approach
- layered design: isolate low-level data manipulation from high-level attribute handling
- DBMS: Often used as common data store for all subsystems
## 5.10 Resource Management Component
- Resource: disk drives, processors, communication lines, database, objects
- Design challenge: subsystems compete for resources concurrently
- Solution: Design control mechanisms regardless of resource nature
## 5.11 Object Design Process
### 5.11.1 Purpose
- prepare for implementation based on system design decisions
- transform analysis and system design models
- investigate alternative implementations
- minimize execution time, memory, and other cost measures
### 5.11.2 Forms of Object Description
1. Protocol Description
	- describes interface definition
	- contains messagees na object can receive, and corresponding operations
2. Impelemntation Description
	- describes internal details
	- contains private data structures, procedural descriptions of operations
### 5.11.3 Object Design Steps
1. Develop problem statement
2. Identify objects and classes
3. Filter out required classes
4. identify associations, attributes, links
5. prepare data dictionary
6. discard unnecessary associations/attributes
7. apply inheritance
8. check accessibility
9. iterate and refine
10. group classes into modules
## 5.12 Object DBMS
### 5.12.1 Features
- Object identity
	- unique OIDs for objects
- complex objects
	- support for nested/composite objects
- encapsulation
	- data + methods stored together
- inheritance
	- class hierarchies in database
- polymorphism
	- operations on subtypes
- persistence
	- objects survive program execution
### 5.12.2 Object DBMS vs RDBMS

| Aspect                  | Object DBMS                 | RDBMS                     |
| ----------------------- | --------------------------- | ------------------------- |
| **Data Model**          | Objects and classes         | Tables and rows           |
| **Data Representation** | Complex objects             | Flat tables               |
| **Relationships**       | Direct references           | Foreign keys              |
| **Inheritance**         | Supported                   | Not directly supported    |
| **Encapsulation**       | Methods stored with data    | Business logic separate   |
| **Query Language**      | Object Query Language (OQL) | SQL                       |
| **Performance**         | Better for complex objects  | Better for simple queries |
| **Schema Evolution**    | Easier                      | Requires migration        |

---
---

---
---
# 6 Chapter
## 6.1 Overview of Testing
### 6.1.1 Concept
- Software testing is the process to identify correctness, completeness, and quality of developed software
- executing program under positive and negative conditions by manual or automated means
- checking specification, functionality and performance
### 6.1.2 Testing = Verification + Validation
| Aspect             | Verification                       | Validation                         |
| ------------------ | ---------------------------------- | ---------------------------------- |
| **Question**       | Are we building the product right? | Are we building the right product? |
| **Focus**          | Conformance to specifications      | Conformance to user needs          |
| **Method**         | Static testing (no code execution) | Dynamic testing (code execution)   |
| **Activities**     | Reviews, walkthroughs, inspections | Black box, white box testing       |
| **Responsibility** | QA team                            | UAT testers, business users        |
### 6.1.3 Objectives
1. Uncover errors
	- find as many bugs as possible in the product
2. Demonstrate requirements
	- show software matches specifications
3. Validate Quality
	- ensure quality with minimum cost and effort
4. Generate Test Cases
	- create high-quality test cases and effective tests
### 6.1.4 Importance of Software Testing
1. Confidence
2. Identify weakness
3. Quality measurement
4. Requirements Validation
5. System Understanding
6. Usability Proof
### 6.1.5 Terminology
- Error: Human action producing incorrect result leading to fault
- Bug: Presence of error during software execution
- Fault: State of software caused by an error
- failure: deviation from expected result (an event)
- Test data: input devised to test the system
- Test case: Triplet (I, S, O), I = input, S = system state, O = expected output
## 6.2 OO Testing
### 6.2.1 Concept
- Collection of testing techniques to verify and validate object-oriented softwaare
- revolves around fundamental entity called "class"
- larger systems divided into small, well-defined units (classes) and implemented separately
### 6.2.2 Testing Levels in OOT

| Level                          | Testing Activities                                                                                                         |
| ------------------------------ | -------------------------------------------------------------------------------------------------------------------------- |
| 1. Requirements Testing        | Model reviews, prototype walkhroughs, usage scenario testing                                                               |
| 2. Analysis Testing            | Model reviews, prototype walkthroughs, usage scenario testing                                                              |
| 3. Architecture/Design Testing | Model reviews, walkthroughs, prototype walktrhoughs                                                                        |
| 4. Code Testing                | Black box, white box, boundary value, class testing, integration testing, coverage testing, inheritance regression testing |
| 5. System Testing              | Function testing, installation testing, operations testing, stress testing, support testing                                |
| 6. User Testing                | Alpha testing, Beta testing, UAT                                                                                           |
## 6.3 Types of Testing
### 6.3.1 Unit Testing

| Aspect       | Description                                                       |
| ------------ | ----------------------------------------------------------------- |
| Definition   | Testing individual units of source code (function, file, program) |
| Performed by | Software developers                                               |
| Purpose      | Ensure code meets design and behaves as intended                  |
| Focus        | Smallest testable part of code                                    |
### 6.3.2 Integration Testing

| Aspect       | Description                                            |
| ------------ | ------------------------------------------------------ |
| Definition   | Testing integrated units as a group after unit testing |
| Performed By | Testers                                                |
| Purpose      | Check data flow between modules                        |
#### 6.3.2.1 Types of Integration Testing
1. Big Bang
	- all modules combined into complete system, then tested
2. Top Down
	- Testing from top to bottom following control flow
	- higher level modules tested first
3. Bottom Up
	- Lower-level modules tested first
	- used to facilitate testing of higher-level modules
### 6.3.3 System Testing
- Testing complete integrated system
- Evaluate system's compliance with specified requirements
- type is black box testing
- behavior, design end-user expectations
### 6.3.4 Acceptance Testing
- testing to verify requirements are met as per delivery
- Performed by user or customer
#### 6.3.4.1 Alpha vs Beta Testing

| Alpha Testing                               | Beta Testing                             |
| ------------------------------------------- | ---------------------------------------- |
| Performed by developers at development site | performed by customers at their own site |
| white-box + black box techniques            | balack box technique only                |
| simulated/virtul environment                | reaal-time environemtn                   |
| absence of targeted end users               | absence of development/qa team           |
| not open to market/public                   | open to market and public                |
| less user feedback incorporation            | incorporates user feedback               |
| used for software applications              | used for softwarae products              |
## 6.4 OO vs Conventional Testing

| Aspect          | Conventional                  | OO                                                |
| --------------- | ----------------------------- | ------------------------------------------------- |
| Unit of Testing | functions, modules            | claasses                                          |
| Test focus      | input-process-output view     | sequences of operations to exercise class states  |
| Dependencies    | Data and calling dependencies | Class-to-claass, inheritance, polymorphism        |
| Integration     | Top-down, bottom-up, big bng  | class integration, inheritance regression         |
| reusability     | limited test case reuse       | test cases reusable with inheritance              |
| encapsulation   | not a factor                  | affects testing (need to test through interfaces) |
| polymorphism    | not present                   | requires testing of dynamic binding               |
## 6.5 Interclass test case design
### 6.5.1 Concept
- test case design becomes more complex during integration of object oriented system
- collaboration testing accomplished through
	- random methods
	- partitioning methods
	- scenario based testing
	- behavioral etsting
### 6.5.2 Multiple class testing process
- Step 1:
	- For each client class, use a list of class operations to generate random test sequences
- Step 2:
	- operations send messages to server classes
- Step 3:
	- for each message, determine collaborator class and corresponding operation in server object
- Step 4:
	- For each message, determine next level of operations invoked and incorporated into test sequence
### 6.5.3 Interclass Test Case design methods
#### 6.5.3.1 Random Testing
##### 6.5.3.1.1 Process
- generate random sequences of operations across collaborating classes
- focus on interactions between classes
- identify sequences that test class interactions
##### 6.5.3.1.2 Example
```
Random Sequence:
1. Order.create()
2. Inventory.checkStock(orderItem)
3. Order.addItem(item)
4. Inventory.reserveItem(item)
5. Order.calculateTotal()
6. Inventory.updateStock(item)
```
#### 6.5.3.2 Partition Testing
- Types, with example of bank account
	- By operation type
		- group operations by behavior
		- e.g., creation, modification, deletion, query
	- By State
		- test based on object state
		- e.g., account: new, active, closed, overdrawn
	- By Attribute Values
		- Test based on attribute ranges
		- e.g., Balance: Positive, zero, negative
	- By collaborator
		- test interactions with specific collaborators
		- e.g., account: interacts with customer, transaction
- Approach is to divide the test space into categories
##### 6.5.3.2.1 Example
```
Partition by State:
- New Account: test deposit, withdrawal, closure
- Active Account: test normal operations
- Overdrawn Account: test fees, restrictions
- Closed Account: test no operations allowed

Partition by Operation:
- Creation: constructor, initialize
- Modification: deposit, withdraw, transfer
- Query: getBalance, getStatement
- Destruction: close, terminate
```
#### 6.5.3.3 Scenario based testing
- approach is to create realistic user scenarios that exercise multiple classes
- exmple: library system scenrio
```
Scenario: Member borrows book
1. Member searches for book (Catalog class)
2. System checks availability (Inventory class)
3. Member requests book (Loan class)
4. System creates loan (Loan class)
5. System updates member record (Member class)
6. System updates book status (Book class)
```
#### 6.5.3.4 Behavioral Testing
- approach is test based on state models of collaborating objects
- process:
	- identify states of collaborating objects
	- test transitions triggered by messages
	- verify correct state changes across claasses
- Example: ATM system behavior
```
State: Card Inserted → PIN Entered → Validated → Transaction Selected → Complete
Messages between: ATM, CardReader, BankSystem, Account
```
#### 6.5.3.5 Inheritance Regression Testing
- inherited methods
	- test whether subclass preserves superclaass behavior
- Overridden methods
	- test new behaavior and ensure it doesn't break contracts
- New method
	- test aadded functionality
- Polymorphic calls
	- test dynamic binding together
- approach is to test subclasses for inherited behavior
---
---

---
---
# 7 Chapter
## 7.1 Project Selection and Preparation
### 7.1.1 Process Maturity Levels (SEI capability maturity model)

| Level | Name       | Description                                                                     |
| ----- | ---------- | ------------------------------------------------------------------------------- |
| 1     | Initial    | No documented method, each developer works independently                        |
| 2     | Repeatable | Informal method exists by consensus, "the way we do things around here"         |
| 3     | Defined    | Formaal, documented process; continuously refined by software process group     |
| 4     | Managed    | Formal measurements of process and product (time, cost,, productivity, quality) |
| 5     | Optimizing | Measurements systemaatically used as feedback to optimize process               |
### 7.1.2 Introducing new development process
- Important observations
	- organization maturity != individual maturity
	- transition period causes temporary productivity drop
	- mature systems with limited maintenance needs may not justify technology change
- key success factors for transition
	- upper management support
	- careful first project
	- positive team attitude
	- method before tool
	- integration
	- reasonable expectation
	- realistic reuse expectation
### 7.1.3 Factors Selecting first project for new method
- Project importance:
	- real project that is important, but not with tight schedule or hard constraints
- problem domain
	- well-known and well-defined domain
- team selection
	- experienced developers with positive view of change
	- management confidence
- project maanager
	- high degree of interest in the task
- staff commitment
	- full time on project, not disturbed by other projects
- planning
	- detailed plan developed in advance with pre-established evaluation criteria
- sponsor
	- upper management person with special interest to follow and support project
### 7.1.4 General factors for project selection
- Strategic alignment
	- does project align with business goals
- feasibility
	- is project technically, economically, operationally feasible?
- Risk level
	- what are the identified risks? can they be managed?
- Resource availbility
	- are skilled staff, budget, infrastructure aavilable
- Timeline
	- is schedule realistic? any hard constraints
- Scope
	- is scope well defined? manageable?
- Stakeholder support
	- is there commitment from key stakeholders
- Reuse Potential
	- can components be reused in future projects?
## 7.2 Risk Management Process
### 7.2.1 Activities
Risk Identification -> Risk AAssessment (analysis + prioritization)
 -> Risk Control (plaanning + resolution + monitoring)
### 7.2.2 Risk Management Flow
```

┌─────────────────────┐
│ Risk Identification │───> List of potential risks
└────────┬────────────┘
         ▼
┌─────────────────────┐
│ Risk Analysis       │───> Prioritized Risk List
└────────┬────────────┘
         ▼
┌─────────────────────┐
│ Risk Planning       │───> Avoidance & Contingency Plans
└────────┬────────────┘
         ▼
┌─────────────────────┐
│ Risk Monitoring     │───> Risk Assessment
└────────┬────────────┘
         │
         └──────> (loops back to analysis)
```
### 7.2.3 Types of Risk
- Schedule Risk
	- wrong time estimtion
	- improper resource tracking
	- failure to identify complex functionalities
	- scope expansion
- Budget Risk
	- wrong budget estimation
	- cost overruns
	- scope expansion
- Operational Risk
	- Priority conflicts
	- unclear responsibilities
	- insufficient resources
	- no training
	- poor communication
- Technical Risk
	- changing requirement
	- immature technology
	- complex product
	- difficult integration
- Programmatic risk
	- running out of funds
	- market changes
	- changing customer priorities
	- government regulation changes
### 7.2.4 Management Principles
- Global Perspective
	- review system design and implementaation
	- consider risk impact
- Forward looking view
	- consider future threats
	- create future plans
- open communication
	- free flow of communication between client and team
- integrated management
	- make risk management integral to project management
- continuous process
		- track risks continuously throughout project
### 7.2.5 Risk Management Paradigm
1. Identify
2. Analyze
3. Plaan
4. Track
5. Control
 6. communicate
## 7.3 Softwaare Quality Assurance
### 7.3.1 Definition
- Planned and systematic actions to provide confidence that product conforms to technical requirements
- management activities to identify quality problems early
### 7.3.2 SQA Components
- Software Quality Control
	- focuses on product
	- activities like
		- ensure delivered software hs minimum faults
		- satisfies user needs
- Softwarae quality engineering
	- focuses on process
	- activities like
		- institute procedures
		- techniques
		- tools for fault free development
### 7.3.3 Main SQA Tools
- development process
	- structured pproch
- reviews and audits
	- early fault detection
- Testing
	- validation and verification
- Metrics
	- Measurement and improvement
- 