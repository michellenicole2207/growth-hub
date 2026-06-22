# ISTQB CTFL — Common Mistakes

Typical exam traps, easily confused concepts, and tips to avoid falling for them.

---

## Easily Confused Concepts

### Error vs. Defect vs. Failure vs. Root Cause `Ch1`

| Term | What it is | Who creates it |
|---|---|---|
| **Error** | A human mistake | Developer, analyst, tester |
| **Defect** | The flaw the error introduced into the work product | Caused by the error |
| **Failure** | The visible incorrect behavior when the defect is executed | Caused by the defect |
| **Root cause** | The underlying reason the error was made | Process or environment issue |

> **Trap:** "A defect always causes a failure." — FALSE. A defect may never execute, or may only fail under specific conditions.

---

### Testing vs. Quality Assurance `Ch1`

| | Testing | QA |
|---|---|---|
| **Focus** | Product | Process |
| **Goal** | Find defects | Prevent defects |
| **Orientation** | Corrective | Preventive |

> **Trap:** "QA and testing are the same thing." — FALSE. Testing is part of QA, but QA is broader — it covers the entire development process.

---

### Verification vs. Validation `Ch1`

- **Verification** → "Are we building the product **right**?" — conformance to specification
- **Validation** → "Are we building the **right** product?" — fitness for user needs

> **Memory tip:** Validation = Value to the user.

---

### Confirmation Testing vs. Regression Testing `Ch2`

- **Confirmation testing**: re-tests a specific defect that was fixed — did *this* fix work?
- **Regression testing**: re-tests the whole system after any change — did anything *else* break?

> **Trap:** "Regression testing is only needed after bug fixes." — FALSE. Any change (enhancement, refactor, configuration change) can introduce regressions.

---

### Black-box / White-box as Test Types vs. Test Techniques `Ch2` `Ch4`

The same terms appear in two different chapters with related but distinct meanings:

| Context | Meaning |
|---|---|
| **Ch2 — Test types** | *What* the tests are based on: specification (black-box) vs. structure (white-box) |
| **Ch4 — Test techniques** | *How* test cases are derived: from spec (black-box techniques) vs. from code (white-box techniques) |

> **Trap:** Seeing "black-box" in a question and assuming it always means the Ch4 technique. Check what the question is actually asking about.

---

### Static Testing vs. Static Analysis `Ch3`

- **Static testing** = the broad category — evaluating a work product *without executing it* (includes reviews AND tool-based analysis)
- **Static analysis** = the tool-based subset of static testing — automated analysis against a formal syntax

> **Trap:** "Static analysis and static testing are the same." — FALSE. Static analysis is *one type* of static testing.

---

### Walkthrough vs. Technical Review vs. Inspection `Ch3`

| | Walkthrough | Technical Review | Inspection |
|---|---|---|---|
| **Led by** | Author | Moderator | Moderator (NOT author) |
| **Formality** | Low–Medium | Medium–High | Highest |
| **Scribe** | Not required | Depends | Mandatory |
| **Author as leader?** | Yes | No | **Never** |

> **Trap:** "In a walkthrough, individual review beforehand is mandatory." — FALSE. It is *optional* (the syllabus says "not required").
> **Trap:** "In a walkthrough, a scribe is mandatory." — FALSE. A scribe is optional in walkthroughs; the author may even fill the role.
> **Trap:** "In an inspection, the author can lead the review." — FALSE. The author cannot be the review leader or the scribe.

---

### Equivalence Partitioning vs. Boundary Value Analysis `Ch4`

- **EP** — selects *one representative value* from each partition (any value, not necessarily the edge)
- **BVA** — specifically targets the *edges* of ordered partitions; extends EP, doesn't replace it

> **Trap:** "BVA replaces EP." — FALSE. BVA extends EP by adding boundary-specific test cases on top of it.

---

### 2-value BVA vs. 3-value BVA `Ch4`

- **2-value**: boundary value + its closest neighbor from the adjacent partition
- **3-value**: the boundary value itself + the value immediately below it + the value immediately above it

> **Trap:** "3-value BVA tests three partitions." — FALSE. It tests three specific values around one boundary.

---

### Statement Coverage vs. Branch Coverage `Ch4`

- **Statement coverage**: every executable statement run at least once
- **Branch coverage**: every branch (true/false outcome of every decision) exercised

> **Critical rule:** Branch coverage **subsumes** statement coverage — 100% branch coverage guarantees 100% statement coverage. The reverse is NOT true.
> **Trap:** "100% statement coverage means all branches are tested." — FALSE.

---

### Severity vs. Priority `Ch5`

- **Severity** = how badly the defect impacts the system (technical view)
- **Priority** = how urgently it needs to be fixed (business view)

> **Trap:** "A high-severity defect is always high priority." — FALSE.
> Example: a crash in a feature used by 0.1% of users = high severity, low priority.
> Example: a typo on the login page = low severity, high priority.

---

### Test Monitoring vs. Test Control `Ch5`

- **Monitoring** = collecting data and checking progress against the plan (observing)
- **Control** = taking corrective action when deviations are found (acting)

> **Trap:** "Monitoring and control are the same activity." — FALSE. Monitoring without control is just observation.

---

### Product Risk vs. Project Risk `Ch5`

- **Product risk** = risk that the system fails to meet quality expectations → drives *testing* decisions
- **Project risk** = risk to the project schedule, budget, or resources → managed by *project management*

---

## Exam Traps — Statements That Look True But Aren't

| Trap statement | Why it's wrong |
|---|---|
| "Testing proves the software is correct." | Testing shows the *presence* of defects, never their absence (Principle 1) |
| "With enough time, we can test everything." | Exhaustive testing is impossible (Principle 2) |
| "If all tests pass, the software has no defects." | Absence of defects is a fallacy (Principle 7) |
| "More testing always means higher quality." | Testing is context-dependent; more is not always better (Principle 6) |
| "The author can lead or scribe an inspection." | Not allowed — unique rule for inspections |
| "Q1 in the testing quadrants is business-facing." | Q1 is *technology-facing* + supporting the team; Q2 is business-facing |
| "Regression testing only runs after a bug fix." | Any change — enhancements, refactors, migrations — can break existing behavior |
| "100% statement coverage guarantees full testing." | It does not test all branches; branch coverage is stronger |
| "Exploratory testing has no structure." | It uses time-boxed *sessions* guided by a *test charter* |
| "0-switch coverage tests sequences of transitions." | 0-switch = single transitions only, no chaining |
| "White-box testing is always dynamic." | White-box *analysis* can be applied statically to pseudocode or unexecutable code |
| "Planning Poker is the only named estimation technique in CTFL 4.0." | CTFL v4.0.1 names four techniques: Estimation based on ratios, Extrapolation, **Wideband Delphi**, and Three-point estimation. Planning Poker is a *variant* of Wideband Delphi, not a separate technique. |
| "A walkthrough requires individual review beforehand." | Individual review is *optional* in walkthroughs. A scribe is also optional (not mandatory). |
| "BVA can be applied to any partition." | BVA only applies to *ordered* partitions (those with min/max values) |

---

## Tips to Avoid Traps

**Read the question stem carefully.**
ISTQB questions often hinge on a single word: *BEST*, *MOST appropriate*, *EXCEPT*, *NOT*, *LEAST likely*. Missing that word flips the correct answer.

**Know the difference between K-levels in the question.**
- A K1 question asks you to *identify* or *recall* — pick the correct definition.
- A K2 question asks you to *explain* or *distinguish* — pick the most accurate explanation.
- A K3 question gives you a *scenario* — apply the technique and derive the result.

**When two answers both seem correct, go more specific.**
ISTQB prefers the answer that matches the syllabus definition most precisely. The "almost right" answer is usually a distractor that swaps one key word.

**For K3 technique questions, work it on paper.**
Don't try to do EP, BVA, or state transition in your head. Sketch the partitions or table quickly — you'll catch errors you'd miss mentally.

**The syllabus definition wins over industry practice.**
If you've worked in QA for years and something "feels" right, but it contradicts the CTFL 4.0 syllabus definition, go with the syllabus. The exam tests the standard, not real-world variation.

**Watch for absolutes.**
Words like *always*, *never*, *all*, *only*, *impossible* are often traps. Testing principles 1 and 2 specifically address what is and isn't possible in testing.

**When unsure between two answers, eliminate first.**
Cross out the two clearly wrong answers. Then compare the remaining two against the exact syllabus wording — the right answer will use the correct terminology.
