# Chapter 2 - Testing Throughout the Software Development Lifecycle

> **The big idea:** Testing doesn't happen at the end. It lives inside every phase of development,
> adapts to whatever model the team uses, and changes shape depending on the context.

---

## Cognitive Levels in This Chapter

> K1 = Remember · K2 = Understand · K3 = Apply — see Chapter 1 for the full legend.

### Learning Objectives for Chapter 2

| LO | K | Topic |
|---|---|---|
| FL-2.1.1 | K2 | Explain the impact of the chosen SDLC model on testing |
| FL-2.1.2 | K1 | Recall good testing practices that apply to any SDLC model |
| FL-2.1.3 | K1 | Recall examples of TDD, ATDD, and BDD |
| FL-2.1.4 | K2 | Summarize the DevOps benefits for testing |
| FL-2.1.5 | K2 | Explain the shift-left approach |
| FL-2.1.6 | K2 | Explain how retrospectives can be used for process improvement in testing |
| FL-2.2.1 | K2 | Distinguish the different test levels |
| FL-2.2.2 | K2 | Distinguish the different test types |
| FL-2.2.3 | K2 | Distinguish confirmation testing from regression testing |
| FL-2.3.1 | K2 | Summarize the triggers for maintenance testing |
| FL-2.3.2 | K2 | Explain the role of impact analysis for maintenance testing |

> **Exam tip:** No K3 in this chapter. K1 items are FL-2.1.2 and FL-2.1.3 — just recall, no explanation needed.
> Everything else requires you to *explain* or *distinguish*.

---

## 2.1 Testing in the Context of an SDLC — 💡 Understand (K2)

An SDLC model defines how development phases and activities relate to each other. The choice of model directly impacts **how** testing is done — not whether testing is done.

### The three main SDLC model categories — 💡 Understand (K2)

| Model | Examples | How testing fits |
|---|---|---|
| **Sequential** | Waterfall, V-model | Testing begins after development; V-model maps each dev stage to a test level |
| **Iterative** | Spiral, Prototyping | Testing occurs within each repeated cycle |
| **Incremental** | Unified Process | Each small increment is tested before moving to the next |

> In practice, many real projects combine models — e.g., Agile uses both iterative and incremental approaches.
> Agile practices like Scrum, Kanban, TDD, BDD, and XP are methods that operate *within* these model types.

### The SDLC impacts testing in 5 ways — 💡 Understand (K2)
1. Scope and timing of test activities (when and what gets tested)
2. Level of detail of test documentation
3. Choice of test techniques and approach
4. Extent of test automation
5. Roles and responsibilities of testers

### Good testing practices — apply to ANY SDLC model — 🧠 Remember (K1)
- Every development activity has a corresponding test activity
- Different test levels have specific and different test objectives
- Test analysis and design begin during the corresponding development phase
- Testers review work products as soon as drafts are available

---

## Testing as a Driver: TDD, ATDD, and BDD — 🧠 Remember (K1)

These approaches are examples of **test-first approaches** to development — they flip the traditional order so that **tests are written before the code**.

| Approach | Who uses it | How it works |
|---|---|---|
| **TDD** (Test-Driven Development) | Developers | Write a failing test → write code to pass it → refactor. TDD was designed to replace extensive upfront software design. |
| **ATDD** (Acceptance Test-Driven Development) | Whole team | Tests are derived from acceptance criteria "as part of the system design process" before the feature is built. |
| **BDD** (Behavior-Driven Development) | Whole team | Write tests in plain language using Given/When/Then format; test cases "should then be automatically translated into executable tests." |

All three implement the **early testing principle** and support **shift left**. They also support an **iterative development model** in addition to early testing and shift left.

> **Exam tip (K1):** For FL-2.1.3, you only need to recall who uses each approach and its core idea. The "how it works" details in the table are for context — the exam tests recognition, not reproduction of the procedure.

---

## DevOps and Testing — 💡 Understand (K2)

DevOps bridges development, testing, and operations to deliver high-quality software faster.

**Benefits for testing:**
- Fast feedback on code quality via CI/CD pipelines
- Automated regression tests run on every commit
- Visibility on non-functional quality (performance, reliability) increases
- Reduces repetitive manual testing through automation
- CI promotes shift left in testing by encouraging developers to submit high-quality code accompanied by component tests and static analysis
- Automated processes like CI/CD facilitate establishing stable test environments

> **Exam scope:** The *benefits* of DevOps for testing are directly tested (FL-2.1.4, K2). The risks below are supporting context not covered by a specific LO — understand them but don't memorize them.

**Risks and challenges:**
- DevOps pipeline must be defined and maintained
- Test automation requires additional resources
- CI/CD tools must be introduced and kept up to date

> Even with heavy automation, manual testing — especially from the user's perspective — is still needed.

---

## Shift Left — 💡 Understand (K2)

Shift left means **testing earlier in the SDLC** — not waiting until the code is complete.

Good practices to achieve shift left:
- Review specifications from a tester's perspective (find ambiguities early)
- Write test cases before the code is written
- Use CI/CD to get fast feedback on every code commit
- Perform static analysis before dynamic testing
- Start non-functional testing at the component level, where possible

> Shift left may increase early effort and cost, but it saves significantly more later.

> **Important:** For shift left to work, stakeholders must be convinced and bought into the concept. Without stakeholder buy-in, the additional upfront effort cannot be justified.

---

## Retrospectives and Process Improvement — 💡 Understand (K2)

Retrospectives are held at the end of an iteration, project, or release milestone. Participants (not only testers — also developers, architects, product owners, business analysts) discuss:
- What went well and should be retained?
- What didn't go well and could be improved?
- How to incorporate improvements going forward?

**Benefits for testing:**
- Increased test effectiveness and efficiency
- Improved quality of testware
- Team bonding and learning
- Better cooperation between development and testing
- Improved quality of the test basis — deficiencies in the extent and quality of requirements are identified and addressed

---

## 2.2 Test Levels and Test Types — 💡 Understand (K2)

### Test Levels — the five levels — 💡 Understand (K2)

Each level has a different focus, test basis, and set of objectives.

| Level | Focus | Typically performed by |
|---|---|---|
| **Component testing** (unit) | Individual components in isolation | Developers |
| **Component integration testing** | Interfaces and interactions between components | Developers / Testers |
| **System testing** | End-to-end behavior of the entire system | Independent testers |
| **System integration testing** | Interfaces between the system and external systems/services | Testers |
| **Acceptance testing** | Validation; demonstrating readiness for deployment | Business / End users |

> **How test levels are distinguished (K2):** Test levels differ from each other by the following attributes: **test object** (what is being tested), **test objectives** (why it is tested), **test basis** (what the tests are based on), **defects and failures** (what types are typically found), and **approach and responsibilities** (who does it and how).

**How SDLC model affects test levels:**
- **Sequential models:** Testers participate in requirements reviews and test design in early phases; dynamic testing only happens in later phases when executable code exists.
- **Agile models:** Lightweight documentation, extensive test automation for regression, experience-based techniques favored for manual testing.
- **Iterative/incremental models:** Both static and dynamic testing can occur at all test levels within each iteration. Frequent delivery requires fast feedback and extensive regression testing.

### Acceptance Testing Types — 💡 Understand (K2)
- **UAT** (User Acceptance Testing): Real users validate the system meets their needs
- **OAT** (Operational Acceptance Testing): Operational readiness — backup, recovery, security
- **Contractual/Regulatory**: Verifies compliance with contracts or regulations
- **Alpha testing**: Internal users test at the developer's site
- **Beta testing**: External users test in their own environment

### Test Types — what aspect is being tested — 💡 Understand (K2)

| Type | What it checks |
|---|---|
| **Functional testing** | What the system does — functional completeness, correctness, appropriateness |
| **Non-functional testing** | How well the system behaves — ISO/IEC 25010 characteristics: Functional suitability, Performance efficiency, Compatibility, Usability, Reliability, Security, Maintainability, Portability, Safety |
| **Black-box testing** | Behavior based on specifications, without knowledge of internal structure |
| **White-box testing** | Internal structure — code paths, architecture, data flows |

> All four test types can be applied at **any** test level.

> **Note:** "Black-box" and "white-box" appear in both Chapter 2 (as test *types*) and Chapter 4 (as test *technique categories*). In Chapter 2 they classify *what the tests are based on* (spec vs. structure); in Chapter 4 they classify *how test cases are derived*. Same terms, related but distinct meaning — don't let it confuse you.

### Change-Related Testing — 💡 Understand (K2)
- **Confirmation testing**: Verifies that a specific defect has been fixed

  > Two approaches to confirmation testing: (1) Execute all test cases that previously failed due to the defect. (2) Add new tests to cover changes made to fix the defect. When time is short, confirmation testing may be limited to simply reproducing the failure that triggered the defect report.

- **Regression testing**: Ensures that changes haven't broken existing functionality

> Regression testing grows with every release — it's a strong candidate for automation.

---

## 2.3 Maintenance Testing — 💡 Understand (K2)

Maintenance testing is triggered when a system that's already in production needs to change.

### Triggers (v4 categories) — 💡 Understand (K2)
| Trigger | Examples |
|---|---|
| **Modifications** | Planned enhancements, corrective changes (bug fixes), hot fixes |
| **Upgrades or migrations** | Moving to a new platform, OS, or environment |
| **Retirement** | End of life — data archiving and retrieval testing |

### Scope depends on — 💡 Understand (K2)
- Degree of risk of the change
- Size of the existing system
- Size of the change

### Impact Analysis — 💡 Understand (K2)
Before testing, **impact analysis** determines which parts of the system could be affected by the change. This helps define the scope of regression testing and relies on good traceability.

---

## Key Terms Cheat Sheet — 🧠 Remember (K1)

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
