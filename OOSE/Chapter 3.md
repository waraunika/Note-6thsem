# 3.1 Class Relationship
- a relationship is a connection among things.
- in Object Oriented (OO) modeling, the 3 most important relationships are dependencies, generalizations and associations
## 3.1.A Dependencies
- relationship that states that one thing (for example class Window) uses the information and services of another thing (for example, class Event), but not necessarily the reverse
- graphically, a dependency is rendered as a dashed directed line, directed to the thing being depended on.
- figure:
  ![[Pasted image 20260208112349.png]]
- Most often we will use dependencies between classes to show that one class uses operations from another class or it uses variables or arguments typed by the other class.
- this is very much a using relationship
	- if the used class changes, the operation of the other class may be affected as well,
	- because the used class may now present a different interface or behavior
- in the UML, we can also create dependencies among many other things, especially notes and packages.
- unidirectional relationship
- we can use dependency relationships in class diagrams, component diagrams, deployment diagrams, and use case diagram to indicate that a change to the supplier might require a change to the client
- typically, dependency relationships do not have names
## 3.1.B Generalizations
- relationship between a general kind of thing (called the superclass or parent) and a more specific kind of thing (called subclass or child)
- graphically, generalization is rendered as a solid directed line with a large unfilled triangular arrowhead, pointing to the parent, as shown below
- use generalizations when we want to show parent/child relationships
- figure:
  ![[Pasted image 20260208112711.png]]
## 3.1.C Associations
- structural relationship that specifies that objects of one thing are connected to another object
- given an association connecting two classes, we can relate objects of one class to objects of the other class.
- an asosciation that oconects exactly 2 classes is called a binary association.
- we can have associations that connect mroe than 2 classes, called n-ary associations
- graphically, an association is rendered as a solid line connecting the same or different classes
- use associations when we want to show structural relationships
- beyond this basic form, there are four adornments that apply to associations
	- name
	- role
	- multiplicity
	- aggregation
### 1.C.i Name
- an association can have a name, and we use that name to describe the nature of the relationship.
- So that there is no ambiguity about its meaning
- Also we can give a direction to the name by providing a direction triangle that points in the direction we intend to read the name.
- figure:
  ![[Pasted image 20260209080653.png]]
### 1.C.ii Role
- When a class participates in an association, it has a specific role that it plays in that relationship
	-  a role is just the face the class at the far end of the association presents to the class at the near end of the association
- we can explicitly name the role a class plays in an association.
- the role played by an end of an association is called an end name
- in figure:
	- the class Person playing the role of employee is associated with the class Company playing the role of employer.
	- ![[Pasted image 20260209080849.png]]
- the same class can play the same or different roles in other associations
### 1.C.iii Multiplicity
- important for us to state how many objects may be connected across an instance of an association.
- this "how many" is called the multiplicity of an association's role
- it represents a range of integers specifying the possible size of the set of related objects.
- it is written as an expression with a minimum and maximum value, which may be the same
- two dots are used to separate the minimum and maximum values.
- the number of objects must be in the given range.
- we can show a multiplicity as:
	- exact one (1)
	- zero or one (0..1)
	- many (0..\*), or one or more (1..\*)
	- integer range (such as 2..5)
	- exact number (3..3 for 3)
- figure:
	- ![[Pasted image 20260209081206.png]]
	- Person 1..* and * Company
	- each company object has an employee one or more person objects (multiplicity 1..\*)
	- each person has an employer zero or more company objects (multiplicity \*, which is equivalent to 0..\*).
### 1.C.iv Aggregation
- plain aggregation between two classes represents a structural relationship between peers, meaning that both classes are conceptually at the same level, no one more important than the other
- sometimes we will want to model a "whole/part" relationship, in which one class represents a larger thing (the "whole"), which consists of smaller things (the "parts)
- this kind of relationship is called aggregation, which represents a "has-a" relationship meaning that an object of the whole has objects of the part.
- an aggregation association appears as a solid line, with an unfilled diamond at the association end,
	- which is connected to the classifier that represents the aggregate.
- figure:
	- ![[Pasted image 20260209082121.png]]
	- ![[Pasted image 20260209082131.png]]
	- let us consider an example of a car and a wheel
	- a car needs a wheel to function correctly, but a wheel doesn't always need a car and can also be used with bike, bicycle, or any other vehicles
	- wheel object is meaningful even without the car object.
	- such relationship is called UML Aggregation relation
### 1.C.v Composition
- A composition association relationship represents a whole-part relationship and is a form of aggregation
- A composition association relationship specifies that the lifetime of the part of classifier is dependent on the lifetime of the whole classifier.
- in a composition association relationship, data usually flows in only direction
  - from whole classifier to part classifier
- for example, a composition association relationship connects a Student class with a Schedule class, which means that if we remove the student, the schedule is also removed.
- We can rename any association to describe the nature of the relationship between the two classifiers.
- As the following figure illustrates, a compsition association relationship appears as a solid line with a filled diamond at the association end, which is connected to the whole, or composite, classifier.
- figure: (slide 133)
### 1.C.vi Association vs. Aggregation vs. Composition
- 1st
  - Association is the most general (m:n) relationship.
  - Aggregation is a stronger relationship where one is a part of the other.
  - Composition is even stronger than aggregation, ties the lifecycle of the part and the whole together.
- 2nd
  - Association relationship can be reflexive (objects can have relation to itself)
  - but aggregation cannot be reflexive.
  - aggregation is anti-symmetric (If B is a part of A, A can't be a part of B).
- 3rd
 - Composition has the property of exclusive aggregation i.e. an object can be a part of only one composite at a time.
 - for example, a frame belongs to exactly one Window, whereas in simple aggregation, a part may be shared by several objects.
 for example, a Wall may be a part of one or more Room objects.
- 3rd
  - in addition, in composition, the whole has the responsibility for the disposal of all its parts, i.e. for their creation and destruction.
- 4th
  - for example, when a Frame object is created, it has to be attached to an enclosing Window.
  - Similarly, when the Window is destroyed, it must in turn destroy its Frame parts.
# 3.2 Conceptual Model of UML
- to understand the UML, we need to form a conceptual model of the language, and this requires learning three major elements:
	- The UML's basic building blocks.
	- The rules that dictate how those building blocks may be put together and
	- some common mechanisms that apply throughout the UML
## 3.2.A Basic Building Blocks of the UML
- The vocabulary of the UML encompasses three kinds of building blocks:
### 2.A.i Things
- 4 kinds of things in the UML
1. **Structural Things**
	- These are the nouns of UML models
	- there are the mostly static parts of a model
	- represent element that are either conceptual or physical
	- collectively the structural things are called classifiers
	- Class, interface, collaboration, use case, component, node, etc. are example of structural things in UML.
2. **Behavioral Things**
	- These are the dynamic parts of UML models.
	- these are the verbs of a model,
	- representing behavior over time and psace
	- in all, there are three primary kinds of behavioral things:
		- interaction, state machine and activity
3. **Grouping Things**
	- These are the organizational parts of UML models
	- these are the boxes into which a model can be decomposed
	- there is one primary kind of grouping thing called packages
4. **Annotational Things**
	- These are explanatory parts of UML models.
	- comments you may apply to describe illuminate and remark about any element in a model
	- there is one primary kind of annotational thing called a note.
	- Graphically, a note is rendered as a rectangle with a dog eared corner together with a textual or graphical comment, as in figure below:
	  ![[Pasted image 20260207224041.png | 400]]
### 2.A.ii Relationships
Four kinds of relationships in the UML:
#### A.ii.a Dependency
#### A.ii.b Association
#### A.ii.a Generalization
#### A.ii.a Realization
### 2.A.iii Diagrams
- a diagram is the graphical presentation of a set of elements, most often rendered as a connected graph of vertices (things) and paths (relationships)
- we draw diagrams to visualize a system from different perspectives, so a diagram is a projection into a system.
- the uml includes thirteen kinds of diagrams
#### A.iii.a Class Diagram
##### iii.a.1 Concept
- class is description of a set of objects that share the same attributes, operations, relationships, and semantics
- graphically, a class is rendered as a rectangle.
- notation permits you to visualize an abstraction apart from any specific programming language and in a way that lets you emphasize the most important parts of an abstraction: its name, attributes and operations
- figure:
  ![[Pasted image 20260208104157.png]]
##### iii.a.2 Components
1. Class Name
	- An attribute is a named property of a class that describes a range of values that instances of the property may hold.
	- a name is a textual string
	- that name alone is known as a simple name
	- a qualified name is the class name prefixed by the name of the package in which that class lives
	- a class maybe drawn showing only its name as shown below
	- symbols:
	  ![[Pasted image 20260208104404.png]]
2. Attributes
	- named property of a class that describes a range of values that instance sof the property may hold
	- a class may have any number of attributes or no attributes at all
	- an attribute represents some property of the thing you are modeling that is shared by all objects of that class
	- for example: every wall has a height, width, and thickness
	- you might model our customers in such a way that each has a name, address, phone number and date of birth
	- an attribute may be text, just like a class name
	- in practice an attribute name is a short noun or noun phrase that represents some property of its enclosing class.
	- extra info:
		- at the most abstract level, we simply write each attribute's name
		- usually enough information for the average reader to understand the intent of our model.
		- however, we can also specify the visibility, scope and multiplicity of each attribute
		- we can also specify the type, initial value, and changeability of each attribute
		- for example, legal attribute declarations
			- origin <- Name only
			- + origin <- Visibility and name
			- origin: Point <- Name and type
			- name: string\[0..1] <- Name, type, and multiplicity
			- origin: Point = (0, 0) <- Name, type and initial value
			- id: Integer \{readonly} <- Name and property
		- unless otherwise specified, attributes are always changeable. we can use the readonly property to indicate that the attribute's value may not be changed after the object is initialized
	- symbols:
	  ![[Pasted image 20260208104526.png]]
	- we can further specify an attribute by stating its type and possibly a default initial value, as shown below:
	  ![[Pasted image 20260208104553.png]]
3. Operations
	- implementation of a service that can be requested from an object of the class to affect behavior
	- in other words, an operation is an abstraction of something you can do to an object that is shared by all objects of that class.
	- operations may be drawn showing only their names
	- extra nifo:
		- at the most abstract level, wee simply write each operation's name
		- however, we can also specify the visibility and scope of each operation.
		- we can also specify the parameters, return type, concurrency semantics, and other properties of each operation
		- collectively, the name of an operation plus its parameters (including its return type, if any) is called the operation's signature
	- For example: the following are legal declarations:
		- display <- Name only
		- + display <- visibility and name
		- set(n: Name, s: String) <- Name and parameters
		- getID(): Integer <- Name and return type
		- restart() {guarded} <- Name and property
	 - figure:
	  ![[Pasted image 20260208104825.png]]
	- an operation name may be text
	- in practice, an operation name is a short verb or verb phrase that represents some behavior of its enclosing class
4. Responsibilities
	- contract or obligation of a class
	- e.g., 
		- a Wall class is responsible for knowing about height, width, and thickness
		- a FraudAgent class, for a credit card application, is responsible for processing orders and determining if they are legitimate, suspect or fraudulent
		- a TempSensor class is responsible for measuring temperature and raising an alarm if the temperature reaches a certain point.
	- graphically, responsibilities can be drawn in a separate compartment at the botto of the class icon.
	- figure:
	  ![[Pasted image 20260208105130.png]]
5. Advance class
	- classifiers (and classes) have a number of advanced features beyond simpler properties of attributes and operations
	- we can model multiplicity, visibility, signature, polymorphism and other characteristics
	- we can model the semantics of a class so that you can state its meaning to whatever degree of formality you like
	- earlier it was sufficient to include a customer class that carries out certain responsibilities
	- as we refine architecture and move to construction, we'll have to decide on a structure for the class (its attributes) and a behavior (its operations) that are sufficient and necessary to carry out those responsibilities
	- finally, as we evolve to the executable system, we'll need to model details, such as the visibility of individual attributes and operations, the concurrency semantics of the class as a whole and its individual operations, and the interfaces the class realizes
	- the uml provides a representation for a number of advanced properties
	- this notation permits us to visualize, specify, construct and document a class to any level of details we wish.
	- figure:
	  ![[Pasted image 20260208105552.png]]
	- UML also provides several other kinds of classifiers to help us model
		1. interface
			- collection of operations that are used to specify a service of a class or a component
			- figure:
			  ![[Pasted image 20260208105648.png]]
		2. Datatype
			- a type whose values are immutable
			- including primitive built-in types (such as numbers and string) and enumeration types (such as boolean).
			- figure:
			  ![[Pasted image 20260208105732.png]]
		3. Association
			- A description of a set of links, each of which relates two or more objects
		4. Signal
			- the specification of an asynchronous message communicated between instances
		5. Component
			- a modular part of a system that hides its implementation behind a set of external interfaces
			- figure:
			  ![[Pasted image 20260208105843.png]]
		6. Node
			- a physical element that exists at run time and that represents a computational resource generally having atleast some memory and often processing capabilities.
			- symbol:
			  ![[Pasted image 20260208110136.png]]
		7. Use Case
			- a description of a set of a sequence of actions, including variants
			- that a system performs that yields an observable result of value to a particular actor
			- symbol:
			  ![[Pasted image 20260208110147.png]]
		8. Subsystem
			- a component that represents a major part of a system
			- symbol:
			  ![[Pasted image 20260208110155.png]]
6. Visibility
	- the visibility of a feature specifies whether it can be used by other classifiers
	- when we specify the visiblity of a classifier's features, we generally want to hide all its implementation details and expose only those features that are necessary to carry out the responsibilities of the abstraction.
	- we specify any of four levels of visiblity
		1. public
			- any outside classifiers with visibility to the given classifier can use the feature
			- specified by prepending the symbol +
		2. protected
			- any descendant of the classifier can use the feature
			- specified by prepending the symbol #
		3. private
			- only the classifier itself can use the feature;
			- specified by prepending the symbol -
		4. package
			- only classifiers declared in the same package can use the feature
			- specified by prepending the symbol ~
	- Figure:
	  ![[Pasted image 20260208110422.png]]
7. Multiplicity
	- the number of instances a class may have is called its multiplicity
	- we can specify the multiplicity of a class my writing a multiplicity expression in the upper-right corner of the class icon
	- for example, NetworkController is a singleton class (it can have exactly one instance)
	- similarly, there are exactly three instance of the class ControlRod in the system
	- Multiplicity applies to attributes, as well.
	- we can specify the multiplicity of an attribute by writing a suitable expression in brackets just after the attribute name.
	- figure:
	  ![[Pasted image 20260208110654.png]] 
8. Abstract, Root, Leaf and Polymorphic elements
	- to represent abstract classes for which we cannot create instances, the class name is written in italics in UML
	- to represent abstract methods, we write the operation signature in italics.
	- We can also represent leaf and root classes in UML. 
	- a class which has no child classes is known as leaf class.
	- such a class can be represented by writing leaf as a property under the class name
	- in class hierarchies it is common for the classes to have methods with same signatures
	- this feature of declaring methods with same signatures is known as polymorphism
	- such methods are represented in UML by writing their signatures in italics.
	- figure:
	  ![[Pasted image 20260208111530.png]]
##### iii.a.3 Example
1. Library management system
	- Classes
		- Library management system class: 
			- manages all operations of Library manager system
			- it is central part of organization for which software is being designed.
		- User Class - It manages all operations of user
		- Librarian Class - It manages all operations of Librarian
		- Book Class - It manages all operations of books. basic building block of system
		- account class - it manages all operations of account
		- library database class - it manages all operations of library database
		- staff class -manages all operations of staff
		- student class - it manages all operations of student
	- Attributes
		- Library Management system attributes: usertype, username, password
		- user attributes - name, id
		- librarian attributes - name, id
		- librarian attributes - name, id, password, searchstring
		- book attributes - title, author, isbn, publication
		- account attributes - no_borrowed_books, no_reserved_books, no_returned_books, no_lost_books, fine_amount
		- library database attribtues - list_of_books
		- staff class attributes - dept
		- student class attributes - class
	- Methods
		- library management system methods - Login(), Register, Logout()
		- user methods - Verify(), CheckAccount(), get_book_info()
		- Librarian Methods - Verify_librarian(), search()
		- book methods - show duedate(), reservation_status(), feedback(), book_request(), renew_info()
		- account methods - calculate_fine()
		- library database methods - add(), delete, update(), display(), search()
#### A.iii.b Object Diagram
#### A.iii.c Component Diagram
#### A.iii.d Composite Structure Diagram
#### A.iii.e Use Case Diagram
##### iii.e.1 Concept
- diagram that shows a set of use cases and actors and their relationships
- represents user's interaction with the system
- like all other diagrams, use case diagrams may contain notes and constraints
- we may want to place instances of use cases in our diagrams, when we want to visualize a specific executing system
- Components:
	- Actors
	- Use Case
	- System Boundary
	- Relationship
- Functions:
	- helps to identify, clarify and organize the system requirements
	- describes the behavior of the target system from an external point of view
	- helps in understanding its components
	- depict who (or what) interacts with the system
	- show what outside world wants the system to do.
##### iii.e.2 Components
1. Actor
	- someone or something that must interact with the system under development
	- e.g. figure:
	  ![[Pasted image 20260208073322.png]]
	- not part of the system, is external to it
	- single actor may perform more than 1 functionality (use case)
	- function:
		- input information to the system
		- receive information from the system
		- input to and out from the system
	- find who is actor by asking:
		- who uses the system?
		- who installs the system
		- who starts up the system
		- what other system use this system
		- who gets the information to the system
	- categories
		- **principle**: who uses the main system functions
		- **secondary**: who takes care of administration and maintenance
		- **external hardware**: the hardware devices which are part of application domain and must be used
		- **other system**: the other system with which the system must interact
2. Use Case
	- represents functionality of a system which are the specific roles played by the actors within and around the system
	- e.g. figure:
	  ![[Pasted image 20260208073716.png | 400]]
	- how to find use cases:
		- what functions will the actor want from the system
		- does the system store information?
			- if yes, then which actors will perform CRUD operation?
		- does system need to notify and actor about changes in its internal state?
	- generic format for documenting a use case
		- pre condition: if any
		- use case: name of the use case
		- actor: list of actors, indicating who initiates the use case
		- purpose: intention of the use case
		- overview: description
		- type: primary/secondary
		- post condition: if any
	- example: description of opening a new account in the bank
		- use case: open new account
		- actors: customer, cashier, manager
		- purpose like to have a new saving account
		- description: 
			- a customer arrives in the bank to open the new account
			- customer requests for the new account form, fill the form and submit
				- along with the minimal deposit
			- at the end of complete successful process customer receives the passbook
3. System Boundary
	- helps to identify what is an external vs internal
	- external environment is represented only by actors
	- represented as a rectangle
	- e.g., figure:
	  ![[Pasted image 20260208074117.png]]
4. Relationship
	- communicates:
		- relationship between use case and actor
	- include/extend:
		- relationship between two use cases
	- notation to show the include and extend relationship: figure:
	  ![[Pasted image 20260208074250.png]]
	- \<\<include>> relationship
		- may contain the functionality of another use case
		- used to show how the system can use a pre-existing components
		- an include relationship is a relationship in which one use case (the base use case, BUC) includes or uses the functionality of another use case (the inclusion use case, IUC)
		- represented as a dashed line with an open arrow pointing from the BUC to IUC.
		- keyword \<\<include>> is attached to the connector arrow.
		- format, figure:
		  ![[Pasted image 20260208074501.png]]
		- e.g., figure:
		  ![[Pasted image 20260208074521.png]]
		- the figure illustrates restaurant order management system that provides customer with the option of placing orders as well as tracking orders.
		- This behavior is modeled with 2 BUC called *PlaceOrder* and *TrackOrder* that has an IUC called *ValidateUser*.
		- the *ValidateUser* use case is a separate inclusion use case because it contains behaviors that several other use cases in the system use.
		- That include relationship points from the *PlaceOrder* & *TrackOrder* use case to the *ValidateUser* use case indicate that
			- *PlaceOrder* & *TrackOrder* use cases always includes the behaviors of the *ValidateUser* use case
	- \<\<extend>> relationship
		- used to show optional behavior, which is required only under certain conditions.
		- typically used in exceptional circumstances
		- represented as dotted line labeled \<\<extend>> with an arrow toward the base case.
		- format, figure:
		  ![[Pasted image 20260208074941.png]]
		- example, figure:
		  ![[Pasted image 20260208075001.png]]
			- here, *OrderPizza* & *Help* use cases are optional to BUC PlaceOrder
	- Key difference between extend and include:
			
| Particulars                                    | Included use case | Extending use case |
| ---------------------------------------------- | ----------------- | ------------------ |
| is this use case optional                      | No                | Yes                |
| Is the BUC complete without this use case?     | No                | Yes                |
| Is the execution of this use case conditional? | No                | Yes                |
| Does this use case change the behavior of BUC? | No                | Yes                |
- Association
	- it indicates the communication between an actor and a use case
	- it is represented by a solid line
- Generalization
	- relationship between general use case and a special use case
	- generalization relationships can be used to relate use cases.
		- use cases can have common behaviors that other use cases (i.e., child use cases) can modify by adding steps or refining others
	- represented by a line with a triangular arrow head toward the parent use case.
	- e.g., figure:
	  ![[Pasted image 20260208075406.png]]
	- e.g., figure:
	  ![[Pasted image 20260208075425.png]]
		- figure shows the use case for purchasing various tickets
		- purchase ticket contains the basic steps necessary for purchasing tickets
			- while the child use cases, (Purchase Concert Ticket, Purchase Theater Ticket, Purchase Baseball Ticket) specialize Purchase Ticket for specific kind of tickets being purchased.
- Example: Withdraw money from ATM
	- Description
		- Use case Scenario: Withdraw money from ATM
		- Participating actors:
			- Customer
			- ATM Machine
			- Bank
		- Preconditions:
			- Network connection is active
			- ATM has available cash
		- Flow of events:
			- Bank customer inserts ATM card and enters PIN
			- Customer is validated
			- ATM displays actions available on ATM unit 
			- Customer selects withdraw cash
			- ATM prompts the account
			- customer selects account
			- ATM prompts amount
			- customer enters desired amount
			- information sent to Bank, inquiring if sufficient funds/allowable withdrawal limit
			- money is dispensed and receipt prints
	- Figure:
	  ![[Pasted image 20260208080100.png]]
- Example: Library management System
	- figure:
	  ![[Pasted image 20260208080124.png]]
#### A.iii.f Sequence Diagram
##### iii.f.1 Concept
- interaction diagram
- shows message exchanged or interaction between objects in the system
- mainly emphasizes on time ordering of messages between objects
- used to illustrate the dynamic view of the system
##### iii.f.2 Components
1. Object/Participants
	- diagram is made up of collection of participants or objects
	- participants are system parts that interact with each other
	- participants interact with each other by sending and receiving message
	- the object is represented as:
	  ![[Pasted image 20260208081102.png]]
2. Lifeline
	- represents the existence of an object over a period of time
	- represented by vertical dashed line
	- most objects that appeared in Interaction diagram will be in existence for the duration of an interaction.
	- So these objects are aligned at the top of diagram with their lifeline from top to bottom of diagram
	- figure:
	  ![[Pasted image 20260208081333.png]]
3. Activation bar
	- represented by tall thin rectangle
	- can be marked by a written message
	- also called focus of control
	- shows period of time during which an object is performing action or operation
		- the top of rectangle is aligned with start of the action
		- bottom is aligned with its completion
	- figure
	  ![[Pasted image 20260208081346.png]]
4. Messages:
	- Messages can flow in whatever direction required for interaction (L -> R or R -> L)
	- the messages on sequence diagram are specified using an arrow from participant that wants to pass the messages to the participant that receive the messages
	- the interaction in a sequence diagram between the objects can be shown by using messages.
	- Types:
		1. Asynchronous message
			- It is a messaga where the sender is not blocked and can continue executing
			- representing by solid line with open arrowhead
			- figure:
			  ![[Pasted image 20260208081544.png]]
		2. Synchronous message
			- message where the sender is blocked and waits until the receiver has finished processing of message
			- when invoked, the caller waits for the receiver to return from the message invocation
			- represented by solid line with filled arrowhead.
			- figure:
			  ![[Pasted image 20260208081631.png]]
		3. Reflexive message/ self message
			-  if the object sends the message to itself
			- represented by solid line with loops the lifeline of object.
			- figure:
			  ![[Pasted image 20260208081732.png]]
		4. Return messages
			- used at the end of activation bar to show that control flow of activation returns to the participant that pass the original message
			- represented by dashed line from receiver to sender
			- figure:
			  ![[Pasted image 20260208081820.png]]
		5. Create messages
			- used to create object during interaction
			- object can be created by using \<\<create>> to indicate the timing of creation
			- figure:
			  ![[Pasted image 20260208081858.png]]
		6. Destroy messages
		- used to destroy the objects during interactin
		- objects can be terminated using \<\<destroy>> which points to an "X"
		- indicates that the object named message is terminated
		- object destruction is avoided unless memory management is critical
		- figure:
		  ![[Pasted image 20260208082013.png]]
5. Time
	- about ordering, not duration
	- important factor
	- time on sequence diagram starts at top of the page just below the object and then progress down the page
	- describes the order in which interaction takes place
	- figure:
	  ![[Pasted image 20260208082152.png]]
6. Event
	- Event is created while sending/receiving message 
	- when interaction takes place, events are called as built in blocks for messages and signals
	- can be referred as smallest part of an interaction and event can occur at any given point in a time.
	- figure:
	  ![[Pasted image 20260208082300.png]]
7. Control Information
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
	- consider drawing several diagrams for modeling complex scenarios
	- don't use sequence diagrams for detailed modeling of algorithms
		- done better by activity diagrams, pseudo code or state charts
##### iii.f.3 Example
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
#### A.iii.g Communication Diagram
- aka Collaboration Diagram
- show a particular sequence of messages exchanged between a number of objects
- sequence diagram highlight more of temporal aspect in timely manner
	- no need to number messages
- collaboration diagram, temporal aspect can be shown by numbering interactions with sequential labels
- used to show the time ordering among messages
- Notations:
  ![[Pasted image 20260208083956.png]]
- Example:
  ![[Pasted image 20260208084010.png]]
- 2 main feature that distinguish them sequence diagram
	- path:
		- attach a path stereotype to far end of a link, to indicate how one object is linked to another
		- link could be \>\> local$\cdot$d indicating that the designated object is local to the sender
		- typically we will only need to render the path of the link explicitly for local, parameter, global, and self but not association paths
	- sequence number
		- to indicate the time order of a message, we prefix the message with a number
			- start with message numbered 1
		- increase monotonically for each new message in control flow
		- to show nesting, we use Dewey decimal numbering
			- 1 is 1st message
			- 1.1 is first message nested in message 1
			- 1.2 is second message nested in message 1 and so on
		- we can show nesting to an arbitrary depth
		- along the same link, we can show many message (possible being sent from direction direction)
		- each will have a unique sequence number
- illustrate in a graph or network format
- objects can be placed anywhere on the diagram
- example:
	- collaboration diagram for bookRenew use case
	  ![[Pasted image 20260208084541.png]]
	- collaboration diagram for makePayment
	  ![[Pasted image 20260208084559.png]]
		- read as:
		1. message makePayment is sent to instance of Register
			- sender is not identified
		2. Register instance sends the makePayment message to a Sale instance
		3. Sale instance creates an instance of a Payment
- Link
	- connection path between two objects
	- indicates form of navigation and visibility between the objects is possible
	- link is an instance of an association
		- e.g., there is a link or path of navigation from a register to a sale, along which messages may flow, such as makePayment message
	- figure:
	  ![[Pasted image 20260208085017.png]]
- Messages
	- each message between objects is represented with a message expression and small arrow indicating the direction of the message
	- many messages may flow along this link
	- a sequence number is added to show the sequential order of messages in the current thread of control
	- figure:
	  ![[Pasted image 20260208085031.png]]
	- Message to "self" or "this"
		- a message can be sent fro an object to itself.
		- illustrated by a link to itself, with messages flowing along the link.
		- figure:
		  ![[Pasted image 20260208101452.png]]
- Creation of instances
	- any message can be used to create an instance, but there is a convention in UML to use a message named *create* for this purpose.
	- if another (perhaps less obvious) message name is used, the message may be annotated with a special feature called a UML stereotype, like so: \<\<create>>
	- the create message may include parameters, indicating the passing of initial values.
	- UML property {new} may be optionally be added to the instance box to highlight the creation.
	- figure:
	  ![[Pasted image 20260208101735.png]]
- Conditional Messages:
	- shown by following a sequence number with a conditional clause in square brackets, similar to an iteration clause.
	- message is only sent if the clause evaluates to be true.
	- figure:
	  ![[Pasted image 20260208101952.png]]
- Mutually exclusive conditional pahts
	- if it is necessary to modify the sequence expressions with a conditional path letter.
	- the first letter used is a by convention.
	- figure states that either 1a or 1b could execute after msg1.
	- both are sequence number 1 since either could be the first internal message.
	- not that subsequent nested messages are still consistently prepended with their outer message sequence.
	- thus 1b. 1 is nested message within 1b.
	- figure:
	  ![[Pasted image 20260208102136.png]]
- Iteration or looping
	- if the details of the iteration clause are not important to the modeler, a simple '\*' can be used.
	- figure:
	  ![[Pasted image 20260208102221.png]]
- example of sequence diagram:
  ![[Pasted image 20260208102244.png]]
- another one:
  ![[Pasted image 20260208102300.png]]
- another one:
  ![[Pasted image 20260208102313.png]]
#### A.iii.h State Diagram
#### A.iii.i Activity Diagram
##### iii.i.1 Concept
- visually represents a series of actions or flow of control in a system similar to flowchart
- activities modeled can be sequential and concurrent
- in both cases, an activity diagram will have a beginning (initial state) and an end (final state)
- and in between them, series of actions to be performed by the system.
##### iii.i.2 Symbols
1. Initial state or start point
	- small circle followed by an arrow represents the initial action state or the start point for any activity diagram.
	- symbol:
	  ![[Pasted image 20260208102537.png]]
2. activity or action state
	- an activity represents execution of an action or performing some operation.
	- represented using a rectangle with rounded corners.
	- symbol:
	  ![[Pasted image 20260208102905.png]]
3. action flow
	- aka edges and paths
	- illustrate the transitions from one action state to another
	- usually drawn with an arrowed line
	- symbol:
	  ![[Pasted image 20260208102622.png]]
4. object flow
	- refers to creation and modification of objects by activities
	- an object flow arrow from an action to an object means that the action creates or influences the object
	- an object flow arrow from an object to an action indicates that the action state uses the object.
	- symbol:
	  ![[Pasted image 20260208102746.png]]
5. decision and branching
	- a diamond represents a decision with alternate paths
	- when an activity requires a decision prior to moving on to the next activity, add a diamond between 2 activities
	- the outgoing alternates should be labeled with a condition or guard expression.
	- one of the path can be labeled as 'else'
	- symbol:
	  ![[Pasted image 20260208103010.png]]
6. Final state or End Point
	- an arrow pointing to a filled circle nested inside another circle represents the final action state.
	- symbol:
	  ![[Pasted image 20260208103039.png]]
7. Synchronization
	- a fork node is used to split a single incoming flow into multiple concurrent flows.
	- represented as a straight, slightly thicker line
	- a join node joins multiple concurrent flows back into a single outgoing flow
	- a fork and join mode used together are often referred to as synchronization.
	- symbol:
	  ![[Pasted image 20260208103232.png]]
8. Fork
	- used to split a single incoming flow into multiple concurrent flows
	- represented as straight, slightly thicker line in an activity diagram.
	- symbol:
	  ![[Pasted image 20260208103304.png]]
9. Join
	- joins multiple concurrent flows back into a single outgoing flow.
	- symbol:
	  ![[Pasted image 20260208103340.png]]
10. Time event
	- refers to an event that stops the flow for some amount of  time
	- represented by an hourglass.
	- symbol:
	  ![[Pasted image 20260208103430.png]]
	  ![[Pasted image 20260208103438.png]]
11. Swimlanes
	- when modeling workflows of business processes, to partition the activity states on an activity diagram into groups, each group representing the business organization responsible for those activities
	- in UML, each group is called a swimlane, because, visually, each group is divided from its neighbor by a vertical solid line.
	- a swimlane specifies a locus of activities
	- each swimlane has a high-level responsibility for part of overall activity of an activity diagram, and each swimlane may eventually be implemented by one or more classes
	- in an activity diagram partitioned into swimlanes, every activity belongs to exactly one swimlane, but transitions may cross lanes.
##### Example
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
#### A.iii.j Deployment Diagram
#### A.iii.k Package Diagram
#### A.iii.l Timing Diagram
#### A.iii.m Interaction Overview Diagram
# 3.3 Class Diagram
# 3.4 Advanced Relationship
# 3.5 Advanced Relationship
# 3.6 Interface
# 3.7 Object Diagram
# 3.8 Interactions
# 3.9 Use Cases
# 3.10 Use Case Diagram
# 3.11 Interaction Diagram
# 3.12 Activity Diagram State Chart Diagram
# 3.13 Component and Components Diagram
# 3.14 Deployment Diagram


# 3.15 Examples
### 3.15.A Use Case:
1. A coffee vending machine dispenses coffee to customers. Customers order coffee by selecting a recipe from a set of recipes. Customers pay using coins. Change is given back if any to the customer. The service staff loads ingredients into machine. The service staff can also add a recipe by indicating name of coffee, units of coffee powder, milk, sugar, water and chocolate to be added as well as the cost of coffee.
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
2. Restaurant order system
	- figure:
	  ![[Pasted image 20260208080550.png]]
3. Banking Application
	- figure:
	  ![[Pasted image 20260208080733.png]]
4. 
