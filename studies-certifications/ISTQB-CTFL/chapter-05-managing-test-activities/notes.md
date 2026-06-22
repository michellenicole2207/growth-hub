# Chapter 5 - Managing Test Activities

> **The big idea:** Good testing doesn't just happen — it has to be planned, tracked, and wrapped up properly.
> This chapter is about the organizational and managerial side of testing: how to define strategy,
> estimate effort, measure progress, manage risk, and report results.

---

## Cognitive Levels in This Chapter

> K1 = Remember · K2 = Understand · K3 = Apply — see Chapter 1 for the full legend.

### Learning Objectives for Chapter 5

| LO | K | Topic |
|---|---|---|
| FL-5.1.1 | K2 | Exemplify the purpose and content of a test plan |
| FL-5.1.2 | K1 | Recognize how a tester adds value to iteration and release planning |
| FL-5.1.3 | K2 | Compare entry criteria and exit criteria |
| FL-5.1.4 | **K3** | Apply estimation techniques to calculate test effort for a defined scenario |
| FL-5.1.5 | **K3** | Apply test case prioritization for a given scenario |
| FL-5.1.6 | K2 | Recall the concepts of the test pyramid |
| FL-5.1.7 | K2 | Summarize the testing quadrants and their relationship to test levels and test types |
| FL-5.2.1 | K2 | Explain the purpose of test monitoring and control and the difference between them |
| FL-5.2.2 | K2 | Summarize the metrics used for testing |
| FL-5.2.3 | K2 | Summarize the purpose and content of test reports |
| FL-5.3.1 | K2 | Explain how risks influence the scope of testing |
| FL-5.3.2 | K1 | Recall risk identification and risk assessment |
| FL-5.4.1 | **K3** | Apply a defect report for a given scenario |
| FL-5.4.2 | K2 | Summarize the content and purpose of a defect report |

> **Exam tip:** Three K3 items here — estimation (FL-5.1.4), prioritization (FL-5.1.5), and defect reports (FL-5.4.1).
> The exam will give you a situation and ask you to produce something: an estimate, a prioritized list, or a defect report.
> FL-5.1.2 and FL-5.3.2 are K1 — pure recall.

---

## 5.1 Test Planning — 💡 Understand (K2)

A **test plan** documents the means and schedule for achieving test objectives. It's a living document — updated as the project evolves.

### What a test plan typically includes — 💡 Understand (K2)

| Section | Content |
|---|---|
| **Context** | Scope, test basis, constraints, test environment |
| **Objectives** | What testing aims to achieve |
| **Stakeholders** | Roles, responsibilities, communication |
| **Test approach** | Strategy, techniques, types of testing |
| **Schedule** | Milestones, effort, timelines |
| **Resources** | People, tools, environments |
| **Entry and exit criteria** | When to start and when to stop testing |
| **Risk and issues** | Known risks and mitigation strategies |
| **Metrics** | What will be measured to track progress |

---

## 5.2 Tester's Contribution to Iteration and Release Planning — 🧠 Remember (K1)

In Agile and iterative contexts, testers actively participate in:

- **Release planning** — estimating effort for features across multiple iterations; analyzing risks; defining the overall test approach
- **Iteration planning** — analyzing user stories in the backlog; assessing testability; identifying acceptance criteria; estimating test effort per story; participating in risk identification and assessment

> Testers bring a quality perspective that developers and product owners may not naturally have — challenging assumptions, spotting missing acceptance criteria, and flagging ambiguities early.

---

## 5.3 Entry Criteria and Exit Criteria — 💡 Understand (K2)

### Entry criteria — when to START testing — 💡 Understand (K2)

Conditions that must be met before a test activity begins. Testing without these satisfied wastes effort.

**Examples:**
- Testware is available (test cases, test scripts, test data)
- Test environment is ready and configured
- The test object has passed a smoke test

### Exit criteria — when to STOP testing — 💡 Understand (K2)

Conditions that determine when a test activity is sufficiently complete.

**Examples:**
- Planned tests have been executed
- Coverage level achieved (statements, requirements)
- Defect density is below the defined threshold
- Time or budget has been exhausted (pragmatic exit)

> In Agile, entry/exit criteria are often called **Definition of Ready (DoR)** and **Definition of Done (DoD)**.

---

## 5.4 Estimation Techniques — ⚙️ Apply (K3)

Estimating how much testing effort is needed is notoriously difficult. The CTFL v4.0.1 syllabus names four specific estimation techniques:

### Estimation Techniques — ⚙️ Apply (K3)

| Technique | How it works |
|---|---|
| **Estimation based on ratios** | Uses metrics from previous similar projects (e.g., ratio of test effort to development effort). Applied to current project data to estimate test effort. |
| **Extrapolation** | Uses measurements collected early in the current project to estimate remaining effort. The more data collected, the more accurate the estimate. |
| **Wideband Delphi** | Expert-based group technique. Experts independently estimate, share results anonymously, discuss differences, and repeat until consensus is reached. Planning Poker is a variant of Wideband Delphi adapted for Agile. |
| **Three-point estimation** | Produces three estimates: most optimistic (a), most likely (m), most pessimistic (b). Final estimate = (a + 4m + b) / 6. Reduces bias and accounts for uncertainty. |

> **Exam note:** Planning Poker is a **variant of Wideband Delphi**, not a separate technique. Both are named in the syllabus.

---

## 5.5 Test Case Prioritization — ⚙️ Apply (K3)

Not all tests are equally important. Prioritization determines the order in which tests are run.

### Strategies — ⚙️ Apply (K3)

| Strategy | Prioritize by |
|---|---|
| **Risk-based** | Highest risk areas first — most impact if they fail |
| **Coverage-based** | Tests that cover more requirements or code first |
| **Requirements-based** | Tests linked to the most critical or important requirements |
| **Activity-based** | Dependency-driven order (some tests must run before others) *(supporting concept — not defined in the CTFL 4.0 syllabus)* |

> In practice, risk-based prioritization is the most common and the most effective — it maximizes defect detection in the shortest time when time is limited.

---

## 5.6 The Test Pyramid — 💡 Understand (K2)

The **test pyramid** is a model that groups tests by granularity and recommends how to distribute them:

```
        /\
       /  \   UI / End-to-End (few, slow, expensive)
      /----\
     /      \  Integration (some)
    /--------\
   /          \  Unit (many, fast, cheap)
  /____________\
```

- **Bottom (unit)**: many small, fast, isolated tests — cheap to write and maintain
- **Middle (integration)**: tests of interactions between components
- **Top (UI/E2E)**: few, slow, brittle tests — use only where needed

> **Important:** The test pyramid is a model, not a fixed rule. **The number and naming of the layers may differ.** Multiple variants exist in industry (e.g., 3-layer, 4-layer, with or without separate API/service layer). What the model conveys is that: lower layers (closer to code) should have more tests, be faster, and be cheaper; higher layers (closer to UI/user) should have fewer tests, be slower, and be more expensive. The general principle of test distribution matters more than the specific layer names.

> The pyramid implies: **automate at the lowest level possible**. The more you push automation up to the UI level, the slower and more fragile your test suite becomes.

---

## 5.7 Testing Quadrants — 💡 Understand (K2)

The **testing quadrants** (Brian Marick) categorize test types by two axes:

- **Business-facing vs. Technology-facing**
- **Supporting the team (guiding development) vs. Critiquing the product (finding problems)**

| | Supporting the team | Critiquing the product |
|---|---|---|
| **Technology-facing** | **Q1**: Component tests, component integration tests | **Q4**: Performance tests, load tests, stress tests, security tests, smoke tests (**note: usability tests go in Q3, not Q4**) |
| **Business-facing** | **Q2**: Functional tests, story tests, user story tests, prototypes, simulations, API testing | **Q3**: Exploratory testing, usability testing, user acceptance testing |

**Quadrant overview:**
- **Q1** (technology-facing, supporting the team): component tests, component integration tests
- **Q2** (business-facing, supporting the team): functional tests, story tests, user story tests, prototypes, simulations, API testing
- **Q3** (business-facing, critiquing the product): exploratory testing, usability testing, user acceptance testing
- **Q4** (technology-facing, critiquing the product): performance tests, load tests, stress tests, security tests, smoke tests — **note: usability tests are business-facing and belong in Q3, not Q4**

> The quadrants are a **communication tool** — they help teams talk about what kinds of testing are needed and who should do them. They are not prescriptive.

---

## 5.8 Risk and Testing — 💡 Understand (K2)

Risk is central to test planning. It drives prioritization, coverage decisions, and the depth of testing applied to each area.

### Key concepts — 🧠 Remember (K1)

- **Risk**: a **potential event, hazard, threat, or situation** whose occurrence causes an adverse effect. Risk level = likelihood × impact.
- **Risk level**: a combination of **likelihood** (probability) and **impact** (consequence)
- **Product risk**: risk that something in the system will fail — drives testing scope
- **Project risk**: risk to the project itself (schedule, budget, team) — managed through project management

### Project Risk Categories — 💡 Understand (K2)

The syllabus organizes project risks into four named categories:

- **Organizational risks:** funding cuts, conflicting priorities, changes in organizational structure
- **People risks:** insufficient skills, staff conflicts, team communication issues
- **Technical risks:** technology failures, tool issues, environment problems
- **Supplier risks:** third-party delivery failures, supplier going out of business, contract issues

### Risk-Based Testing — 💡 Understand (K2)

Uses risk as the primary guide for:
- **What** to test (high-risk areas get more focus)
- **How much** to test (riskier areas get more test cases)
- **When** to test (high-risk items are tested earlier)

**Two stages:**
1. **Risk identification**: brainstorm with stakeholders — what could go wrong?
2. **Risk assessment**: evaluate likelihood and impact; prioritize accordingly

> If a high-risk area receives adequate testing and no defects are found, this provides evidence of quality — not just the absence of failures.

### 5.2.4 Product Risk Control — 💡 Understand (K2)

Product risk control consists of two activities:

**Risk mitigation** — taking actions to reduce the likelihood or impact of identified risks:
- Testing the high-risk areas more thoroughly
- Using specific test techniques for particular risk types
- Applying multiple independent testing activities to high-risk items
- Adjusting test design and execution based on risk assessment

**Risk monitoring** — tracking identified risks throughout the project:
- Checking whether mitigation actions have reduced risk levels
- Identifying new risks that emerge during the project
- Updating the risk register and adjusting test activities accordingly

---

## 5.9 Test Monitoring, Test Control, and Test Completion — 💡 Understand (K2)

### Test Monitoring — 💡 Understand (K2)

Ongoing activity of checking test progress against the plan.

**Common test metrics collected:**

| Metric | What it tells you |
|---|---|
| % of test cases executed | How much of the plan is done |
| % passed / failed / blocked | Quality signal |
| Defect detection rate | How many defects are being found over time |
| Defect density by module | Where defects cluster |
| Requirements / code coverage | How thoroughly the system is exercised |
| Resource / budget consumption | Is the project on track? |

### Test Control — 💡 Understand (K2)

Taking corrective actions when monitoring reveals deviations from the plan.

**Examples of control actions:**
- Reprioritize tests when a critical defect is found
- Adjust schedule or scope if risks materialize
- Change the test approach (e.g., add exploratory sessions)
- Add resources if the team is falling behind

> Monitoring without control is just observation. Control is what makes monitoring useful.

### Test Progress Reports — 💡 Understand (K2)

Communicate current status to stakeholders. Typically include:
- Test period covered
- Progress against the plan
- Impediments and blockers
- Planned activities for the next period

### Test Completion Reports — 💡 Understand (K2)

Produced at the end of a test phase, iteration, or project. Summarize:
- What was tested, how, and with what results
- Deviations from the plan
- Defects found and their status
- Testware to archive or hand off
- Lessons learned

### 5.3.3 Communicating the Status of Testing — 💡 Understand (K2)

The goal of communicating test status is to ensure stakeholders have the information they need to make decisions (about release, risk acceptance, etc.).

**Communication options:**

| Option | When to use |
|---|---|
| **Verbal communication** | Informal, immediate updates; useful for daily collaboration |
| **Dashboards** | Real-time visual summaries of test progress, coverage, and defect status; suitable for distributed teams and executives |
| **Electronic communication** | Emails or automated messaging for specific events (e.g., test run completed, critical defect found) |
| **Test progress reports** | Formal periodic reports during test execution; tracks progress against plan |
| **Test completion reports** | Produced at major milestones (end of a test level, end of iteration, release); includes summary of what was tested, results, remaining risks |

> **Exam tip (K2):** A question may describe a stakeholder's information need and ask which communication channel is most appropriate. Match the formality and frequency of the channel to the stakeholder's needs.

---

## 5.4 Configuration Management — 💡 Understand (K2)

Configuration management (CM) provides a discipline for identifying, controlling, and tracking work products and their versions throughout the project lifecycle.

**Key concepts:**
- **Configuration item:** Any work product placed under configuration management (e.g., test cases, test scripts, test data, test environment specs, test plans)
- **Baseline:** A formally approved version of a configuration item, from which changes are controlled. A baseline represents a known, stable state.
- **Change control:** Any modification to a baselined item must go through a formal change control process, including approval and impact assessment.

**CM and testing:** CM ensures that testers are working with the correct versions of the test basis and testware. It enables reproducibility of test results and supports impact analysis when changes are made.

> In practice: your test cases should reference specific software versions. "Tested with v2.3.1" is meaningful only if CM ensures that v2.3.1 can be reproduced.

---

## 5.11 Defect Management — ⚙️ Apply (K3)

The defect management process tracks defects from discovery to closure.

### Defect lifecycle (typical) — 💡 Understand (K2)

> **Note:** The CTFL 4.0 syllabus does not prescribe specific lifecycle states. The diagram below is a common industry pattern for illustration. For the exam, focus on the **defect report fields** (FL-5.4.1/5.4.2), not the lifecycle state names.

```
New → Assigned → Open → Fixed → Retest → Closed
                              ↘ Rejected / Deferred
```

### A good defect report includes — ⚙️ Apply (K3)

| Field | Purpose |
|---|---|
| **Unique ID** | Tracking |
| **Summary** | Short description of the failure |
| **Date and author** | Who found it and when |
| **Environment** | OS, browser, version, configuration |
| **Steps to reproduce** | Exact sequence to reproduce the failure |
| **Expected result** | What should have happened |
| **Actual result** | What actually happened |
| **Severity** | Impact on the system (Critical, Major, Minor, Trivial) |
| **Priority** | How urgently it needs to be fixed |
| **Status** | Current state in the lifecycle |
| **Attachments** | Logs, screenshots, videos |
| **Context of the defect** | Test phase, environment, test technique in use when the defect was found |
| **References** | Links to the test case that found the defect, related requirements, or related defects |

> **Severity vs. Priority:** A typo in a login button label is low severity but possibly high priority (it's the first thing every user sees). A crash in a rarely-used feature might be high severity but low priority.

---

## Key Terms Cheat Sheet — 🧠 Remember (K1)

| Term | Definition |
|---|---|
| **Test plan** | Document describing the scope, approach, schedule, and resources for testing |
| **Entry criteria** | Conditions that must be met before a test activity begins |
| **Exit criteria** | Conditions that determine when a test activity is complete |
| **Risk** | A potential event, hazard, threat, or situation whose occurrence causes an adverse effect |
| **Product risk** | Risk that a system component fails to meet expected behavior |
| **Project risk** | Risk to the project schedule, budget, or resources |
| **Risk-based testing** | Using risk as the guide for prioritizing what, how much, and when to test |
| **Test pyramid** | Model recommending more unit tests than integration or UI tests; number and naming of layers may vary |
| **Testing quadrants** | Framework categorizing tests by audience (business vs. technology) and purpose (guiding vs. critiquing) |
| **Test monitoring** | Checking test progress against the plan |
| **Test control** | Taking corrective action when deviations are found |
| **Defect report** | A document capturing a failure and all information needed to reproduce, track, and resolve it |
| **Severity** | The impact of a defect on the system |
| **Priority** | The urgency with which a defect should be fixed |
| **Configuration management** | Tracking versions of testware to ensure consistency and reproducibility |
| **Wideband Delphi** | Expert-based estimation technique using anonymous rounds of estimation and discussion until consensus |
| **Three-point estimation** | Estimation using optimistic, most likely, and pessimistic values: (a + 4m + b) / 6 |
| **Risk mitigation** | Actions taken to reduce the likelihood or impact of identified risks |
| **Risk monitoring** | Tracking risks throughout the project and updating the risk register accordingly |

---

## Practice Questions

- What is the purpose of a test plan and what does it typically include?
- What is the difference between entry criteria and exit criteria? Give one example of each.
- What are the four estimation techniques named in CTFL v4.0.1? How does three-point estimation work?
- What is the relationship between Planning Poker and Wideband Delphi?
- What is risk-based test prioritization and why is it the most common strategy?
- What is the test pyramid and what does it recommend about automation? Why can the number of layers vary?
- What are the four testing quadrants and what axes define them?
- Which quadrant does usability testing belong to, and why does it matter?
- What is the difference between product risk and project risk?
- What are the four categories of project risk named in the syllabus?
- What are the two stages of risk-based testing (identification and assessment)?
- What are the two activities of product risk control?
- What is the difference between test monitoring and test control?
- What should a test completion report include?
- What are the five communication options for reporting test status? When would you use a dashboard vs. a verbal update?
- What is the difference between severity and priority in defect management?
- Why does configuration management matter for testing? What is a baseline?
- What are the two fields added to defect reports beyond the basic list (context and references)?
- How do entry/exit criteria relate to Definition of Ready and Definition of Done in Agile?
- What metrics would you collect to monitor test progress?
