# Iterative Development
## Concept
- Iterative Development = cyclical process where you make and test incremental adjustments.
- Popular in: Agile, Scrum, software development, design, research.
- **Core cycle**: Planning → Analysis → Implementation → Testing → Evaluation.
## Iterative Development Process
| Stage                          | Activities                                                                   |
| ------------------------------ | ---------------------------------------------------------------------------- |
| **1. Planning & Requirements** | Map initial requirements, gather documents, create timeline for first cycle  |
| **2. Analysis & Design**       | Create working architecture, schematic, or algorithm satisfying requirements |
| **3. Implementation**          | Develop functionality and design to meet specifications                      |
| **4. Testing**                 | Identify what's not working; stakeholders, users provide feedback            |
| **5. Evaluation & Review**     | Compare iteration with requirements and expectations                         |
## Benefits of Iterative Development
- **Flexibility**: Adapt to new needs and unexpected issues
- **Continuous improvement**: Each cycle refines the product
- **Early feedback**: Users see working product early
- **Risk reduction**: Problems identified and resolved incrementally
# Unified Process
## Concept
- **Unified Process (UP)** = iterative and incremental software development process for building **object-oriented systems**.
- Also known as **Rational Unified Process (RUP)**.
- Provides disciplined approach to assign tasks and responsibilities in development organization.
## Why Use UP?
| Reason           | Explanation                                                 |
| ---------------- | ----------------------------------------------------------- |
| **Iterative**    | Reduces unexpected costs, prevents resource wastage         |
| **Structured**   | Provides framework for OOA/D                                |
| **Flexible**     | Can be applied in lightweight/agile approach with XP, Scrum |
| **UML-friendly** | Well-suited for UML-based modeling                          |
## Goal
- Ensure production of **high-quality software** meeting end-user needs within **predictable schedule and budget**.
## Phases
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

### Inception
| Activity       | Description                                                  |
| -------------- | ------------------------------------------------------------ |
| Business model | Develop initial business model                               |
| Requirements   | Identify customer requirements                               |
| Communication  | With customers and team members                              |
| Scope          | Identify project scope and size                              |
| Feasibility    | Perform feasibility study (technical, economic, operational) |
| Risk           | Identify initial project risks                               |
| Planning       | Create project plan and goals                                |
- **Purpose**: Develop idea into vision of end product
- **Objectives** at End of Inception:
	- Concurrence on project scope and estimates
	- Understanding of requirements
	- 10-20% of use cases analyzed
### Elaboration
| Activity        | Description                              |
| --------------- | ---------------------------------------- |
| Refine vision   | More detail from inception               |
| Architecture    | Establish baseline architecture          |
| Risk resolution | Identify and address high risks          |
| Requirements    | Identify most requirements, refine scope |
| Estimates       | Create more realistic estimates          |
#### Types of Risks Addressed:
| Risk Type              | Description                                  |
| ---------------------- | -------------------------------------------- |
| **Requirements Risk**  | Unclear or changing requirements             |
| **Technological Risk** | New/unfamiliar technology                    |
| **Skills Risk**        | Team skill gaps                              |
| **Political Risk**     | Stakeholder conflicts, organizational issues |
- **Purpose**: Describe in detail; refine vision; establish baseline architecture
- **Objectives at End of Elaboration**:
	- Use case model complete (80-90%)
	- Non-functional requirements elaborated
	- Software architecture described
	- Revised risk list
	- Preliminary user manual (optional)
### Construction
|Activity|Description|
|---|---|
|Coding|Implementation of all components|
|Testing|Unit, integration, system testing (except beta)|
|Integration|Components integrated|
|Refactoring|Done after each iteration|
|Resource Management|Optimize cost, schedule, quality|
- **Purpose**: Develop and complete project; iterative implementation of remaining elements.
- **Characteristics**:
	- Incremental and iterative
	- Lower risk elements implemented
	- Preparation for deployment
- **Objectives at End of Construction**:
	- Product stable and mature for release
	- Actual vs planned expenditure acceptable
	- All features tested
### Transition
| Activity     | Description                                 |
| ------------ | ------------------------------------------- |
| Beta testing | User acceptance testing in real environment |
| Bug fixing   | Remove defects based on feedback            |
| Deployment   | Release to production                       |
| Optimization | Performance tuning                          |
| Releases     | New releases as needed                      |
- **Purpose**: Transition from development environment to production.
- **Objectives of Transition Phase**:
	- Customer satisfaction
	- Stakeholder concurrence on deployment baselines
	- Final product baseline achieved cost-effectively
## Summary of Phases
| Phase            | Focus                               | Key Outputs                                          | Risk Level  |
| ---------------- | ----------------------------------- | ---------------------------------------------------- | ----------- |
| **Inception**    | Vision, scope, feasibility          | Project plan, initial requirements, risk list        | High        |
| **Elaboration**  | Architecture, detailed requirements | Use case model, architecture baseline, refined risks | Medium-High |
| **Construction** | Coding, testing, integration        | Operational product, test results                    | Medium      |
| **Transition**   | Deployment, user acceptance         | Released product, user feedback                      | Low         |
# UP Disciplines
**Discipline** = set of activities (and related artifacts) in one subject area.
## UP Disciplines Overview
| Discipline                            | Purpose                             | Key Activities                                                                                               |
| ------------------------------------- | ----------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| **Business Modeling**                 | Understand business environment     | Understand surroundings, create system vision, create business models                                        |
| **Requirements**                      | Document business requirements      | Gather detailed info, define functional/non-functional requirements, develop UI dialogs, evaluate with users |
| **Design**                            | Design system based on requirements | Design architecture, use case realization, database, UI, security                                            |
| **Implementation**                    | Build/acquire system components     | Build software components, acquire components, integrate                                                     |
| **Testing**                           | Verify quality                      | Unit testing, integration testing, usability testing, acceptance testing                                     |
| **Deployment**                        | Make system operational             | Acquire hardware, package/install, train users, convert data                                                 |
| **Project Management**                | Manage project                      | Finalize scope, develop schedule, identify risks, monitor plan                                               |
| **Configuration & Change Management** | Control changes                     | Develop change control procedures, manage models and components                                              |
| **Environment**                       | Support development                 | Select tools, tailor UP process, provide technical support                                                   |
## Detailed Discipline Descriptions
### Business Modeling
- **Purpose**: Understand business context
- **Artifacts**: Vision document, business models
- **Activities**:
    1. Understand surroundings (stakeholders, processes)
    2. Create system vision
    3. Create business models (use cases, domain models)
### Requirements
- **Purpose**: Document what system should do
- **Maps to**: Traditional systems analysis
- **Activities**:
    1. Gather detailed information
    2. Define functional and non-functional requirements
    3. Develop user interface dialogs
    4. Evaluate requirements with users
### Design
- **Purpose**: How system will be built
- **Activities**:
    1. Design support services architecture and deployment environment
    2. Design use case realization (interaction diagrams)
    3. Design database
    4. Design system and user interfaces
    5. Design system security and controls
### Implementation
- **Purpose**: Build or acquire components
- **Activities**:
    1. Build software components (coding)
    2. Acquire software components (third-party)
    3. Integrate software components
### Testing
- **Purpose**: Ensure quality
- **Activities**:
    1. Define and conduct unit testing
    2. Define and conduct integration testing
    3. Define and conduct usability testing
    4. Define and conduct user acceptance testing (UAT)
### Deployment
- **Purpose**: Make system operational
- **Activities**:
    1. Acquire hardware and system software
    2. Package and install components
    3. Train users
    4. Convert and initialize data
### Project Management
- **Purpose**: Support all activities (most important support discipline)
- **Activities**:
    1. Finalize system and project scope
    2. Develop project and iteration schedule
    3. Identify project risks and confirm feasibility
    4. Monitor and control project plan
    5. Monitor and control communications
    6. Monitor and control risks and outstanding issues
### Configuration & Change Management
- **Purpose**: Control changes to artifacts
- **Artifacts managed**: Requirements, design, source code, executables
- **Activities**:
    1. Develop change control procedures
    2. Manage models and software components
### Environment
- **Purpose**: Provide development infrastructure
- **Includes**: Facilities, workspace, communication forums
- **Activities**:
    1. Tailor UP development process
    2. Provide technical support services
## UP Phases vs Disciplines
```
┌──────────────────────────────────────────────────────────────────────┐
│                     UNIFIED PROCESS WORKFLOW                         │
├──────────────────────────────────────────────────────────────────────┤
│              Inception │ Elaboration │ Construction │ Transition     │
├──────────────────────────────────────────────────────────────────────┤
│ Business Modeling  ████│█████████████│█████████████│█████████████    │
├──────────────────────────────────────────────────────────────────────┤
│ Requirements       ████│█████████████│█████████████│█████████████    │
├──────────────────────────────────────────────────────────────────────┤
│ Design             ████│█████████████│█████████████│                 │
├──────────────────────────────────────────────────────────────────────┤
│ Implementation     ████│█████████████│█████████████│                 │
├──────────────────────────────────────────────────────────────────────┤
│ Testing            ████│█████████████│█████████████│█████████████    │
├──────────────────────────────────────────────────────────────────────┤
│ Deployment         ████│             │             │█████████████    │
├──────────────────────────────────────────────────────────────────────┤
│ Project Management ██████████████████████████████████████████████    │
├──────────────────────────────────────────────────────────────────────┤
│ Config & Change    ██████████████████████████████████████████████    │
├──────────────────────────────────────────────────────────────────────┤
│ Environment        ██████████████████████████████████████████████    │
└──────────────────────────────────────────────────────────────────────┘
```
## UP Advantages and Challenges
### Advantages
| Advantage           | Description                                       |
| ------------------- | ------------------------------------------------- |
| **Iterative**       | Early risk identification, continuous improvement |
| **Flexible**        | Can be tailored for lightweight/agile projects    |
| **Well-structured** | Clear phases and disciplines                      |
| **UML-integrated**  | Seamless with object-oriented modeling            |
| **Predictable**     | Better schedule and cost estimation               |
| **Quality-focused** | Testing integrated throughout                     |
### Potential Challenges
| Challenge                | Description                             |
| ------------------------ | --------------------------------------- |
| **Complexity**           | Full UP may be heavy for small projects |
| **Overhead**             | Documentation and process overhead      |
| **Learning curve**       | Requires understanding of disciplines   |
| **Customization needed** | Must be tailored for specific projects  |
# Requirement Elicitation in OOA
## 4.8.A Process
| Step                         | Activity                                           |
| ---------------------------- | -------------------------------------------------- |
| **1. Identify Stakeholders** | Users, clients, domain experts, managers           |
| **2. Gather Information**    | Interviews, workshops, questionnaires, observation |
| **3. Analyze Domain**        | Understand terminology, business rules, workflows  |
| **4. Identify Objects**      | Extract nouns from requirements, classify          |
| **5. Define Use Cases**      | Capture interactions from user perspective         |
| **6. Validate**              | Confirm understanding with stakeholders            |
## Types of Requirements in OO Systems
| Requirement Type                | Description              | Example                            |
| ------------------------------- | ------------------------ | ---------------------------------- |
| **Functional Requirements**     | What system must do      | "System shall validate user login" |
| **Non-Functional Requirements** | Quality attributes       | "Response time < 2 seconds"        |
| **Domain Requirements**         | From problem domain      | "Interest rate calculated monthly" |
| **User Requirements**           | End-user needs           | "User-friendly interface"          |
| **System Requirements**         | Technical specifications | "Must run on Windows/Linux"        |
| **Business Requirements**       | Organizational goals     | "Reduce processing time by 30%"    |
# Static vs Dynamic Analysis in OOAD
| Aspect         | Static Analysis                 | Dynamic Analysis                                  |
| -------------- | ------------------------------- | ------------------------------------------------- |
| **Focus**      | Structure, relationships        | Behavior, interactions                            |
| **When**       | During analysis/design          | During testing/execution                          |
| **Diagrams**   | Class diagram, object diagram   | Sequence diagram, activity diagram, state diagram |
| **Questions**  | _What are the parts?_           | _How do they behave?_                             |
| **Outputs**    | Class hierarchies, associations | Message flows, state changes                      |
| **Validation** | Structural consistency          | Behavioral correctness                            |
# Summary

| Topic                     | Key Points                                                                                                                   |
| ------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| **Iterative Development** | Cyclical: Plan → Analyze → Implement → Test → Evaluate; repeats                                                              |
| **Unified Process (UP)**  | Iterative, incremental, OO-focused; 4 phases                                                                                 |
| **Inception**             | Vision, scope, feasibility, risk ID                                                                                          |
| **Elaboration**           | Architecture, detailed requirements, risk resolution                                                                         |
| **Construction**          | Coding, testing, integration                                                                                                 |
| **Transition**            | Deployment, beta testing, user feedback                                                                                      |
| **UP Disciplines**        | Business modeling, requirements, design, implementation, testing, deployment, project management, config/change, environment |
| **Requirement Types**     | Functional, non-functional, domain, user, system, business                                                                   |
| **Static Analysis**       | Structure (class diagrams)                                                                                                   |
| **Dynamic Analysis**      | Behavior (sequence, activity, state diagrams)                                                                                |


[[Chapter 5 Object Oriented Design]]