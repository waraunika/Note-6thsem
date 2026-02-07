# 1.1 Introduction to Software Engineering
## 1.1.A Concept
### 1.A.i Software
- is more than just a program code
- is an executable code, which serves some computational purpose.
- considered to be a collection of executable programming code, associated libraries and documentations.
- when made for a specific requirement is called software product.
- may be developed fro a particular customer, or may be developed for a general market
### 1.A.ii Engineering
- is all about developing some quality products by using some well-defined, scientific principles and standard within the specified budget and time.
### 1.A.iii Definition
- Hence, software engineering is defined as a branch of computer science which is associated with development of quality software using well-defined scientific principles, methods and procedures.
- outcome of software engineering is an efficient and reliable software product that supports over the long term.
- mainly used for large projects based on software systems rather than single programs or applications.
- The main goal of software engineering is to develop software application for improving the quality, budget and efficiency.
---
## 1.1.B Types of Software
### 1.B.i Application Software
#### B.i.a Generic (Packaged) Software
- application software designed to fulfill the needs of large group of users is known as generic or packaged software
- e.g., MS-Word, Adobe Reader, MS-Excel
#### B.i.b Tailored (Specific) Software
- application software designed to fulfill the needs of a particular user/organization is known as tailored/specific software
- e.g., software used in department stores, hospitals, schools, etc.
### 1.B.ii System Software
- software that can directly control the hardware of the computer
- e.g., video driver, audio driver
### 1.B.iii Utility Software
- small software that usually performs some useful tasks is known as utility software
- e.g., Win Zip, JPEG Compressor, PDF merger, etc.
---
---
# 1.2 Software processes and software process models
## 1.2.A Software Processes
- collection of activities, actions and tasks that are performed when some work product is to be created
- process is not rigid description for how to build computer software, rather
- it is an adaptable approach that enables people doing the work to pick and choose the appropriate set of work actions and tasks.
- road map followed to build a product or system through a series of predictable step is called software process.
- it is a framework for the activities, actions, and tasks required to build high-quality software.
- done by: software engineers.
- managed/adapted by: managers
- people who have requested the software have a say in the process of defining, building, and testing it.
- its important because it provides, path, stability and control over project.
### 2.A.i Software Development Life Cycle
- process used by software industry to design, develop and test high quality software.
- aims to produce a high-quality software that meets or exceeds customer expectations, reaches completion within times and cost estimates.
- also called a software development process.
- is a framework defining tasks performed at each step in the software development process.
- consists of a detailed plan describing how to develop, maintain, replace and alter or enhance specific software.
- the life cycle defines a methodology for improving the quality of software and the overall development process.
- the following figure is a graphical representation of the various stages of a typical SDLC.
  ![[sdlc.png]]
### 2.A.ii Typical stages
1. **Planning and Requirement Analysis**
	- most important and fundamental stage
	- performed by senior members of the team with input from the customer, the sales department, market surveys and domain experts in the industry.
	- information is then used to plan the basic project approach and to conduct product feasibility study in the economical, operational and technical areas.
	- planning for the quality assurance requirements and identification of the risks associated with the project is also done in the planing stage.
	- The outcome of the technical feasibility study is to define the various technical approach that can be followed to implement the project successfully with minimum risks.
2. **Defining Requirements**
	- once the requirement analysis is done, the next step is to clearly define and document the product requirements and get them approved from the customer or the market analysts.
	- done through Software Requirement Specification (SRS) document which consists of all the product requirements to be designed and developed during project life cycle.
3. **Designing the Product Architecture**
	- SRS is the reference for product architecture to come out with the best architecture for the product to be developed.
	- based on requirement specified in SRS, usually more than one design approach for the product architecture is proposed and document in a Design Document Specification (DDS).
	- Each design approach is outlined with a focus on:
		- System components, and their interactions.
		- Data flow between the modules.
		- User interface design mock-ups.
		- External system integration points.
	- This DDS is reviewed by all the important stakeholders.
	- based on various parameters as risk assessment, product robustness, design modularity, budget and time constraints,
		- the best design approach is selected for the product.
	- DDS typically includes:
		- **Architectural Diagrams** (high level overview of the system structure)
		- **Module Specification** (Detailed descriptions of each component)
		- **Data Model** (ER diagrams, database schemas and entity relationships)
		- **Technology Stack** (Suggested technologies for implementation)
4. **Building or Developing the Product**
	- actual development starts and the product is built
	- programming code is generated as per DDS during this stage.
	- design is performed in detailed and organized manner.
	- coding guidelines defined by organization are followed
	- programming tools like compilers, interpreters, debuggers, etc. are used.
	- high level languages such as C, C++, Pascal, Java, PHP are used.
	- language is chosen with respect to the type of software being developed.
5. **Testing the Product**
	- usually a subset of all stages in modern SDLC models,
	- testing activities are involved in all stages
	- this stage refers to testing only phase of product where product defects are reported, tracked, fixed and retested,
		- until the product reaches quality standards as defined in SRS.
6. **Deployment in the Market and Maintenance**
	- once the product is tested and ready to be deployed it is released formally in the apt market.
	- sometimes product deployment happens in stages as per the business strategy of that organization.
	- the product may first be released in a limited segment and tested in the real business environment (UAT: User Acceptance Testing).
	- The based on the feedback, the product may be released as it is 
		- or with suggested enhancements in the targeting market segment.
	- After the product is released to the market, its maintenance is done for the existing customer base.
---
## 1.2.B Software Process Model
- mechanism of dividing software development work into distinct phases to improve designs, product management, and project management.
- is a specific methodology or approach used to organize and execute the stages of SDLC.
- provides guidelines for how the phases in the SDLC are carried out.
### 2.B.i Factors in choosing software model
1. **Project Requirement**
	- take some time to go through the project requirements and clarify them alongside our organizations or team's expectation.
	- will the user need to specify requirements in detail after each iterative session?
	- will the requirements change during the development process?
2. **Project Size**
	- consider the size of the project
	- larger project -> bigger teams -> need more extensive and elaborative project plans
3. **Project Complexity**
	- Complex projects may not have clear requirements
	- requirements may change often and the cost of delay is high
	- ask yourself if the project requires constant monitoring or feedback from the client
4. **Cost of Delay**
	- is the project highly time bound with a huge cost of delay
	- or timelines are flexible?
5. **Customer Involvement**
	- customers should consult during the process?
	- do users need to participate in all phases?
6. **Familiarity with Technology**
	- involves the developer's knowledge and experience with the project domain, software tools, language and methods needed for development
7. **Project Resource**
	- involves the amount and availability of fund, staff and other resources.
## 1.2.C Types of SPM
### 2.C.i Waterfall Model
#### C.i.a Concept
- first SPM
- aka linear-sequential SPM
  simple to understand and use
- each phase must be completed before the next phase can begin
	- no overlapping in phases
- outcome of one phase acts as input for the next phase sequentially.
#### C.i.b Figure
![[Pasted image 20260207101311.png]]
#### C.i.c Phases
1. **Requirement Analysis**
	- All possible requirements of the system to be developed are captured in this phase
	- documented in Requirement Specification Document.
	- Output: 
		- Understanding of what the system should do
2. **System Design**:
	- The requirement specification from 1st phase are studied and system design is prepared
	- system design helps in specifying hardware and system requirements
	- help in defining the overall system architecture
	- Output:
		- System Design Documents (including UML diagrams, database schema, and interface designs).
3. **Implementation**
	- With inputs from system design, the system is developed in small programs called units, which are integrated in the next phase.
	- Each unit is developed and tested for its functionality,
		- referred to as Unit Testing
	- Output:
		- Executable program modules
4. **(Integration &) Testing**
	- units are integrated into a system after testing of each unit.
	- post integrated, the system is tested for any faults and failures
	- Output:
		- a fully functional, tested system.
5. **Deployment**
	- Once the functional and non-functional testing is done:
		- the product is deployed in the customer environment or released into the market.
	- Output:
		- Operational software in the production environment
6. **Maintenance**
	- to fix potential issues, patches are released.
	- also to enhance the product, some better versions are released.
	- Maintenance is done to deliver these changes in the customer environment.
	- Output:
		- Updated and stable system.
#### C.i.d Application
- requirements are very well documented, clear and fixed
- product definition is table
- technology is understood and is not dynamic
- ample resources with required expertise are available to support the product.
- the project is short.
#### C.i.e Adv/Disadv
| S.N. | Adv                                                                 | Disadv                                                                                       |
| ---- | ------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| 1    | Simple and easy to understand & use                                 | doesn't allow much reflection/revision                                                       |
| 2    | Easy to manage due to rigidity of model                             | no working software is produced until late during life cycle                                 |
| 3    | Phases are processed and completed one at a time                    | high amounts of risk and uncertainty                                                         |
| 4    | works well for smaller projects where requirements are well defined | not suitable for the projects where requirements are at a moderate to high risk of changing. |
| 5    | Clearly defined stages                                              | Poor model for long and ongoing projects                                                     |
| 6    | well understood milestones                                          | not a good model for complex and object-oriented projects                                    |
| 7    | Easy to arrange tasks                                               | Difficult to measure progress within stages.                                                 |
| 8    | process and results are well documented                             |                                                                                              |
### 2.C.ii. V model
#### C.ii.a Concept
- extension of waterfall model
- emphasizing the relationship between development phases and their corresponding testing phases.
- the next phase starts only after completion of the previous phase.
	- there is a testing activity for each development activity.
- sequential development model with focus on quality and testing.
- Verification:
	- involves static analysis technique (review), without executing code
	- evaluates the product development phase to find whether specified requirements meet
	- are we building the product right?
- Validation:
	- involves dynamic analysis technique (functional, non-functional), testing done by executing code.
	- process to evaluate the software after the completion of the development phase
	- to determine whether software meets the customer expectations and requirements.
	- to see if right product is built.
- contains verification phases on one side, validation phase on other side
- joined by coding phase in V shape, thus called V model
- corresponding testing phase of development phase is planned in parallel.
#### C.ii.b Figure
![[Pasted image 20260207103157.png]]
#### C.ii.c Phases
1. **Requirement Analysis**
	- This phase contains detailed communication with the customer to understand their requirements and expectations,
	- aka Requirement gathering
2. **System Design**:
	- contains the system design and the complete hardware and communication setup for developing the product
	- system test plan is developed based on the system design.
3. **Architectural Design**
	- system design is broken down further into modules taking up different functionalities.
	- data transfer and communication between the modules and with the outside world (other systems) is clearly understood.
	- it typically consists of the list of modules, brief functionality of each module, their interface relationships, dependencies, database tables, architecture diagrams, technology detail, etc.
	- the integration testing model is carried out in a particular phase.
4. **Module Design**
	- system breaks down into small modules
	- the detailed design of modules is specified, also known as Low-Level Design (LLD).
5. **Testing Phases**
	1. Unit Testing:
		- unit test plans are developed during module design phase.
		- these unit test plans are executed to eliminate bugs at code or unit level
		- these unit test plans are executed to eliminate bugs at code or unit level.
	2. Integration Testing:
		- the modules are integrated and the system is tested
		- performed on the architecture design phase
		- verifies the communication of modules among themselves
		- done after completion of unit testing.
	3. System Testing:
		- test the complete application with its functionality, inter dependency and communication
		- tests the functional and non-functional requirements of the developed application.
	4. User Acceptance Testing:
		- UAT is performed in a user environment that resembles the production environment.
		- UAT verifies that the delivered system meets user's requirement and system is ready for use in real world.
#### C.ii.d Application
- Why it is preferred:
	- easy to manage due to rigidity of model
	- each phase has specific deliverable and a review process
	- proactive defect tracking, detects defects at early stage
- when to use?
	- where requirements are clearly defined and fixed
	- when ample technical resources are available with technical expertise
#### C.ii.e Adv/Disadv
| S.N. | Adv                                                                | Disadv                                                                                        |
| ---- | ------------------------------------------------------------------ | --------------------------------------------------------------------------------------------- |
| 1    | highly disciplined model and phases are completed one at a time    | high risk and uncertainty                                                                     |
| 2    | model used for small projects where project requirements are clear | not good for complex and object oriented projects                                             |
| 3    | simple and easy to understand and use                              | not suitable for projects where requirements are not clear and contains high risk of changing |
| 4    | model focuses on verification and validation early in life cycle   | does not support iteration of phases                                                          |
| 5    | enhances error-free and good quality product                       | does not handle concurrent events                                                             |
| 6    | enables project management to track progress accurately            |                                                                                               |
### 2.C.iii Incremental Model
#### C.ii.a Concept
- process of software development where requirements are divided into multiple standalone modules of the software development cycle
- the whole requirement is divided into various builds so multiple development cycles take place here, making the life cycle a multi waterfall cycle
- cycles are divided up into smaller, more easily managed modules and each module passes through the requirements, design, implementation and testing phases.
- working version of software is produced during the first module, so we have working software early on during the software life cycle
- each subsequent release of the module adds function to the previous release and the process continues till the system is completed.
#### C.ii.b Figure
![[Pasted image 20260207110456.png]]
#### C.ii.c Phases
#### C.ii.d Application
- when to use the model?
	- a project has lengthy development schedule
	- when software team are not very well skilled or tained
	- when the customer demands a quick release of the product
#### C.ii.e Adv/Disadv
| SN  | Adv                                                     | Disadv                                    |
| --- | ------------------------------------------------------- | ----------------------------------------- |
| 1   | Errors are easy to be recognized                        | need for good planning                    |
| 2   | easier to test and debug                                | total cost is high                        |
| 3   | more flexible                                           | well defined module interfaces are needed |
| 4   | simple to manage risk as it is handles during iteration |                                           |
| 5   | client gets important functionality early               |                                           |
### 2.D.iv RAD Model
#### C.ii.a Concept
- Rapid Application Model
- high speed version of linear sequential model
- software project can be implemented if:
	- project can be broken down into small modules wherein each module can be assigned independently to separate teams
	- these modules can finally be combined to form the final product.
- development of each module involves various basic steps as in the waterfall model, i.e. analyzing, designing, coding and then testing, etc.
- short time span i.e.e time frame for delivery (time box) is generally 60-90 days.
#### C.ii.b Figure
![[Pasted image 20260207111321.png]]
#### C.ii.c Phases
1. **Business Modelling**
	- define the flow of information within the organization, so that it covers all functions
	- helps in clearly understand teh nature, type, source and process of information.
2. **Data Modelling**
	- convert the component of the information flow into a set of data objects.
	- each object is referred as an entity
3. **Process Modelling**
	- data objects defined in the previous phase are used to depict the flow of information
	- adding, deleting, modifying and retrieving the data objects are included
4. **Application Designing**
	- generation of the application and coding takes place
	- 4the generation programming language is the preferred choice
5. **Testing**
	- test the new program component.
#### C.ii.d Application
- when to use?
	- when customer has well-known requirements
	- when user is involved throughout the life cycle
	- when the project can be time boxed.
	- when the functionality can be delivered in increments
	- when high performance is nont required
	- when low technical risks are involved and the system can be modularized.
- applications:
	- model should be used for a system with known requirements and requiring a short development time
	- suitable for projects where requirement scan eb modularized and reusable components are available for developemnt
	- model can also be used when already existing system components can be used in developing a new system with minimum changes
	- model can only be used if the teams consist of domain experts.
	- mmodel should be chosen when the budget permits the use of automated tools and technqieus required.
#### C.ii.e Adv/Disadv
| S.N. | Adv                                                                                                        | Disadv                                                                                                   |
| ---- | ---------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
|      | use of reusable components help to reduce the cycle                                                        | use of powerful and efficient tools require highly skilled professional                                  |
|      | due to emphasis on rapid development, results in delivery of fully functional project in short time period | absence of reusable components can lead to failure of the project.                                       |
|      | encourages the development of program component reusable.                                                  | team leader must work closely with the developers and customers to close the project in time             |
|      |                                                                                                            | the system which cannot be modularized suitable cannot use this model                                    |
|      |                                                                                                            | not suitabel for applications that have  ahigh degree of technical risk                                  |
|      |                                                                                                            | not suitable for the large projects because they require more man power for creating multiple RAD groups |



### 2.D.v Evolutionary Process Model
#### C.ii.a Concept
- referred to as successive versions model
- evolutionary model is a combination of iterative and incremental model of SDLC
- delivering our system in incremental process over time is the action done in this model
- some initial requirements and architecture invisioning need to be done
- better for software product that have their feature set redefined during development because of user feedback and other factors.
- divides development cycle into smaller, incremental waterfall models in which users are able to get access to the product at the end of each cycle.
- feedback is provided by the users on the product for the planning stage of the next cycle and the development team responds, often by changing the product, plan or process.
- therefore, teh software prduct evolves with time.
- all teh models have the disadv that the duration of time from start of the project to delivery time of a solution is very high
- evolutionalry model solves problem in a different approach
- evolutionary model suggests breaking down of work into smaller chunks, prioritizing them and then deliviering those chunks to the customer one by one.
- the number of chunks is huge and is the number of deliveries made to the customer.
- necessary conditions for implementing this model:
	- customer needs are clear and been explained in deep to the deeloper team
	- there might be small changes required in spearate parts but not  amajor change
	- as it requires time, so there mus tbe some time left for the market constraints
	- risk is high and continuous targets achieve and report to customer repeatedly.
	- use dwhne owkring on a technology is new and requires time to learn.
#### C.ii.b Figure
![[Pasted image 20260207113002.png]]
#### C.ii.c Phases

#### C.ii.d Application
- used in large projects where we can easily find modules for incremental implementation
- when the customer wants to start using the core features instead of waiting for the full software
- used in Object Oriented  software development because the system can be easily portioned into units in terms of objects.
#### C.ii.e Adv/Disadv
| S.N. | Adv                                                              | Diasdv                                                                                                                                         |
| ---- | ---------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| 1    | user gets a chance to experiment partially developed system      | hard to divide the problem into several versions that would be acceptable to the customer which can be incrementally implemented and delivered |
| 2    | reduces the error because the core modules get tested thoroughly |                                                                                                                                                |
### 2.D.vi Iterative Model
#### C.ii.a Concept
- iterative process starts with a simple implementation of a small set of the sofwtare requirements and iteratively enhnaces the volving versions until the complete system is implemented and ready to be deployed.
- process is then repeated, producing a new verison of teh software at the end of each iteration of the model
- at each iteration, design modification
#### C.ii.b Figure
#### C.ii.c Phases
#### C.ii.d Application
#### C.ii.e Adv/Disadv
### 2.D.vii. Spiral Model
#### C.ii.a Concept
#### C.ii.b Figure
#### C.ii.c Phases
#### C.ii.d Application
#### C.ii.e Adv/Disadv
### 2.D.viii. Prototype Model
#### C.ii.a Concept
#### C.ii.b Figure
#### C.ii.c Phases
#### C.ii.d Application
#### C.ii.e Adv/Disadv
---
---
# 1.3 Agile Software Developments
# 1.4 Requirements Engineering processes
# 1.5 System modeling
# 1.6 Software prototyping
# 1.7 Object Oriented Software Development

Need of software engineering?
functional and non-functional requirements with example
requirement gathering