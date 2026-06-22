# Chapter 4 - Test Analysis and Design

> **The big idea:** How do you decide *what* to test and *how* to test it without just guessing?
> Test techniques give you a systematic, repeatable way to design test cases that cover
> what matters — based on specifications, code structure, or your own experience.

---

## Cognitive Levels in This Chapter

> K1 = Remember · K2 = Understand · K3 = Apply — see Chapter 1 for the full legend.

### Learning Objectives for Chapter 4

| LO | K | Topic |
|---|---|---|
| FL-4.1.1 | K2 | Summarize the categories of test techniques and their subcategories |
| FL-4.2.1 | **K3** | Apply equivalence partitioning to derive test cases for a given scenario |
| FL-4.2.2 | **K3** | Apply boundary value analysis to derive test cases for a given scenario |
| FL-4.2.3 | **K3** | Apply decision table testing to derive test cases for a given scenario |
| FL-4.2.4 | **K3** | Apply state transition testing to derive test cases for a given scenario |
| FL-4.3.1 | K2 | Explain statement testing |
| FL-4.3.2 | K2 | Explain branch testing |
| FL-4.3.3 | K2 | Explain the value of white-box testing |
| FL-4.4.1 | K2 | Explain error guessing |
| FL-4.4.2 | K2 | Explain exploratory testing |
| FL-4.4.3 | K2 | Explain checklist-based testing |
| FL-4.5.1 | K2 | Explain the factors that make a good user story (INVEST criteria) |
| FL-4.5.2 | K2 | Recall the typical formats for writing acceptance criteria |
| FL-4.5.3 | K2 | Summarize the activities of the ATDD approach |

> **Exam tip:** The four black-box techniques (FL-4.2.1–4.2.4) are **K3** — the exam will give you a scenario
> and ask you to produce test cases. Practice deriving them, not just explaining them.
> White-box techniques (FL-4.3.1–4.3.2) are only K2 — you explain statement and branch coverage, not calculate it.

---

## 4.1 The Three Categories of Test Techniques — 💡 Understand (K2)

Think of test techniques as three different lenses for looking at a system:

| Category | Also known as | Based on | Key characteristic |
|---|---|---|---|
| **Black-box** | Specification-based | Specified behavior | Tests are independent of implementation — they survive code changes |
| **White-box** | Structure-based | Internal structure/code | Tests depend on how the software is built; created after design/implementation |
| **Experience-based** | — | Tester's knowledge and skill | Complementary to the other two; finds defects the others miss |

> **Memory tip:** Black = you can't see inside the box. White = you can see everything inside. Experience = you've seen similar boxes break before.

---

## 4.2 Black-Box Test Techniques — ⚙️ Apply (K3)

### 4.2.1 Equivalence Partitioning (EP) — ⚙️ Apply (K3)

**The idea:** If the system treats all values in a group the same way, you only need to test one value from that group.

- Divide input (or output) data into **partitions** where all elements are processed identically
- One test case per partition is sufficient
- **Valid partition**: contains values the system should accept
- **Invalid partition**: contains values the system should reject
- **100% EP coverage** = exercise every partition (valid AND invalid) at least once
- Coverage = partitions exercised ÷ total partitions

**When multiple inputs exist:** Use **Each Choice coverage** — at least one value from each partition set appears in at least one test case.

> **Example:** A field accepts ages 18–65. Partitions: under 18 (invalid), 18–65 (valid), over 65 (invalid). You need at least 3 test cases — one per partition.

---

### 4.2.2 Boundary Value Analysis (BVA) — ⚙️ Apply (K3)

**The idea:** Developers make the most mistakes at the edges of a range — so test there.

- Extends EP by specifically targeting the **boundaries** of ordered partitions
- Only applicable to **ordered** partitions (where min/max values exist)

**Two versions:**

| Version | Coverage items per boundary | More rigorous? |
|---|---|---|
| **2-value BVA** | Boundary value + its closest neighbor from the adjacent partition | Less |
| **3-value BVA** | The boundary value itself, the value immediately below it, and the value immediately above it | More — can catch off-by-one errors 2-value misses |

> **Example:** For a range 1–10 using 3-value BVA, test: 0, 1, 2 (lower boundary) and 9, 10, 11 (upper boundary).

**100% coverage:** Exercise all boundary values (2-value) or all boundary values and their neighbors (3-value).

---

### 4.2.3 Decision Table Testing — ⚙️ Apply (K3)

**The idea:** When the system behaves differently depending on combinations of conditions, a table maps every combination to its expected outcome.

- Best for testing **business rules** and complex logic
- Each **column** = one decision rule (a unique combination of conditions + resulting actions)
- Notation:
  - **T** = condition is true, **F** = condition is false
  - **–** = condition is irrelevant to the outcome
  - **N/A** = condition is infeasible for this rule
  - **X** = action occurs, **blank** = action does not occur

**100% coverage** = exercise all columns with feasible condition combinations.
Coverage = feasible columns exercised ÷ total feasible columns.

> **Note:** Coverage is measured against the actual columns in the table being used. If the table has been minimized (rules collapsed), coverage is calculated against its actual columns — not against the theoretical 2ⁿ maximum.

**Strength:** Reveals gaps and contradictions in requirements; systematic — nothing gets overlooked.
**Weakness:** With many conditions, the number of rules grows exponentially (2ⁿ). Use a minimized table or risk-based approach to reduce scope.

---

### 4.2.4 State Transition Testing — ⚙️ Apply (K3)

**The idea:** Some systems behave differently depending on their current state. This technique tests those state-dependent behaviors.

**Key concepts:**
- **State diagram**: shows all possible states and the valid transitions between them
  - Transition syntax: `event [guard condition] / action`
- **State table**: equivalent to a state diagram; rows = states, columns = events; empty cells = invalid transitions

A test case = a sequence of events that produces a sequence of state changes.

**Three coverage criteria (weakest → strongest):**

| Coverage | What it exercises | Notes |
|---|---|---|
| **All states** | All states at least once | Weakest — can be achieved without testing all transitions |
| **Valid transitions** (0-switch) | All valid transitions — each valid transition exercised at least once, without chaining sequences (0-switch = single steps only) | Most widely used criterion |
| **All transitions** | All valid + all invalid transitions | Strongest; required for mission/safety-critical software |

> **Key exam point:** Achieving valid transitions coverage guarantees all states coverage. Achieving all transitions coverage guarantees both.
> Test only **one** invalid transition per test case to avoid defect masking.

---

## 4.3 White-Box Test Techniques — 💡 Understand (K2)

### 4.3.1 Statement Testing — 💡 Understand (K2)

- **Coverage items:** executable statements
- Aim: design test cases to execute statements until an acceptable coverage level is reached
- **100% statement coverage** = every executable statement run at least once
- Coverage = statements exercised ÷ total executable statements

**Limitation:** 100% statement coverage does NOT guarantee all branches are tested. A defect that only triggers under a specific condition may be missed.

---

### 4.3.2 Branch Testing — 💡 Understand (K2)

- **Coverage items:** branches — transfers of control between nodes in a control flow graph
- Branches can be **unconditional** (straight-line code) or **conditional** (if/else, switch, loop decisions)
- **100% branch coverage** = all branches exercised
- Coverage = branches exercised ÷ total branches

> **Critical rule: Branch coverage subsumes statement coverage.**
> If you achieve 100% branch coverage, you automatically achieve 100% statement coverage.
> The reverse is NOT true.

**Limitation:** Doesn't detect defects that only appear on a specific path through the code.

---

### 4.3.3 The Value of White-Box Testing — 💡 Understand (K2)

**Strength:** Takes the entire implementation into account — can find defects even when the spec is vague, outdated, or incomplete.

**Weakness:** If the software is missing a required feature entirely (defect of omission), white-box testing won't detect it — it only tests what's there.

**Also useful in static analysis:** White-box *analysis* (a form of static testing) can be applied to pseudocode or unexecutable code to review structure without running it. White-box *testing* (dynamic) requires executable code — don't confuse the two.

> Black-box testing alone gives you no measure of actual code coverage. White-box testing provides that objective measurement.

---

## 4.4 Experience-Based Test Techniques — 💡 Understand (K2)

### 4.4.1 Error Guessing — 💡 Understand (K2)

**The idea:** Use what you know about how software breaks to anticipate where it will break.

Based on the tester's knowledge of:
- How the application has worked (or failed) in the past
- Types of mistakes developers typically make
- Types of failures common in similar applications

**Fault attacks:** Create a structured list of likely errors, defects, and failures → design tests specifically to expose them. Lists can come from experience, defect data, or common failure knowledge.

---

### 4.4.2 Exploratory Testing — 💡 Understand (K2)

**The idea:** Design, execute, and evaluate tests simultaneously while learning about the system.

- Testing is used to learn, explore deeper, and find untested areas
- **Session-based approach:** testing within a defined time box, guided by a **test charter** containing test objectives
- Each session ends with a **debriefing** with stakeholders

**Best used when:**
- Specifications are few, inadequate, or missing
- There's significant time pressure
- You want to complement more formal techniques

**More effective when the tester:** is experienced, has domain knowledge, and brings analytical thinking, curiosity, and creativity.

---

### 4.4.3 Checklist-Based Testing — 💡 Understand (K2)

**The idea:** Use a prepared checklist of test conditions to guide testing — especially when detailed test cases don't exist.

- Items are often phrased as questions
- Built from experience, user knowledge, and understanding of how software fails
- Should be **regularly updated** based on defect analysis — checklists can wear out just like tests

**Do NOT include in checklists** *(industry guidance — not explicitly listed in the CTFL 4.0 syllabus):*
- Items that can be checked automatically
- Items better suited as entry/exit criteria
- Items that are too general

**Trade-off:** High-level checklists provide consistency and coverage breadth, but less repeatability than detailed test cases.

---

## 4.5 Collaboration-Based Test Approaches — 💡 Understand (K2)

Unlike the other techniques (which focus on *finding* defects), collaboration-based approaches focus on **avoiding defects through shared understanding**.

### 4.5.1 Collaborative User Story Writing — 💡 Understand (K2)

A **user story** represents a feature valuable to a user or purchaser. Every user story has **3 Cs** (Jeffries 2000):

| C | What it is |
|---|---|
| **Card** | The medium describing the story (index card, electronic board entry) |
| **Conversation** | Explains how the software will be used (verbal or documented) |
| **Confirmation** | The acceptance criteria |

**Standard format:** *"As a [role], I want [goal], so that I can [resulting business value]."*

**Good user stories follow INVEST:**
- **I**ndependent
- **N**egotiable
- **V**aluable
- **E**stimable
- **S**mall
- **T**estable

> If a stakeholder can't imagine how to test a user story, it's a signal the story is unclear or not valuable enough.

---

### 4.5.2 Acceptance Criteria — 💡 Understand (K2)

Acceptance criteria are the **conditions a user story must meet to be accepted** by stakeholders. They are essentially the test conditions for acceptance testing.

**Used to:**
- Define the scope of the user story
- Reach consensus among stakeholders
- Describe both positive and negative scenarios
- Serve as the basis for acceptance tests
- Allow accurate planning and estimation

**Two most common formats:**

| Format | Example |
|---|---|
| **Scenario-oriented** (BDD) | Given [context], When [action], Then [outcome] |
| **Rule-oriented** | Bullet point verification list or input-output mapping table |

---

### 4.5.3 Acceptance Test-Driven Development (ATDD) — 💡 Understand (K2)

**The idea:** Write test cases *before* implementing the user story, using the acceptance criteria as the guide.

**How it works:**
1. **Specification workshop**: team (customers + developers + testers) analyzes the user story and acceptance criteria together; resolves ambiguities and gaps
2. **Test case creation**: test cases are created based on acceptance criteria; they serve as examples of correct behavior
3. **Implementation**: developers write code to pass the test cases

**Order of test cases:** positive (happy path) → negative → non-functional quality characteristics (e.g., performance, usability)

Test cases must be expressed in language **understandable by stakeholders** (natural language: preconditions, inputs, postconditions).

> When captured in an automation framework format, acceptance tests become **executable requirements**.

---

## Key Terms Cheat Sheet — 🧠 Remember (K1)

| Term | Definition |
|---|---|
| **Black-box technique** | Derives tests from specified behavior; independent of internal structure |
| **White-box technique** | Derives tests from internal structure/code |
| **Experience-based technique** | Uses tester's knowledge and experience to design tests |
| **Equivalence partitioning** | Divides data into partitions processed identically; one test per partition |
| **Boundary value analysis** | Tests at the edges of equivalence partitions |
| **Decision table testing** | Tests combinations of conditions and their resulting actions |
| **State transition testing** | Tests behavior based on system states and transitions between them |
| **Statement coverage** | % of executable statements exercised by tests |
| **Branch coverage** | % of branches exercised; subsumes statement coverage |
| **Error guessing** | Anticipating defects based on experience and failure knowledge |
| **Exploratory testing** | Simultaneous design, execution, and evaluation within a time-boxed session |
| **Checklist-based testing** | Testing guided by a prepared list of conditions, often as questions |
| **User story** | A description of a feature valuable to a user; has Card, Conversation, Confirmation |
| **INVEST** | Criteria for a good user story: Independent, Negotiable, Valuable, Estimable, Small, Testable |
| **Acceptance criteria** | Conditions a user story must meet to be accepted; test conditions for acceptance tests |
| **ATDD** | Test cases written before the user story is implemented, based on acceptance criteria |

---

## Practice Questions

- What are the three categories of test techniques and how do they differ?
- In equivalence partitioning, why is one test per partition considered sufficient?
- What is the difference between 2-value BVA and 3-value BVA? When would you use each?
- What does each symbol mean in a decision table (T, F, –, N/A, X)?
- What are the three state transition coverage criteria, from weakest to strongest?
- Why should you test only one invalid transition per test case in state transition testing?
- What does "branch coverage subsumes statement coverage" mean?
- What is the main strength and weakness of white-box testing?
- What is a fault attack in error guessing?
- When is exploratory testing most useful?
- What are the 3 Cs of a user story?
- What does INVEST stand for?
- What are the two most common formats for writing acceptance criteria?
- What happens in the specification workshop in ATDD?
- What is the main difference between defect detection techniques (4.2–4.4) and collaboration-based approaches (4.5)?
