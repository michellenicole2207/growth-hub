# ISTQB CTFL — Glossary

All key terms from Chapters 1–6, sorted alphabetically.
Each entry shows the chapter(s) where it is tested and the cognitive level.

> **How to use:** Read the term, try to recall the definition, then check it.
> Focus extra time on K2 terms (you need to *explain* them, not just recall) and K3 terms (you need to *apply* them).

---

## A

**Acceptance criteria** `Ch4` `💡 K2`
The conditions a user story must meet to be accepted by stakeholders. They define the scope of the story, guide acceptance testing, and are typically written in scenario-oriented (Given/When/Then) or rule-oriented format.

**Acceptance testing** `Ch2` `💡 K2`
The test level focused on validation — confirming the system is ready for deployment. Performed by business representatives or end users. Includes UAT, OAT, contractual/regulatory testing, alpha, and beta testing.

**Alpha testing** `Ch2` `💡 K2`
A type of acceptance testing performed by internal users at the developer's site, before release.

**Anomaly** `Ch3` `🧠 K1`
Any result or condition that deviates from expectations, discovered during a review. May or may not be a defect — needs to be investigated.

**ATDD — Acceptance Test-Driven Development** `Ch2` `Ch4` `💡 K2`
An approach where test cases are written before the user story is implemented, based on acceptance criteria. Steps: specification workshop → test case creation → implementation. Closely related to BDD.

---

## B

**BDD — Behavior-Driven Development** `Ch2` `🧠 K1`
A test-first approach where tests are written in natural language using the Given/When/Then format, making them understandable to the whole team including non-technical stakeholders.

**Beta testing** `Ch2` `💡 K2`
A type of acceptance testing performed by external users in their own environment, after release.

**Black-box technique** `Ch4` `💡 K2`
A test technique that derives test cases from the specified behavior of the software — without knowledge of its internal structure. Tests survive code changes because they are specification-based. See also: *Equivalence Partitioning*, *Boundary Value Analysis*, *Decision Table Testing*, *State Transition Testing*.

**Black-box testing** `Ch2` `💡 K2`
A test type where tests are based on the specification or specified behavior of the system, without knowledge of internal structure. Can be applied at any test level.

**Boundary Value Analysis (BVA)** `Ch4` `⚙️ K3`
A black-box technique that extends equivalence partitioning by specifically targeting the boundaries of ordered partitions. Two versions: 2-value BVA (boundary + nearest neighbor) and 3-value BVA (boundary + value immediately below + value immediately above). Exploits the fact that developers make the most mistakes at the edges of ranges.

**Branch** `Ch4` `💡 K2`
A transfer of control between nodes in a control flow graph. Branches can be unconditional or conditional (e.g., from an if/else or switch statement).

**Branch coverage** `Ch4` `💡 K2`
The percentage of branches exercised by a test suite. 100% branch coverage guarantees 100% statement coverage (subsumption), but not vice versa. Stronger than statement coverage.

**Branch testing** `Ch4` `💡 K2`
A white-box technique that designs test cases to exercise all branches in the code. Corresponds to branch coverage.

---

## C

**Checklist-based testing** `Ch4` `💡 K2`
An experience-based technique where tests are guided by a prepared list of conditions, often phrased as questions. Checklists should be regularly updated based on defect analysis to prevent them from wearing out.

**Component integration testing** `Ch2` `💡 K2`
A test level focused on testing the interfaces and interactions between integrated components. Usually performed by developers or testers after component testing.

**Component testing** `Ch2` `💡 K2`
The test level focused on individual components tested in isolation. Also called unit testing. Typically performed by developers.

**Confirmation testing** `Ch2` `💡 K2`
Testing performed after a defect has been fixed, to verify that the specific defect no longer causes a failure. Also called re-testing.

**Configuration management (CM)** `Ch5` `💡 K2`
The discipline of identifying, tracking, and controlling versions of testware and test objects. Ensures test cases can be linked to the correct software version and that testing is reproducible. Supporting context for FL-5.1.1 — not a standalone LO.

**CI/CD — Continuous Integration / Continuous Delivery** `Ch6` `🧠 K1`
A DevOps practice where every code change automatically triggers a build and a test run. Integrates testing directly into the development pipeline, enabling fast feedback and supporting shift left. CI/CD tools connect developer commits to test results without manual intervention.

**Coverage measurement tool** `Ch6` `🧠 K1`
A tool that measures how much of the code or requirements has been exercised by a test suite. Produces objective metrics such as statement coverage or branch coverage percentages.

**Coverage criterion** `Ch4` `💡 K2`
A rule or target used to determine whether a test suite is sufficient. Examples: all partitions exercised (EP), all branches exercised (branch coverage), all valid transitions exercised (state transition).

---

## D

**Data-driven testing** `Ch6` `🧠 K1`
A test automation approach where the test script is separated from the test data. Data is stored externally (e.g., a spreadsheet or database) and fed into the script at runtime, allowing the same script to run with many different data sets.

**Decision table testing** `Ch4` `⚙️ K3`
A black-box technique used to test combinations of conditions and their resulting actions. Each column in the table represents one rule (unique combination of conditions). Best suited for testing business logic with complex conditional behavior.

**Defect** `Ch1` `🧠 K1`
A flaw or imperfection in a work product (code, document, design) introduced by a human error. When executed, a defect may cause a failure — or may not, depending on the conditions.

**Defect management** `Ch5` `⚙️ K3`
The process of tracking defects from discovery to closure. Involves logging, classifying, prioritizing, fixing, retesting, and closing defects. The exam tests the content of a defect report (FL-5.4.1/5.4.2).

**Defect report** `Ch5` `⚙️ K3`
A document that records a defect, containing all information needed to reproduce, track, and resolve it. Key fields: unique ID, summary, date/author, environment, steps to reproduce, expected result, actual result, severity, priority, status, attachments.

**Definition of Done (DoD)** `Ch5` `💡 K2`
Agile equivalent of exit criteria — the conditions that must be met for a user story or iteration to be considered complete.

**Definition of Ready (DoR)** `Ch5` `💡 K2`
Agile equivalent of entry criteria — the conditions that must be met before work on a user story or iteration can begin.

**Dynamic testing** `Ch1` `Ch3` `💡 K2`
Testing performed by executing the software. Defects are revealed through failures — the system must run. Contrast with static testing.

---

## E

**Entry criteria** `Ch5` `💡 K2`
Conditions that must be satisfied before a test activity begins. Prevents wasted effort on testing when the system is not ready. In Agile: Definition of Ready (DoR).

**Equivalence partitioning (EP)** `Ch4` `⚙️ K3`
A black-box technique that divides input (or output) data into partitions where all values are expected to be treated identically by the system. One test case per partition is sufficient. Coverage = partitions exercised ÷ total partitions.

**Error** `Ch1` `🧠 K1`
A human mistake — for example, a developer misunderstanding a requirement. An error introduces a defect into a work product.

**Error guessing** `Ch4` `💡 K2`
An experience-based technique that uses the tester's knowledge of how software typically fails to anticipate and target likely defects. Can be structured as a *fault attack* using a list of likely errors.

**Exit criteria** `Ch5` `💡 K2`
Conditions that determine when a test activity is sufficiently complete. May include coverage targets, defect density thresholds, or time/budget exhaustion. In Agile: Definition of Done (DoD).

**Experience-based technique** `Ch4` `💡 K2`
A category of test techniques based on the tester's knowledge, intuition, and experience. Complements black-box and white-box techniques. Includes error guessing, exploratory testing, and checklist-based testing.

**Exploratory testing** `Ch4` `💡 K2`
An experience-based technique where the tester simultaneously designs, executes, and evaluates tests while learning about the system. Uses a *test charter* to guide each time-boxed session. Most effective when specs are incomplete or time is limited.

---

## F

**Failure** `Ch1` `🧠 K1`
The visible, observable incorrect behavior of a system caused by the execution of a defect. Not all defects cause failures — some require specific conditions to trigger.

**Fault attack** `Ch4` `💡 K2`

A structured form of error guessing: the tester creates a list of likely errors and defects, then designs tests specifically to expose them.

**Functional testing** `Ch2` `💡 K2`
A test type that evaluates *what* the system does — its functional completeness, correctness, and appropriateness. Can be applied at any test level.

---

## I

**Impact analysis** `Ch2` `💡 K2`

The process of evaluating which parts of a system are affected by a proposed change. Used before maintenance testing to define the scope of regression testing. Relies on good traceability.

**Informal review** `Ch3` `🧠 K1`
The least formal review type. No defined process, no required output. Goal is simply to find anomalies through a casual inspection.

**Inspection** `Ch3` `🧠 K1`
The most formal review type. Follows a complete defined process based on ISO/IEC 20246. Maximum anomaly detection is the primary goal; metrics are collected. The author **cannot** act as review leader or scribe — unique to this review type.

**INVEST** `Ch4` `💡 K2`
An acronym defining the characteristics of a good user story: **I**ndependent, **N**egotiable, **V**aluable, **E**stimable, **S**mall, **T**estable.

---

## K

**Keyword-driven testing** `Ch6` `🧠 K1`
A test automation approach where test actions are expressed as readable keywords (e.g., `Login`, `ClickButton`, `VerifyText`). The keywords are implemented separately, allowing non-programmers to write and maintain tests without scripting knowledge.

---

## M

**Maintenance testing** `Ch2` `💡 K2`
Testing performed on a system already in production when it needs to change. Triggered by modifications (enhancements, bug fixes, hot fixes), upgrades/migrations (new platform, OS, environment), or retirement (end-of-life data archiving).

**Model-based testing** `Ch6` `🧠 K1`
A test approach where test cases are automatically derived from a behavioral model of the system. The model (e.g., a state machine or decision table) serves as the test basis; a tool generates test cases from it. Reduces manual test design effort for complex systems.

**Moderator** `Ch3` `🧠 K1`
The role responsible for running a review meeting effectively. Handles facilitation, mediation, and time management, and ensures a safe environment for feedback. Required in technical reviews and inspections; optional in walkthroughs.

---

## N

**Non-functional testing** `Ch2` `💡 K2`
A test type that evaluates *how well* the system performs — covering performance, security, usability, reliability, maintainability, portability, and safety. Can be applied at any test level.

---

## O

**OAT — Operational Acceptance Testing** `Ch2` `💡 K2`
A type of acceptance testing focused on operational readiness: backup and recovery, security, performance under load, and other operational characteristics.

---

## P

**Priority** `Ch5` `💡 K2`
How urgently a defect needs to be fixed, from a business perspective. High priority means it must be fixed soon — regardless of severity. A cosmetic bug on the login screen may be low severity but high priority.

**Product risk** `Ch5` `💡 K2`
The risk that a system component or feature will fail to meet expected behavior or quality. Product risks drive the scope and depth of testing.

**Performance testing tool** `Ch6` `🧠 K1`
A tool that simulates concurrent user load on a system and measures response times, throughput, and resource consumption under stress. Used for load testing, stress testing, and endurance testing.

**Project risk** `Ch5` `💡 K2`
The risk to the project itself — schedule, budget, resources, or team. Managed through project management, not testing.

---

## Q

**Quality assurance (QA)** `Ch1` `🧠 K1`
A process-oriented, preventive activity that improves the development process to prevent defects from occurring. Distinct from testing, which is product-oriented and corrective. QA sets up the good process; testing checks the result.

---

## R

**Regression testing** `Ch2` `💡 K2`
Re-running tests after a change to detect unintended side effects — ensuring that existing functionality has not been broken. Grows with every release and is a strong candidate for automation.

**Review** `Ch3` `🧠 K1`
A form of static testing where one or more people manually evaluate a work product. Types range from informal to formal (inspection). Goal: find anomalies, improve quality, build shared understanding.

**Review leader** `Ch3` `🧠 K1`
The role responsible for organizing the overall review: deciding who participates, when, and where. Cannot be the same person as the scribe or author in an inspection.

**Risk** `Ch5` `🧠 K1`
The possibility of an event occurring that causes an adverse consequence. Characterized by its likelihood and impact. The combination of both determines the risk level.

**Risk assessment** `Ch5` `🧠 K1`
The second stage of risk-based testing: evaluating identified risks by their likelihood and impact to determine which areas need the most testing attention.

**Risk identification** `Ch5` `🧠 K1`
The first stage of risk-based testing: brainstorming with stakeholders to identify what could go wrong in the system.

**Risk-based testing** `Ch5` `💡 K2`
A testing approach that uses risk as the primary guide for deciding what to test, how much to test, and when to test. Ensures the highest-risk areas receive the most testing attention — especially important when time is limited.

**Root cause** `Ch1` `🧠 K1`
The fundamental underlying reason why an error was made — e.g., a misunderstood requirement, lack of training, or unclear documentation. Fixing root causes prevents future defects.

---

## S

**Scribe** `Ch3` `🧠 K1`
The role responsible for recording anomalies, decisions, and new findings during a review meeting. Mandatory in walkthroughs and inspections.

**Severity** `Ch5` `💡 K2`
The impact of a defect on the system — how badly it affects functionality, data, or operations. Classified as Critical, Major, Minor, or Trivial. Not the same as priority.

**Shift left** `Ch2` `💡 K2`
The practice of moving testing activities earlier in the SDLC — performing test analysis, design, and even execution as early as possible to find defects when they are cheapest to fix.

**SDLC — Software Development Lifecycle** `Ch2` `🧠 K1`
The process used to plan, create, test, and deliver software. The choice of SDLC model (sequential, iterative, incremental) directly impacts how testing is structured and when it occurs.

**State transition testing** `Ch4` `⚙️ K3`
A black-box technique that tests a system's behavior based on its states and the transitions between them. Coverage criteria: all states (weakest), all valid transitions / 0-switch (most common), all transitions including invalid (strongest).

**Statement coverage** `Ch4` `💡 K2`
The percentage of executable statements exercised by a test suite. 100% statement coverage does not guarantee all branches are tested. Weaker than branch coverage.

**Statement testing** `Ch4` `💡 K2`
A white-box technique that designs test cases to exercise executable statements. Corresponds to statement coverage.

**Static analysis** `Ch3` `Ch6` `💡 K2`
Tool-assisted evaluation of a work product against a formal syntax — without executing it. Examples: linters, code analyzers. Finds issues like undefined variables, unreachable code, and coding standard violations. In Ch6, static analysis tools are a named tool category that supports static testing activities.

**Static testing** `Ch1` `Ch3` `💡 K2`
Testing performed without executing the software. Includes both manual reviews and automated static analysis. Can find defects in non-executable work products (requirements, designs, test plans) that dynamic testing cannot reach.

**System integration testing** `Ch2` `💡 K2`
A test level focused on the interfaces between the system under test and external systems or services. Tests interactions at the system boundary.

**System testing** `Ch2` `💡 K2`
A test level that tests the end-to-end behavior of the entire system against its specified requirements. Typically performed by independent testers.

---

## T

**Test automation** `Ch6` `🧠 K1`
The use of tools to execute tests and compare actual results to expected results automatically, without manual intervention. Most effective for repetitive, stable, high-volume testing. Not a replacement for human judgment and exploratory testing.

**Test automation framework** `Ch6` `🧠 K1`
A set of rules, libraries, and tools that provide the structure and conventions for writing, organizing, and running automated test scripts. Examples include data-driven and keyword-driven frameworks.

**Test management tool** `Ch6` `🧠 K1`
A tool that supports the planning, monitoring, controlling, and reporting of test activities. Typically manages test cases, test suites, test execution schedules, and defect tracking in one place.

**TDD — Test-Driven Development** `Ch2` `🧠 K1`
A development practice where developers write a failing unit test first, then write code to make it pass, then refactor. Implements the early testing principle.

**Technical review** `Ch3` `💡 K2`
A semi-formal review type led by a trained moderator or peer leader with technically qualified reviewers. Focus is on achieving consensus on technical issues and detecting anomalies.

**Test basis** `Ch1` `🧠 K1`
All the information used to derive test cases — requirements, user stories, designs, code, risk assessments, etc. Good traceability links test cases back to the test basis.

**Test charter** `Ch4` `💡 K2`
A document used in exploratory testing to define the objectives of a time-boxed test session. Guides exploration without over-constraining it.

**Test completion report** `Ch5` `💡 K2`
A report produced at the end of a test phase or project. Summarizes what was tested, results, deviations from the plan, defect status, testware to archive, and lessons learned.

**Test control** `Ch5` `💡 K2`
The activity of taking corrective actions when test monitoring reveals deviations from the test plan — such as reprioritizing tests, adjusting scope, or adding resources.

**Test level** `Ch2` `💡 K2`
A group of test activities organized and managed together, with a specific focus and test basis. The five levels: component, component integration, system, system integration, and acceptance testing.

**Test monitoring** `Ch5` `💡 K2`
The ongoing activity of checking actual test progress against the plan, using metrics. Enables test control when deviations are found.

**Test object** `Ch1` `🧠 K1`
The specific work product being tested — e.g., a component, a system, a document, or a configuration.

**Test plan** `Ch5` `💡 K2`
A document that describes the objectives, scope, approach, schedule, and resources for a test effort. A living document updated as the project evolves.

**Test progress report** `Ch5` `💡 K2`
A report that communicates the current testing status to stakeholders. Covers the period, progress vs. plan, impediments, and planned next steps.

**Test pyramid** `Ch5` `💡 K2`
A model recommending a distribution of tests across levels: many unit tests (fast, cheap), fewer integration tests, and very few UI/end-to-end tests (slow, brittle). Encourages automating at the lowest effective level.

**Test type** `Ch2` `💡 K2`
A classification of testing by what aspect of the system is being tested: functional, non-functional, black-box, or white-box. All four types can be applied at any test level.

**Testware** `Ch1` `💡 K2`
All artifacts produced by test activities — including test plans, test cases, test scripts, test data, test logs, defect reports, and completion reports.

**Testing quadrants** `Ch5` `💡 K2`
A framework (Brian Marick) for categorizing test types by two axes: technology-facing vs. business-facing, and supporting the team vs. critiquing the product. Q1 (tech, support): unit/integration tests. Q2 (business, support): functional/story tests. Q3 (business, critique): exploratory/UAT. Q4 (tech, critique): performance/security.

---

## U

**UAT — User Acceptance Testing** `Ch2` `💡 K2`
A type of acceptance testing where real users validate that the system meets their needs and is ready for use in production.

**User story** `Ch4` `💡 K2`
A description of a feature that delivers value to a user or purchaser. Written as: *"As a [role], I want [goal], so that [business value]."* Has three components: Card, Conversation, Confirmation (the 3 Cs). Should follow the INVEST criteria.

---

## V

**Validation** `Ch1` `🧠 K1`
Confirming that a product meets the needs of the user and other stakeholders. Asking: *"Are we building the right product?"* Focuses on fitness for purpose.

**Verification** `Ch1` `🧠 K1`
Confirming that a work product meets its specified requirements. Asking: *"Are we building the product right?"* Focuses on conformance to specifications.

---

## W

**Walkthrough** `Ch3` `🧠 K1`
A review type led by the author, who guides participants through the work product. Aims to educate, gain consensus, and detect anomalies. Individual review beforehand is optional; scribe is mandatory.

**White-box technique** `Ch4` `💡 K2`
A test technique that derives test cases from the internal structure of the software — code paths, branches, data flows. Tests depend on the implementation. Includes statement testing and branch testing.

**White-box testing** `Ch2` `💡 K2`
A test type where tests are based on the internal structure or implementation of the system. Can be applied at any test level.
