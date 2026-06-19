# Chapter 3 - Static Testing

## Key Concepts
- Static testing evaluates work products without executing the software
- Can be performed manually (reviews) or with tools (static analysis)
- Applies to both verification and validation
- Detects defects earlier and cheaper than dynamic testing
- Some defect types can only be found by static testing

---

## 3.1 Static Testing Basics

Static testing does not require code execution. Work products are evaluated through manual examination (e.g., reviews) or with tools (e.g., static analysis). It can improve quality, detect defects, and assess characteristics like readability, completeness, correctness, testability, and consistency.

Static analysis is often incorporated into CI frameworks and is used to detect code defects, evaluate maintainability, and identify security issues.

---

## 3.1.1 Work Products Examinable by Static Testing

Almost any work product can be examined, including:
- Requirement specification documents
- Source code
- Test plans and test cases
- Product backlog items
- Test charters
- Project documentation, contracts, and models

For **static analysis**, work products need a formal syntax (e.g., models, code, or text with formal syntax).

Work products **not appropriate** for static testing: those difficult to interpret by humans or that should not be analyzed by tools (e.g., 3rd party executable code due to legal reasons).

---

## 3.1.2 Value of Static Testing

- Detects defects in the earliest phases of the SDLC (supports the early testing principle)
- Can identify defects that **cannot** be detected by dynamic testing (e.g., unreachable code, defects in non-executable work products)
- Builds confidence in work products and evaluates their quality
- Creates shared understanding among stakeholders
- Improves communication between involved stakeholders
- Overall project costs are lower even when reviews have an upfront cost
- Certain code defects are found more efficiently through static analysis than dynamic testing

---

## 3.1.3 Differences between Static Testing and Dynamic Testing

| Aspect | Static Testing | Dynamic Testing |
|---|---|---|
| Code execution | Not required | Required |
| How defects are found | Directly | Via failures, then root cause analysis |
| Work products | Executable and non-executable | Executable only |
| Rarely executed paths | Easier to detect | Harder to reach |
| Quality characteristics | Maintainability, readability | Performance, reliability |

### Defects easier to find through static testing
- Requirements defects (inconsistencies, ambiguities, contradictions, omissions, duplications)
- Design defects (inefficient database structures, poor modularization)
- Coding defects (undefined values, undeclared variables, unreachable/duplicated code, excessive complexity)
- Deviations from standards (naming conventions, coding standards)
- Incorrect interface specifications (mismatched number, type or order of parameters)
- Security vulnerabilities (e.g., buffer overflows)
- Gaps in test basis coverage (e.g., missing tests for an acceptance criterion)

---

## 3.2 Feedback and Review Process

### 3.2.1 Benefits of Early and Frequent Stakeholder Feedback

Without regular stakeholder involvement, the product may not meet the stakeholder's vision, leading to costly rework, missed deadlines, and project failure.

Frequent feedback throughout the SDLC:
- Prevents misunderstandings about requirements
- Ensures changes to requirements are understood and implemented earlier
- Helps the team focus on features that deliver the most value
- Addresses identified risks proactively

---

### 3.2.2 Review Process Activities

Based on the ISO/IEC 20246 standard, the review process includes:

1. **Planning** — Define scope, purpose, work product, quality characteristics, exit criteria, effort, and timeframes
2. **Review initiation** — Ensure all participants have access to the work product, understand their roles, and have everything needed
3. **Individual review** — Each reviewer assesses the work product independently, identifying anomalies, recommendations, and questions using techniques (e.g., checklist-based, scenario-based)
4. **Communication and analysis** — Anomalies are discussed and analyzed in a review meeting; decisions are made on status, ownership, and required actions
5. **Fixing and reporting** — Defect reports are created; once exit criteria are met, the work product is accepted and results are reported

---

### 3.2.3 Roles and Responsibilities in Reviews

| Role | Responsibility |
|---|---|
| **Manager** | Decides what is reviewed; provides resources (staff, time) |
| **Author** | Creates and fixes the work product under review |
| **Moderator** (facilitator) | Ensures effective running of meetings; handles mediation, time management, and a safe environment |
| **Scribe** (recorder) | Collates anomalies and records review information (decisions, new anomalies) |
| **Reviewer** | Performs the review; may be a project member, SME, or any stakeholder |
| **Review leader** | Takes overall responsibility; decides who, when, and where the review takes place |

---

### 3.2.4 Review Types

From least to most formal:

| Type | Key Characteristics |
|---|---|
| **Informal review** | No defined process; no formal documented output; main objective is detecting anomalies |
| **Walkthrough** | Led by the **author**; objectives include quality evaluation, educating reviewers, gaining consensus, generating ideas, detecting anomalies; individual review beforehand is not required |
| **Technical review** | Performed by technically qualified reviewers; led by a **moderator**; objectives include gaining consensus on technical problems, detecting anomalies, evaluating quality |
| **Inspection** | Most formal type; follows the complete generic process; main objective is maximum number of anomalies; **author cannot act as review leader or scribe**; metrics are collected |

---

### 3.2.5 Success Factors for Reviews

- Define clear objectives and measurable exit criteria (evaluation of participants should **never** be an objective)
- Choose the appropriate review type for the work product and context
- Perform reviews on small chunks to maintain concentration
- Provide feedback to stakeholders and authors so they can improve
- Provide adequate preparation time
- Support from management
- Make reviews part of the organization's culture
- Provide adequate training to all participants
- Facilitate meetings effectively

---

## Key Terms
- **Static testing**: Evaluating a work product without executing it
- **Dynamic testing**: Testing by executing the software
- **Static analysis**: Tool-assisted evaluation of a work product against a formal syntax
- **Review**: A form of static testing in which a work product is evaluated by one or more people
- **Inspection**: The most formal review type; follows a complete defined process; author cannot be review leader or scribe
- **Technical review**: A review led by a moderator with technically qualified reviewers
- **Walkthrough**: A review led by the author
- **Informal review**: A review with no defined process or formal output
- **Anomaly**: Any result that differs from what is expected; identified during a review
- **Moderator** (facilitator): Ensures the effective running of a review meeting

---

## Practice Questions
- What types of work products can be examined by static testing?
- What is the difference between static testing and dynamic testing?
- List three defect types that are easier to find through static testing than dynamic testing.
- What are the five activities in the review process?
- What are the six principal roles in a review and their responsibilities?
- What is the most formal review type, and what are its key characteristics?
- What is the main difference between a walkthrough and a technical review?
- List four success factors for reviews.
- Why should evaluation of participants never be an objective of a review?
