# Chapter 3 - Static Testing

> **The big idea:** You don't need to run software to find problems in it.
> Reviewing documents, designs, and code before execution often catches defects earlier,
> cheaper, and in places dynamic testing simply can't reach.

---

## Cognitive Levels in This Chapter

> K1 = Remember · K2 = Understand · K3 = Apply — see Chapter 1 for the full legend.

### Learning Objectives for Chapter 3

| LO | K | Topic |
|---|---|---|
| FL-3.1.1 | K1 | Recall work products that can be examined by static testing |
| FL-3.1.2 | K2 | Explain the value of static testing |
| FL-3.1.3 | K2 | Compare static testing and dynamic testing |
| FL-3.2.1 | K1 | Recall the activities, roles, and responsibilities of a formal review |
| FL-3.2.2 | K2 | Explain how the different review types differ from one another |
| FL-3.2.3 | K1 | Recall the factors for a successful review |

> **Exam tip:** No K3 in this chapter. Three K1 items (FL-3.1.1, FL-3.2.1, FL-3.2.3) — pure recall.
> FL-3.1.3 and FL-3.2.2 require you to *compare* and *explain differences* — classic K2.

---

## 3.1 Static Testing Basics — 💡 Understand (K2)

Static testing means evaluating a work product **without executing it**. It can be done:
- **Manually** — through reviews (walkthroughs, inspections, etc.)
- **With tools** — through static analysis (e.g., linters, code analyzers integrated into CI pipelines)

It applies to both **verification** and **validation**, and its objectives include improving quality, detecting defects, and assessing readability, completeness, correctness, testability, and consistency.

---

## What Can Be Examined with Static Testing? — 🧠 Remember (K1)

Almost **any work product** — as long as it can be read and understood:

- Requirement specification documents
- Source code
- Test plans and test cases
- Product backlog items, test charters
- Project documentation, contracts, and models

**For static analysis specifically**, the work product needs a formal syntax (e.g., code, models, or structured text).

**NOT appropriate** for static testing: work products that are difficult for humans to interpret or that can't be analyzed by tools for legal reasons (e.g., 3rd party executable code).

---

## Why Bother? The Value of Static Testing — 💡 Understand (K2)

Static testing is powerful because:

1. **It catches defects early** — before they get baked into later work products and become expensive to fix
2. **It finds things dynamic testing can't** — like unreachable code, design flaws, or defects in non-executable documents
3. **It builds shared understanding** — reviewing requirements together aligns the team early
4. **It's cost-effective** — the upfront cost of reviews is far lower than the cost of finding those same defects late in the project

### Defects that are easier and cheaper to find through static testing — 💡 Understand (K2)

| Category | Examples |
|---|---|
| Requirements defects | Inconsistencies, ambiguities, contradictions, omissions, duplications |
| Design defects | Inefficient database structures, poor modularization |
| Coding defects | Undefined values, undeclared variables, unreachable/duplicated code, excessive complexity |
| Standards deviations | Naming convention violations, coding standard violations |
| Interface defects | Mismatched number, type, or order of parameters |
| Security vulnerabilities | Buffer overflows |
| Test basis gaps | Missing tests for an acceptance criterion |

---

## Static vs. Dynamic Testing — Side by Side — 💡 Understand (K2)

| Aspect | Static Testing | Dynamic Testing |
|---|---|---|
| Needs execution? | No | Yes |
| How defects are found | Directly | Via failures → root cause analysis |
| Applicable to | Executable AND non-executable work products | Executable work products only |
| Rare code paths | Easier to detect | Hard to reach |
| Quality characteristics | Maintainability, readability | Performance, reliability |

> Think of it this way: **static testing reads the recipe**, while **dynamic testing tastes the dish**.

---

## 3.2 Feedback and Review Process — 💡 Understand (K2)

### Why Early and Frequent Stakeholder Feedback Matters — 💡 Understand (K2)

If stakeholders aren't involved regularly during development, the product may drift from their original vision. The consequences:
- Costly rework
- Missed deadlines
- Blame games
- Project failure

Frequent feedback throughout the SDLC:
- Prevents misunderstandings about requirements early
- Ensures changes are understood and implemented before they become expensive
- Keeps the team focused on what delivers the most value
- Addresses risks proactively

---

## The Review Process — 5 Activities — 🧠 Remember (K1)

Based on the **ISO/IEC 20246** standard:

| Step | What happens |
|---|---|
| **1. Planning** | Define scope, purpose, exit criteria, effort, and timeframes |
| **2. Review initiation** | Ensure all participants have access, understand their role, and are prepared |
| **3. Individual review** | Each reviewer independently assesses the work product; logs anomalies, recommendations, and questions |
| **4. Communication and analysis** | Anomalies are discussed in a review meeting; decisions made on status, ownership, and follow-up actions |
| **5. Fixing and reporting** | The **author** fixes the defects found; the **review leader** writes the review report; the work product is accepted once exit criteria are met |

---

## Roles in a Review — Who Does What? — 🧠 Remember (K1)

| Role | Responsibility |
|---|---|
| **Manager** | Decides what gets reviewed; provides resources (people, time) |
| **Author** | Creates and later fixes the work product under review |
| **Moderator** (facilitator) | Runs the review meeting; handles mediation, time, and ensures a safe environment |
| **Scribe** (recorder) | Records anomalies, decisions, and new findings during the meeting |
| **Reviewer** | Performs the actual review; can be a team member, SME, or any stakeholder |
| **Review leader** | Owns the review overall; decides who participates, when, and where |

> **Memory tip:** Think of a review as a structured meeting with a **boss** (manager), a **creator** (author), a **referee** (moderator), a **note-taker** (scribe), **evaluators** (reviewers), and an **organizer** (review leader).

---

## Review Types — From Least to Most Formal — 💡 Understand (K2)

| Type | Formality | Led by | Key characteristics |
|---|---|---|---|
| **Informal review** | Lowest | Anyone | No defined process; no formal output; just find anomalies |
| **Walkthrough** | Low–Medium | **Author** | Author guides the team through the work product; educates, gains consensus, detects anomalies; individual review beforehand is optional; **scribe is mandatory** |
| **Technical review** | Medium–High | **Trained moderator or peer leader** | Technically qualified reviewers; focus on consensus on technical problems and detecting anomalies |
| **Inspection** | Highest | **Moderator** (NOT the author) | Follows the full defined process; maximum anomaly detection is the main goal; metrics are collected; **author cannot be review leader or scribe** |

> **Key exam point:** In an inspection, the **author cannot act as review leader or scribe** — this is unique to this review type.

---

## Success Factors for Reviews — 🧠 Remember (K1)

A review succeeds when:

- Objectives are **clear and measurable** — evaluation of participants is **never** an objective
- The **right review type** is chosen for the work product and context
- Reviews are done on **small chunks** so reviewers stay focused
- **Feedback** is given to stakeholders and authors so they can improve
- Participants have **adequate preparation time**
- **Management supports** the review process
- Reviews are part of the **organization's culture**
- All participants receive **adequate training**
- Meetings are **facilitated effectively**

---

## Key Terms Cheat Sheet — 🧠 Remember (K1)

| Term | Definition |
|---|---|
| **Static testing** | Evaluating a work product without executing it |
| **Dynamic testing** | Testing by executing the software |
| **Static analysis** | Tool-assisted evaluation against a formal syntax |
| **Review** | Manual evaluation of a work product by one or more people |
| **Inspection** | Most formal review type; follows a complete defined process; author cannot be leader or scribe |
| **Technical review** | Review led by a moderator with technically qualified reviewers |
| **Walkthrough** | Review led by the author |
| **Informal review** | Review with no defined process or formal output |
| **Anomaly** | Any result that differs from what is expected; identified during a review |
| **Moderator** | Ensures the effective running of a review meeting |

---

## Practice Questions

- What is static testing and how does it differ from dynamic testing?
- What types of work products can be examined by static testing?
- Name three defect types that are easier to find through static testing.
- What are the five activities in the review process?
- What are the six principal roles in a review? What does each one do?
- What is the most formal review type and what makes it unique?
- What is the main difference between a walkthrough and a technical review?
- Why can't the author be the review leader or scribe in an inspection?
- List four success factors for reviews.
- Why should evaluation of participants never be an objective of a review?
