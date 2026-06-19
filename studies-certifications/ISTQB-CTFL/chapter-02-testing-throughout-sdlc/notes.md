# Chapter 2 - Testing Throughout the Software Development Lifecycle

## Key Concepts
- Testing must be adapted to the SDLC model in use
- Good testing practices apply across all SDLC models
- Test levels align with development stages; each has distinct objectives
- Test types can be applied at any test level
- Maintenance testing addresses changes to an already-deployed system

---

## 2.1 Testing in the Context of an SDLC

### SDLC Models

| Model | Description | Testing Approach |
|---|---|---|
| **Sequential** (Waterfall, V-model) | Phases are completed one after another | Testing begins after development; V-model maps each dev stage to a test level |
| **Iterative** (Spiral, RUP) | Requirements and design evolve through repeated cycles | Testing occurs within each iteration |
| **Incremental** (Kanban, Scrum) | System is built and delivered in small pieces | Each increment is tested before the next begins |

> In practice, many projects combine models (e.g., iterative + incremental = Agile).

### Good Testing Practices for Any SDLC
- Every development activity has a corresponding test activity
- Test analysis and design begin as early as possible
- Testers are involved in reviewing documents as soon as drafts are available
- Test levels are defined with clear entry and exit criteria

---

## 2.2 Test Levels

Test levels are groups of test activities organized and managed together.

| Level | Focus | Typical Testers |
|---|---|---|
| **Component testing** (unit) | Individual components in isolation | Developers |
| **Component integration testing** | Interfaces and interactions between components | Developers / Testers |
| **System testing** | End-to-end behavior of the whole system | Independent testers |
| **System integration testing** | Interfaces between the system and external systems | Testers / Ops |
| **Acceptance testing** | System meets business needs; ready for delivery | Business / End users |

### Acceptance Testing Types
- **User Acceptance Testing (UAT)**: Real users validate the system
- **Operational Acceptance Testing (OAT)**: Checks operational readiness (backup, recovery, security)
- **Contractual/Regulatory Acceptance Testing**: Verifies compliance with contracts or regulations
- **Alpha testing**: Performed by internal users at the developer's site
- **Beta testing**: Performed by external users in their own environment

---

## 2.3 Test Types

Test types describe *what* is being tested, independent of the level.

| Type | What it checks |
|---|---|
| **Functional testing** | What the system does — business requirements, features |
| **Non-functional testing** | How the system behaves — performance, security, usability, reliability |
| **Black-box testing** | Behavior without knowledge of internal structure |
| **White-box testing** | Internal structure, code paths, logic |

### Change-Related Testing
- **Confirmation testing** (re-testing): Verifies that a specific defect has been fixed
- **Regression testing**: Ensures that changes have not broken existing functionality

> Regression testing is a strong candidate for automation due to repetition.

---

## 2.4 Maintenance Testing

Triggered when an operational system is modified, migrated, or retired.

### Triggers
- Corrective changes (bug fixes)
- Adaptive changes (new environment, OS upgrade, migration)
- Perfective changes (new features, performance improvements)
- Retirement of a system

### Impact Analysis
- Determines which parts of the system are affected by a change
- Helps decide the scope of regression testing
- Relies on good traceability between test cases and code/requirements

---

## Key Terms
- **SDLC**: Software Development Lifecycle — the process used to plan, create, test, and deliver software
- **Test level**: A group of test activities managed together (component, integration, system, acceptance)
- **Test type**: A classification of testing by objective (functional, non-functional, black-box, white-box)
- **Regression testing**: Re-running tests to detect unintended side effects of a change
- **Confirmation testing**: Re-testing after a defect fix to verify it is resolved
- **Impact analysis**: Evaluating the effect of a change on existing system components and tests
- **Alpha testing**: Early acceptance testing done internally
- **Beta testing**: Acceptance testing done externally by end users
- **UAT**: User Acceptance Testing — business stakeholders validate the system

---

## Practice Questions
- What are the three main categories of SDLC models? Give one example of each.
- What is the difference between component testing and component integration testing?
- What is the difference between confirmation testing and regression testing?
- At which test level is acceptance testing typically performed, and who performs it?
- What triggers maintenance testing?
- Why is regression testing a good candidate for automation?
- What is the purpose of impact analysis in maintenance testing?
