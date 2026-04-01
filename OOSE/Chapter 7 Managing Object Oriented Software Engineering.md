# Project Selection and Preparation
## Process Maturity Levels (SEI Capability Maturity Model)
| Level | Name       | Description                                                                    |
| ----- | ---------- | ------------------------------------------------------------------------------ |
| **1** | Initial    | No documented method; each developer works independently                       |
| **2** | Repeatable | Informal method exists by consensus; "the way we do things around here"        |
| **3** | Defined    | Formal, documented process; continuously refined by software process group     |
| **4** | Managed    | Formal measurements of process and product (time, cost, productivity, quality) |
| **5** | Optimizing | Measurements systematically used as feedback to optimize process               |
**Key Insight**: Organizations below Level 3 are generally not ready to adopt new methods/tools effectively.
## Introducing New Development Process
**Important Observations**:
- Organization maturity ≠ individual maturity
- Transition period causes temporary productivity drop
- Mature systems with limited maintenance needs may not justify technology change

**Key Success Factors for Transition**:

| Factor                              | Description                                                                 |
| ----------------------------------- | --------------------------------------------------------------------------- |
| **Upper Management Support**        | Strategic decision must be backed by a sponsor in management                |
| **Careful First Project Selection** | First project exposed to scrutiny; must have resources to guarantee success |
| **Positive Team Attitude**          | Staff must feel positive about change; sufficient training and CASE tools   |
| **Method Before Tool**              | Introduce method first; tools support method, not vice versa                |
| **Integration**                     | New working method must integrate with existing routines                    |
| **Reasonable Expectations**         | Quality improves immediately; productivity takes years to show profit       |
| **Realistic Reuse Expectations**    | Reuse benefits appear in 2-3 years, not immediately                         |
## Factors to Consider While Selecting a Project
### When Selecting the First Project for New Method:
| Factor                 | Consideration                                                                   |
| ---------------------- | ------------------------------------------------------------------------------- |
| **Project Importance** | Real project that is important, but not with tight schedule or hard constraints |
| **Problem Domain**     | Well-known and well-defined domain                                              |
| **Team Selection**     | Experienced developers with positive view of change; management confidence      |
| **Project Manager**    | High degree of interest in the task                                             |
| **Staff Commitment**   | Full-time on project, not disturbed by other projects                           |
| **Planning**           | Detailed plan developed in advance with pre-established evaluation criteria     |
| **Sponsor**            | Upper management person with special interest to follow and support project     |
### General Project Selection Factors:
| Factor                    | Questions to Consider                                         |
| ------------------------- | ------------------------------------------------------------- |
| **Strategic Alignment**   | Does project align with business goals?                       |
| **Feasibility**           | Is project technically, economically, operationally feasible? |
| **Risk Level**            | What are the identified risks? Can they be managed?           |
| **Resource Availability** | Are skilled staff, budget, infrastructure available?          |
| **Timeline**              | Is schedule realistic? Any hard constraints?                  |
| **Scope**                 | Is scope well-defined? Manageable?                            |
| **Stakeholder Support**   | Is there commitment from key stakeholders?                    |
| **Reuse Potential**       | Can components be reused in future projects?                  |
## Education and Training
| Role                  | Training Needs                                                    |
| --------------------- | ----------------------------------------------------------------- |
| **All Personnel**     | Basic education on concepts and way of working                    |
| **Specialized Roles** | Additional training based on specific responsibilities            |
| **Formal Method**     | More emphasis on formal education when method is strictly defined |
| **Informal Method**   | Several learning projects needed before high productivity         |
# Project Development Organization

## OOSE Model Development Sequence
```
Requirements Model → Analysis Model → Design Model → Source Code → Tested System
```
**Key Principle**: All models must be maintained throughout product life cycle.
## OOSE Processes
| Process                   | Input               | Output                                         | Sub-Processes                                                                                                     |
| ------------------------- | ------------------- | ---------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| **Requirements Analysis** | User needs          | Requirement model with use case specifications | Coordination (identify actors, use cases, domain objects); Specification (specify use cases, objects, subsystems) |
| **Analysis**              | Requirement model   | Analysis model                                 | Identification of analysis objects; Object specification; Subsystem specification                                 |
| **Construction**          | Analysis model      | Design model + unit-tested code                | Use case design; Block construction; Subsystem construction (optional)                                            |
| **Testing**               | Design model + code | Integration tested system                      | Integration testing; System testing; Use case tests; Subsystem tests                                              |
## Project Organization Roles
| Role                            | Responsibility                                                                                          |
| ------------------------------- | ------------------------------------------------------------------------------------------------------- |
| **System Architecture Group**   | System architecture, coherent vision; includes project manager; consistent across first three processes |
| **Requirements Analysis Group** | Initial requirement analysis with end users                                                             |
| **Development Personnel**       | Detailed work; same person should handle same objects across activities                                 |
| **Testing Group**               | Independent testing of system                                                                           |
| **Methodologist**               | Method, language, OS, product structure, development organization                                       |
| **Quality Assurance**           | Product and process quality                                                                             |
| **Documentation/Training**      | System documentation for maintenance and users                                                          |
| **Reuse Coordinator**           | Encourage reuse; evaluate reuse potential of code and designs                                           |
| **Staff/Planner**               | Track cost and time schedules                                                                           |
| **Prototyper**                  | Investigate solutions early                                                                             |
| **Support Environment**         | System management, infrastructure services                                                              |
## Project Management Phases
| Phase                 | Activities                                                                                     |
| --------------------- | ---------------------------------------------------------------------------------------------- |
| **Pre-study**         | Determine project practicability; evaluate requirements; judge technical/practical feasibility |
| **Feasibility Study** | Study technical alternatives and consequences                                                  |
| **Establishment**     | Develop detailed plans and resource plans                                                      |
| **Execution**         | Develop project according to plans                                                             |
| **Conclusion**        | Complete project; summarize improvement proposals                                              |
# COCOMO Model (Constructive Cost Model)
## Development Modes
| Mode             | Description             | Size Range  | Characteristics                                                          |
| ---------------- | ----------------------- | ----------- | ------------------------------------------------------------------------ |
| **Organic**      | Small, simple projects  | 2-50 KLOC   | Small teams, good experience, familiar environment, flexible deadlines   |
| **Semidetached** | Medium complexity       | 50-300 KLOC | Mixed experience levels, mix of rigid/flexible requirements              |
| **Embedded**     | Large, complex projects | >300 KLOC   | Tight hardware/software constraints, high innovation, complex interfaces |
## Basic COCOMO Formulas
```

Effort (E) = a × (KLOC)^b  Person-Months
Time (D) = c × (E)^d  Months
Staff Size = E / D  Persons
Productivity = KLOC / E  KLOC/Person-Month
```
## Basic COCOMO Coefficients
| Mode             | a   | b    | c   | d    |
| ---------------- | --- | ---- | --- | ---- |
| **Organic**      | 2.4 | 1.05 | 2.5 | 0.38 |
| **Semidetached** | 3.0 | 1.12 | 2.5 | 0.35 |
| *Embedded**      | 3.6 | 1.20 | 2.5 | 0.32 |
## Example Calculation
**Given**: Project size = 400 KLOC

|Mode|Effort (PM)|Development Time (Months)|
|---|---|---|
|Organic|2.4 × 400^1.05 = 1295|2.5 × 1295^0.38 = 38|
|Semidetached|3.0 × 400^1.12 = 2462|2.5 × 2462^0.35 = 39|
|Embedded|3.6 × 400^1.20 = 4772|2.5 × 4772^0.32 = 38|
## Advantages & Disadvantages
| Advantages                             | Disadvantages                                          |
| -------------------------------------- | ------------------------------------------------------ |
| Easy to estimate total cost            | Ignores requirements, customer skills, hardware issues |
| Easy to implement with various factors | Limits accuracy of cost estimates                      |
| Provides historical project reference  | Depends heavily on time factors                        |
# Risk Management Process

## Risk Management Activities
```
Risk Identification → Risk Assessment (Analysis + Prioritization) → Risk Control (Planning + Resolution + Monitoring)
```
## Risk Management Process Flow
```

┌─────────────────────┐
│ Risk Identification │───→ List of potential risks
└────────┬────────────┘
         ▼
┌─────────────────────┐
│ Risk Analysis       │───→ Prioritized Risk List
└────────┬────────────┘
         ▼
┌─────────────────────┐
│ Risk Planning       │───→ Avoidance & Contingency Plans
└────────┬────────────┘
         ▼
┌─────────────────────┐
│ Risk Monitoring     │───→ Risk Assessment
└────────┬────────────┘
         │
         └──────→ (loops back to analysis)
```
## Types of Risks
| Risk Type             | Causes                                                                                                          |
| --------------------- | --------------------------------------------------------------------------------------------------------------- |
| **Schedule Risk**     | Wrong time estimation, improper resource tracking, failure to identify complex functionalities, scope expansion |
| **Budget Risk**       | Wrong budget estimation, cost overruns, scope expansion                                                         |
| **Operational Risk**  | Priority conflicts, unclear responsibilities, insufficient resources, no training, poor communication           |
| **Technical Risk**    | Changing requirements, immature technology, complex product, difficult integration                              |
| **Programmatic Risk** | Running out of funds, market changes, changing customer priorities, government regulation changes               |
## Risk Management Principles
| Principle                 | Description                                                   |
| ------------------------- | ------------------------------------------------------------- |
| **Global Perspective**    | Review system design and implementation; consider risk impact |
| **Forward Looking View**  | Consider future threats; create future plans                  |
| **Open Communication**    | Free flow of communication between client and team            |
| **Integrated Management** | Make risk management integral to project management           |
| **Continuous Process**    | Track risks continuously throughout project                   |
## Risk Management Paradigm (6 Phases)
1. **Identify** – Identify risks to avoid future problems
2. **Analyze** – Extract information on nature, behavior, type of risk
3. **Plan** – Take actions; implement plans
4. **Track** – Track actions for risk removal/minimization
5. **Control** – Check techniques; make improvements
6. **Communicate** – Discuss processes with development and testing team
# Software Quality Assurance (SQA)
## Definition
- Planned and systematic actions to provide confidence that product conforms to technical requirements
- Management activity to identify quality problems early
## SQA Components
| Component                        | Focus   | Activities                                                         |
| -------------------------------- | ------- | ------------------------------------------------------------------ |
| **Software Quality Control**     | Product | Ensure delivered software has minimum faults; satisfies user needs |
| **Software Quality Engineering** | Process | Institute procedures, techniques, tools for fault-free development |
## Main SQA Tools
| Tool                    | Purpose                     |
| ----------------------- | --------------------------- |
| **Development Process** | Structured approach         |
| **Reviews & Audits**    | Early fault detection       |
| **Testing**             | Validation and verification |
| **Metrics**             | Measurement and improvement |
## Quality Advice
| Advice                       | Description                                  |
| ---------------------------- | -------------------------------------------- |
| **Follow Process**           | Note what goes wrong                         |
| **Eliminate Faults Early**   | Review all specifications thoroughly         |
| **Right Review Composition** | Ensure appropriate people in review groups   |
| **Track Reviews**            | Note pages reviewed, faults found by type    |
| **Follow Up**                | Identify error-prone objects and individuals |
| **Independent Testing**      | Separate testing group writes test reports   |
| **Do It Right First Time**   | Cheapest approach in long run                |
## Software Product Quality Characteristics
| Category            | Characteristics                                                                       |
| ------------------- | ------------------------------------------------------------------------------------- |
| **Suitability**     | Reliability, Correctness, Accuracy, Efficiency, Usability                             |
| **Maintainability** | Understandability, Modifiability, Traceability, Testability, Portability, Reusability |
# Software Metrics

## Definition
- Standard of measure for estimating quality, progress, and health of software testing effort
## Types of Metrics
| Metric Type         | Description                  | Examples                                                            |
| ------------------- | ---------------------------- | ------------------------------------------------------------------- |
| **Product Metrics** | Product characteristics      | Size, design complexity, performance, quality level                 |
| **Process Metrics** | Development process measures | Total development time, time per process, QA cost, number of faults |
| **Project Metrics** | Project characteristics      | Number of developers, cost, schedule                                |
### 7.6.C OO-Specific Metrics
| Metric                                          | Purpose               |
| ----------------------------------------------- | --------------------- |
| Total number of classes                         | Measure system size   |
| Number of classes reused vs. newly developed    | Measure reuse         |
| Total number of operations                      | Measure functionality |
| Number of operations reused vs. newly developed | Measure reuse         |
| Average operations per class                    | Class complexity      |
| Length of operation                             | Complexity            |
| Stimuli sent per operation                      | Coupling              |
| Average number of inherited operations          | Inheritance depth     |
## McCabe Cyclomatic Complexity
**Formula**: `M = E - N + 2`
- E = number of edges in control flow graph
- N = number of nodes
**Guideline**: No module should have McCabe number > 10 (excessive complexity increases error probability)
# Key Points for Exam
| Topic                         | Key Points                                                               |
| ----------------------------- | ------------------------------------------------------------------------ |
| **Process Maturity**          | Levels 1-5 (Initial → Repeatable → Defined → Managed → Optimizing)       |
| **Project Selection Factors** | Importance, domain, team, manager, commitment, planning, sponsor         |
| **OOSE Processes**            | Requirements → Analysis → Construction → Testing                         |
| **COCOMO**                    | Effort = a×(KLOC)^b; Time = c×(E)^d; Organic/Semidetached/Embedded modes |
| **Risk Types**                | Schedule, Budget, Operational, Technical, Programmatic                   |
| **SQA**                       | Quality Control (product) + Quality Engineering (process)                |
| **Metrics**                   | Product, Process, Project; OO-specific: classes, operations, reuse       |
