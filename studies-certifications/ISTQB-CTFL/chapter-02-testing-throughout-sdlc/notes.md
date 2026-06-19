# Chapter 2 - Testing Throughout the Software Development Lifecycle

> **The big idea:** Testing doesn't happen at the end. It lives inside every phase of development,
> adapts to whatever model the team uses, and changes shape depending on the context.

---

## 2.1 Testing in the Context of an SDLC

An SDLC model defines how development phases and activities relate to each other. The choice of model directly impacts **how** testing is done — not whether testing is done.

### The three main SDLC model categories

| Model | Examples | How testing fits |
|---|---|---|
| **Sequential** | Waterfall, V-model | Testing begins after development; V-model maps each dev stage to a test level |
| **Iterative** | Spiral, Prototyping | Testing occurs within each repeated cycle |
| **Incremental** | Unified Process | Each small increment is tested before moving to the next |

> In practice, many real projects combine models — e.g., Agile uses both iterative and incremental approaches.
> Agile practices like Scrum, Kanban, TDD, BDD, and XP are methods that operate *within* these model types.

### The SDLC impacts testing in 5 ways:
1. Scope and timing of test activities (when and what gets tested)
2. Level of detail of test documentation
3. Choice of test techniques and approach
4. Extent of test automation
5. Roles and responsibilities of testers

### Good testing practices — apply to ANY SDLC model
- Every development activity has a corresponding test activity
- Different test levels have specific and different test objectives
- Test analysis and design begin during the corresponding development phase
- Testers review work products as soon as drafts are available

---

## Testing as a Driver: TDD, ATDD, and BDD

These approaches flip the traditional order — **tests are written before the code**.

| Approach | Who uses it | How it works |
|---|---|---|
| **TDD** (Test-Driven Development) | Developers | Write a failing test → write code to pass it → refactor |
| **ATDD** (Acceptance Test-Driven Development) | Whole team | Derive tests from acceptance criteria before the feature is built |
| **BDD** (Behavior-Driven Development) | Whole team | Write tests in plain language using Given/When/Then format |

All three implement the **early testing principle** and support **shift left**.

---

## DevOps and Testing

DevOps bridges development, testing, and operations to deliver high-quality software faster.

**Benefits for testing:**
- Fast feedback on code quality via CI/CD pipelines
- Automated regression tests run on every commit
- Visibility on non-functional quality (performance, reliability) increases
- Reduces repetitive manual testing through automation

**Risks and challenges:**
- DevOps pipeline must be defined and maintained
- Test automation requires additional resources
- CI/CD tools must be introduced and kept up to date

> Even with heavy automation, manual testing — especially from the user's perspective — is still needed.

---

## Shift Left

Shift left means **testing earlier in the SDLC** — not waiting until the code is complete.

Good practices to achieve shift left:
- Review specifications from a tester's perspective (find ambiguities early)
- Write test cases before the code is written
- Use CI/CD to get fast feedback on every code commit
- Perform static analysis before dynamic testing
- Start non-functional testing at the component level, where possible

> Shift left may increase early effort and cost, but it saves significantly more later.

---

## Retrospectives and Process Improvement

Retrospectives are held at the end of an iteration, project, or release milestone. Participants (not only testers — also developers, architects, product owners, business analysts) discuss:
- What went well and should be retained?
- What didn't go well and could be improved?
- How to incorporate improvements going forward?

**Benefits for testing:**
- Increased test effectiveness and efficiency
- Improved quality of testware
- Team bonding and learning
- Better cooperation between development and testing

---

## 2.2 Test Levels and Test Types

### Test Levels — the five levels

Each level has a different focus, test basis, and set of objectives.

| Level | Focus | Typically performed by |
|---|---|---|
| **Component testing** (unit) | Individual components in isolation | Developers |
| **Component integration testing** | Interfaces and interactions between components | Developers / Testers |
| **System testing** | End-to-end behavior of the entire system | Independent testers |
| **System integration testing** | Interfaces between the system and external systems/services | Testers |
| **Acceptance testing** | Validation; demonstrating readiness for deployment | Business / End users |

### Acceptance Testing Types
- **UAT** (User Acceptance Testing): Real users validate the system meets their needs
- **OAT** (Operational Acceptance Testing): Operational readiness — backup, recovery, security
- **Contractual/Regulatory**: Verifies compliance with contracts or regulations
- **Alpha testing**: Internal users test at the developer's site
- **Beta testing**: External users test in their own environment

### Test Types — what aspect is being tested

| Type | What it checks |
|---|---|
| **Functional testing** | What the system does — functional completeness, correctness, appropriateness |
| **Non-functional testing** | How well the system behaves — performance, security, usability, reliability, maintainability, portability, safety |
| **Black-box testing** | Behavior based on specifications, without knowledge of internal structure |
| **White-box testing** | Internal structure — code paths, architecture, data flows |

> All four test types can be applied at **any** test level.

### Change-Related Testing
- **Confirmation testing**: Verifies that a specific defect has been fixed
- **Regression testing**: Ensures that changes haven't broken existing functionality

> Regression testing grows with every release — it's a strong candidate for automation.

---

## 2.3 Maintenance Testing

Maintenance testing is triggered when a system that's already in production needs to change.

### Triggers (v4 categories)
| Trigger | Examples |
|---|---|
| **Modifications** | Planned enhancements, corrective changes (bug fixes), hot fixes |
| **Upgrades or migrations** | Moving to a new platform, OS, or environment |
| **Retirement** | End of life — data archiving and retrieval testing |

### Scope depends on:
- Degree of risk of the change
- Size of the existing system
- Size of the change

### Impact Analysis
Before testing, **impact analysis** determines which parts of the system could be affected by the change. This helps define the scope of regression testing and relies on good traceability.

---

## Key Terms Cheat Sheet

| Term | Definition |
|---|---|
| **SDLC** | Software Development Lifecycle — the process to plan, create, test, and deliver software |
| **Test level** | A group of test activities organized together (component, integration, system, acceptance) |
| **Test type** | Classification by what is being tested (functional, non-functional, black-box, white-box) |
| **Shift left** | Testing earlier in the lifecycle to catch defects sooner |
| **TDD** | Tests are written before the code to drive development |
| **BDD** | Tests are written in Given/When/Then natural language format |
| **Regression testing** | Re-running tests to detect unintended side effects of a change |
| **Confirmation testing** | Re-testing after a fix to verify the defect is resolved |
| **Impact analysis** | Evaluating which parts of the system are affected by a change |

---

## Practice Questions

- What are the three main SDLC model categories? Give one example of each.
- How does the choice of SDLC model impact testing? Name at least three ways.
- What is the difference between TDD, ATDD, and BDD?
- What are the benefits and risks of DevOps for testing?
- What does "shift left" mean and how can you achieve it?
- What is the difference between component testing and component integration testing?
- What is the difference between confirmation testing and regression testing?
- What are the three triggers for maintenance testing in v4?
- Why is regression testing a good candidate for automation?
- What is the purpose of impact analysis in maintenance testing?
