- **6 Hours**

[[Chapter 5 Object Oriented Design]]
# 1 Overview of Testing
## 1.1 Definition
- **Software Testing** = process to identify correctness, completeness, and quality of developed software.
- Executing program under positive and negative conditions by manual or automated means.
- Checks specification, functionality, and performance.
## 1.2 Testing = Verification + Validation
| Aspect             | Verification                       | Validation                         |
| ------------------ | ---------------------------------- | ---------------------------------- |
| **Question**       | Are we building the product right? | Are we building the right product? |
| **Focus**          | Conformance to specifications      | Conformance to user needs          |
| **Method**         | Static testing (no code execution) | Dynamic testing (code execution)   |
| **Activities**     | Reviews, walkthroughs, inspections | Black box, white box testing       |
| **Responsibility** | QA team                            | UAT testers, business users        |
## 1.3 Objectives of Software testing
| Objective                    | Description                                        |
| ---------------------------- | -------------------------------------------------- |
| **Uncover Errors**           | Find as many bugs as possible in the product       |
| **Demonstrate Requirements** | Show software matches specifications               |
| **Validate Quality**         | Ensure quality with minimum cost and effort        |
| **Generate Test Cases**      | Create high-quality test cases and effective tests |
## 1.4 Importance of Software Testing
| Reason                      | Description                              |
| --------------------------- | ---------------------------------------- |
| **Confidence**              | Provides confidence in the system        |
| **Identify Weakness**       | Reveals areas needing improvement        |
| **Quality Measurement**     | Establishes degree of quality            |
| **Requirements Validation** | Shows extent requirements are met        |
| **System Understanding**    | Provides understanding of overall system |
| **Usability Proof**         | Proves software is usable and operable   |
## 1.5 Terminology
| Term          | Definition                                                               |
| ------------- | ------------------------------------------------------------------------ |
| **Error**     | Human action producing incorrect result leading to a fault               |
| **Bug**       | Presence of error during software execution                              |
| **Fault**     | State of software caused by an error                                     |
| **Failure**   | Deviation from expected result (an event)                                |
| **Test Data** | Input devised to test the system                                         |
| **Test Case** | Triplet (I, S, O) where I = input, S = system state, O = expected output |
# 2 Conventional vs OO Systems
| Aspect               | Conventional Systems                    | Object Oriented Systems                                |
| -------------------- | --------------------------------------- | ------------------------------------------------------ |
| **Structural Units** | Functions, modules, subsystems          | Classes, objects, groups of classes, subsystems        |
| **Behavior**         | Defined control flow among processes    | Multiple active processes running concurrently         |
| **Dependencies**     | Data dependencies, calling dependencies | Class-to-class dependencies, inheritance, polymorphism |
| **Testing Unit**     | Functions/modules                       | Classes                                                |
# 3 Object Oriented Testing
## 3.1 Concept
- Collection of testing techniques to verify and validate object-oriented software.
- Revolves around fundamental entity called **"class"**.
- Larger systems divided into small, well-defined units (classes) implemented separately.
## 3.2 Testing Levels in OOT
| Level                           | Testing Activities                                                                                                         |
| ------------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| **Requirements Testing**        | Model reviews, prototype walkthroughs, usage scenario testing                                                              |
| **Analysis Testing**            | Model reviews, prototype walkthroughs, usage scenario testing                                                              |
| **Architecture/Design Testing** | Model reviews, walkthroughs, prototype walkthroughs                                                                        |
| **Code Testing**                | Black box, white box, boundary value, class testing, integration testing, coverage testing, inheritance regression testing |
| **System Testing**              | Function testing, installation testing, operations testing, stress testing, support testing                                |
| **User Testing**                | Alpha testing, Beta testing, User Acceptance Testing (UAT)                                                                 |
# 4 Types of Testing
## 4.1 Unit Testing
| Aspect           | Description                                                       |
| ---------------- | ----------------------------------------------------------------- |
| **Definition**   | Testing individual units of source code (function, file, program) |
| **Performed By** | Software developers                                               |
| **Purpose**      | Ensure code meets design and behaves as intended                  |
| **Focus**        | Smallest testable part of code                                    |
## 4.2 Integration Testing
| Aspect           | Description                                            |
| ---------------- | ------------------------------------------------------ |
| **Definition**   | Testing integrated units as a group after unit testing |
| **Performed By** | Testers                                                |
| **Purpose**      | Check data flow between modules                        |
### 4.2.1 Types of Integration Testing:
| Type          | Description                                                                          |
| ------------- | ------------------------------------------------------------------------------------ |
| **Big Bang**  | All modules combined into complete system, then tested                               |
| **Top Down**  | Testing from top to bottom following control flow; higher-level modules tested first |
| **Bottom Up** | Lower-level modules tested first; used to facilitate testing of higher-level modules |
## 4.3 System Testing
| Aspect         | Description                                              |
| -------------- | -------------------------------------------------------- |
| **Definition** | Testing complete integrated system                       |
| **Purpose**    | Evaluate system's compliance with specified requirements |
| **Type**       | Black box testing                                        |
| **Focus**      | Behavior, design, end-user expectations                  |
## 4.4 Acceptance Testing
| Aspect           | Description                                            |
| ---------------- | ------------------------------------------------------ |
| **Definition**   | Testing to verify requirements are met as per delivery |
| **Performed By** | User or customer                                       |
### 4.4.1 Alpha vs Beta Testing:
| Alpha Testing                               | Beta Testing                             |
| ------------------------------------------- | ---------------------------------------- |
| Performed by developers at development site | Performed by customers at their own site |
| White box + black box techniques            | Black box technique only                 |
| Simulated/virtual environment               | Real-time environment                    |
| Absence of targeted end users               | Absence of development/QA team           |
| Not open to market/public                   | Open to market and public                |
| Less user feedback incorporation            | Incorporates user feedback               |
| Used for software applications              | Used for software products               |
# 5 OO Based Testing vs Conventional Testing
| Aspect              | Conventional Testing          | Object Oriented Testing                           |
| ------------------- | ----------------------------- | ------------------------------------------------- |
| **Unit of Testing** | Functions, modules            | Classes                                           |
| **Test Focus**      | Input-process-output view     | Sequences of operations to exercise class states  |
| **Dependencies**    | Data and calling dependencies | Class-to-class, inheritance, polymorphism         |
| **Integration**     | Top-down, bottom-up, big bang | Class integration, inheritance regression         |
| **Reusability**     | Limited test case reuse       | Test cases reusable with inheritance              |
| **Encapsulation**   | Not a factor                  | Affects testing (need to test through interfaces) |
| **Polymorphism**    | Not present                   | Requires testing of dynamic binding               |
## 5.1 Berard's Approach
| Element               | Description                                                  |
| --------------------- | ------------------------------------------------------------ |
| **Unique ID**         | Explicitly identified and associated with class being tested |
| **Purpose Statement** | Clearly stated objective                                     |
| **Testing Steps**     | Detailed steps including:                                    |
|                       | • List of specified states for object being tested           |
|                       | • List of messages/operations to be executed                 |
|                       | • List of exceptions that may occur                          |
|                       | • List of external conditions required                       |
- each test case should adhere to the above conditions
## 5.2 Focus of OO Test Case Design
| Conventional                  | Object Oriented                                  |
| ----------------------------- | ------------------------------------------------ |
| Input-process-output view     | Sequences of operations to exercise class states |
| Algorithmic detail of modules | Appropriate operation sequences                  |
## 5.3 Example
### 5.3.1 ATM System
| Test Case | Description                                        |
| --------- | -------------------------------------------------- |
| TC 1      | Successful card insertion                          |
| TC 2      | Unsuccessful due to wrong angle card insertion     |
| TC 3      | Unsuccessful due to invalid account card           |
| TC 4      | Successful entry of PIN number                     |
| TC 5      | Unsuccessful due to wrong PIN entered 3 times      |
| TC 6      | Successful language selection                      |
| TC 7      | Successful account type selection                  |
| TC 8      | Unsuccessful due to wrong account type for card    |
| TC 9      | Successful withdrawal option selection             |
| TC 10     | Successful amount selection                        |
| TC 11     | Unsuccessful due to wrong denominations            |
| TC 12     | Successful withdrawal operation                    |
| TC 13     | Unsuccessful due to insufficient balance           |
| TC 14     | Unsuccessful due to insufficient cash in ATM       |
| TC 15     | Unsuccessful due to exceeding daily limit          |
| TC 16     | Unsuccessful due to server down                    |
| TC 17     | Cancel after card insertion                        |
| TC 18     | Cancel after card and PIN                          |
| TC 19     | Cancel after language, account, withdrawal, amount |
### 5.3.2 Login Page
| Test Case | Description                                      |
| --------- | ------------------------------------------------ |
| 1         | Test without username and password               |
| 2         | Test with only username                          |
| 3         | Test with only password                          |
| 4         | Test with username and wrong password            |
| 5         | Test with password and wrong username            |
| 6         | Test with correct username and password          |
| 7         | Cancel after entering credentials                |
| 8         | Enter long username/password exceeding limit     |
| 9         | Copy/paste in password field                     |
| 10        | After successful logout, try browser back button |
# 6 Interclass Test Case Design
## 6.1 Concept
- Test case design becomes more complex during integration of object-oriented system.
- Collaboration testing accomplished through:
    - Random methods
    - Partitioning methods
    - Scenario based testing
    - Behavioral testing
## 6.2 Multiple Class Testing Process
| Step  | Description                                                                                     |
| ----- | ----------------------------------------------------------------------------------------------- |
| **1** | For each client class, use list of class operations to generate random test sequences           |
| **2** | Operations send messages to server classes                                                      |
| **3** | For each message, determine collaborator class and corresponding operation in server object     |
| **4** | For each message, determine next level of operations invoked and incorporate into test sequence |
## 6.3 Interclass Test Case Design Methods
### 6.3.1 Random Testing
#### 6.3.1.1 Process
- Generate random sequences of operations across collaborating classes
- Focus on interactions between classes
- Identify sequences that test class interactions
#### 6.3.1.2 Example:
```
Random Sequence:
1. Order.create()
2. Inventory.checkStock(orderItem)
3. Order.addItem(item)
4. Inventory.reserveItem(item)
5. Order.calculateTotal()
6. Inventory.updateStock(item)
```
### 6.3.2 Partition Testing
| Partition Type          | Description                                   | Example (Bank Account)                        |
| ----------------------- | --------------------------------------------- | --------------------------------------------- |
| **By Operation Type**   | Group operations by behavior                  | Creation, modification, deletion, query       |
| **By State**            | Test based on object state                    | Account: new, active, closed, overdrawn       |
| **By Attribute Values** | Test based on attribute ranges                | Balance: positive, zero, negative             |
| **By Collaborator**     | Test interactions with specific collaborators | Account: interacts with Customer, Transaction |
Approach is: to divide test space into categories
#### 6.3.2.1 Example for Account Class
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
### 6.3.3 Scenario Based Testing
- Approach is to create realistic user scenarios that exercise multiple classes
- Example: Library System Scenario
```
Scenario: Member borrows book
1. Member searches for book (Catalog class)
2. System checks availability (Inventory class)
3. Member requests book (Loan class)
4. System creates loan (Loan class)
5. System updates member record (Member class)
6. System updates book status (Book class)
```
### 6.3.4 Behavioral Testing
- Approach is test based on state models of collaborating objects
- Process:
	- Identify states of collaborating objects    
	- Test transitions triggered by messages
	- Verify correct state changes across classes
- Example: ATM System Behavior
```
State: Card Inserted → PIN Entered → Validated → Transaction Selected → Complete
Messages between: ATM, CardReader, BankSystem, Account
```
### 6.3.5 Inheritance Regression Testing
| Consideration          | Description                                             |
| ---------------------- | ------------------------------------------------------- |
| **Inherited Methods**  | Test whether subclass preserves superclass behavior     |
| **Overridden Methods** | Test new behavior and ensure it doesn't break contracts |
| **New Methods**        | Test added functionality                                |
| **Polymorphic Calls**  | Test dynamic binding behavior                           |
- approach is to test subclasses for inherited behavior
## 6.4 Interclass Test Case Template
```
┌─────────────────────────────────────────────────────────────┐
│ TEST CASE ID: IC_XXX                                        │
├─────────────────────────────────────────────────────────────┤
│ CLASSES INVOLVED:                                           │
│ - Primary Class:                                            │
│ - Collaborators:                                            │
├─────────────────────────────────────────────────────────────┤
│ INITIAL STATE:                                              │
│ - Object states before test execution                       │
├─────────────────────────────────────────────────────────────┤
│ TEST SEQUENCE:                                              │
│ 1. Message from Class A → Class B                           │
│ 2. Message from Class B → Class C                           │
│ 3. Response from Class C → Class B                          │
│ 4. Response from Class B → Class A                          │
├─────────────────────────────────────────────────────────────┤
│ EXPECTED RESULT:                                            │
│ - Final states of all objects                               │
│ - Return values                                             │
├─────────────────────────────────────────────────────────────┤
│ EXCEPTIONS:                                                 │
│ - Possible exceptions during execution                      │
└─────────────────────────────────────────────────────────────┘
```
## 6.5 Interclass Test Example: Order Processing
- Classes Involved:
	- `Order` (primary)
	- `Inventory` (collaborator)
	- `Payment` (collaborator)
	- `Shipping` (collaborator)
- Test Sequence:
```
1. Order.create(orderId, customerId)
   → State: Order.new
   
2. Order.addItem(itemId, quantity)
   → Message: Inventory.checkAvailability(itemId, quantity)
   → Response: Inventory.available (true)
   → State: Order.pending
   
3. Order.processPayment(paymentDetails)
   → Message: Payment.authorize(amount)
   → Response: Payment.approved
   → State: Order.paid
   
4. Order.confirm()
   → Message: Inventory.reserveItems(orderItems)
   → Message: Shipping.createShipment(orderId)
   → Response: Shipping.confirmed
   → State: Order.confirmed
```
# 7 Summary
|Topic|Key Points|
|---|---|
|**Verification vs Validation**|Verification: building right? (static); Validation: building right product? (dynamic)|
|**Importance of Testing**|Confidence, weakness identification, quality measurement, requirements validation|
|**OOT vs Conventional**|Class as unit; state-based testing; inheritance, polymorphism considerations|
|**Testing Levels**|Unit → Integration → System → Acceptance|
|**Integration Types**|Big Bang, Top Down, Bottom Up|
|**OOT Strategies**|Fault-based, scenario-based, random, partition, behavioral|
|**Test Case Design**|State-based sequences; collaboration testing|
|**Interclass Testing**|Multiple class collaboration; random, partition, scenario, behavioral methods|


[[Chapter 7 Managing Object Oriented Software Engineering]]