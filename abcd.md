# NPCBL Exam — QA Written Notes
**Engineer (Quality) [Grade-8] | Software QA Engineer**
50 Questions · Quick Notes Format · BUET Pattern

---

## CATEGORY 1 — QA Fundamentals (Q1–Q5)

### Q1. SQA vs Software Testing
| | SQA | Testing |
|---|---|---|
| Focus | Process | Product |
| Goal | Prevent defects | Detect defects |
| Phase | Entire SDLC | After coding |
| Example | Code reviews, standards | Running test cases |

> **Nuclear context:** SQA ensures compliance with IEC 61513; Testing verifies actual behavior.

---

### Q2. Bug Life Cycle
```
New → Assigned → Open → Fixed → Retest → Closed
                                       ↘ Reopened → Assigned (loop)
                         ↘ Rejected / Deferred / Duplicate
```
**States:** New, Assigned, Open, Fixed, Retest, Closed, Reopened, Deferred, Rejected, Duplicate

> 💡 **Tip:** Draw as a flowchart in exam.

---

### Q3. Test Case Template
```
Test Case ID:    TC_REG_001
Title:           Verify successful user registration
Module:          User Registration
Priority:        High | Severity: Critical
Pre-conditions:  Page accessible, email not registered
Steps:           1. Navigate → 2. Enter data → 3. Click Register
Expected Result: Success message + confirmation email
Status:          Pass / Fail
```

> 💡 **Must include:** ID, Pre-condition, Steps, Expected Result, Status

---

### Q4. Defect Density
**Formula:** `Defect Density = Defects ÷ Size (FP or KLOC)`

**Example:** 60 defects ÷ 1000 FP = **0.06 defects/FP**
- Industry standard: ≤ 0.05
- 0.06 > 0.05 → **NOT acceptable** → needs more testing

> 💡 **Always:** State formula → Calculate → Compare → Recommend action

---

### Q5. Requirements Traceability Matrix (RTM)
**Purpose:** Map requirements → test cases → ensure no gaps

| Req ID | Requirement | Test Cases | Status |
|--------|-------------|------------|--------|
| REQ-001 | Login with valid credentials | TC-001, TC-002 | Pass |
| REQ-004 | Account lockout after 5 tries | TC-005, TC-006 | **Fail** |
| REQ-006 | Session timeout | TC-009 | Not Tested |

---

## CATEGORY 2 — Testing Techniques (Q6–Q10)

### Q6. BVA + EP

**Equivalence Partitioning (EP):** Group inputs into partitions; test one value per group.

**Boundary Value Analysis (BVA):** Test at the edges of partitions.

**Example (Age field: valid 18–60):**
- EP: test 10 (invalid), 30 (valid), 70 (invalid)
- BVA: test **17, 18, 19** and **59, 60, 61**

> 💡 EP = reduces test count; BVA = targets high-risk edges. Use both together.

---

### Q7. White-box Testing
Tests **internal code structure**. Tester must know source code.

| Coverage Type | What it tests |
|---|---|
| Statement | Every line executed at least once |
| Branch | Every if/else path taken |
| Path | Every unique path through code |

**Example (100% Statement Coverage):**
```
TC-1: age=25 → "Adult"  (covers lines 1, 2)
TC-2: age=15 → "Minor"  (covers lines 1, 3, 4)
```

---

### Q8. Decision Table Testing
Tests **all combinations** of conditions and expected outcomes.

| | R1 | R2 | R3 | R4 |
|---|---|---|---|---|
| Valid Username? | Y | Y | N | N |
| Valid Password? | Y | N | Y | N |
| **Login Success?** | **Y** | N | N | N |
| **Wrong Password?** | N | **Y** | N | N |
| **User Not Found?** | N | N | **Y** | **Y** |

---

### Q9. State Transition Testing
Tests behavior as system **moves between states**.

**ATM Example:**
```
S1 (Idle) → [Insert card] → S2 (Card In)
S2 → [Correct PIN] → S3 (Verified)
S2 → [Wrong PIN x3] → S4 (Locked)
S3 → [Eject] → S1 (Idle)
```

> 💡 Very relevant for nuclear control system mode testing.

---

### Q10. Exploratory Testing
Simultaneous **learning + design + execution** without pre-written scripts.

| Advantages | Disadvantages |
|---|---|
| Fast, no upfront prep | Hard to document/reproduce |
| Finds unexpected bugs | Coverage hard to measure |
| Tests real user scenarios | Depends on tester skill |

> ⚠️ **NPCBL:** NOT suitable as primary method for nuclear software — must use formal scripted testing per IEC 61513.

---

## CATEGORY 3 — Test Management (Q11–Q15)

### Q11. Test Plan Components (IEEE 829)
1. Test Plan ID & Title
2. Introduction / Objectives
3. **Scope** — what is/isn't tested
4. Test Strategy & Approach
5. Test Environment
6. Resource Plan (roles)
7. Schedule & Timeline
8. Risk & Mitigation
9. Test Deliverables
10. **Entry Criteria**
11. **Exit Criteria**
12. Defect Management

---

### Q12. Entry & Exit Criteria

**Entry Criteria (before testing STARTS):**
- SRS approved and baselined
- Test environment set up
- Test cases reviewed & signed off
- Build smoke-tested
- Test data available

**Exit Criteria (when testing STOPS):**
- Pass rate ≥ 95%
- No open Critical/High defects
- Defect density ≤ 0.05/FP
- All test cases executed
- Test Summary Report approved

---

### Q13. Quality Metrics (6 Key Metrics)

| Metric | Formula | Target |
|---|---|---|
| Defect Density | Defects ÷ FP | ≤ 0.05 |
| Test Coverage | (Executed ÷ Total) × 100 | 100% |
| DDE | (Testing defects ÷ Total) × 100 | High |
| Test Pass Rate | (Passed ÷ Executed) × 100 | ≥ 95% |
| MTTD | Avg time to detect bug | Low |
| DRE | (Removed before release ÷ Total) × 100 | ≥ 95% |

---

### Q14. Risk-Based Testing
**Formula:** `Risk = Probability of Failure × Impact of Failure`

**NPCBL Priority:**
- 🔴 **High Risk (test first):** Reactor shutdown triggers, emergency cooling, radiation alarms
- 🟡 **Medium:** Access control, status dashboards
- 🟢 **Low:** UI layout, report formatting

---

### Q15. Test Strategy vs Test Plan

| | Test Strategy | Test Plan |
|---|---|---|
| Level | Organization-wide | Project-specific |
| Created by | Test Manager/QA Lead | Per project |
| Changes | Rarely | Per release |
| Content | How we test in general | How we test THIS project |
| Standard | — | IEEE 829 |

---

## CATEGORY 4 — Automation & CI/CD (Q16–Q18)

### Q16. Selenium & Automation vs Manual

**Selenium components:** WebDriver · Grid · IDE

**Use Automation when:** Regression · Load · Data-driven · CI/CD · Repetitive tasks

**Use Manual when:** Exploratory · Usability/UX · One-time tests · Low ROI automation

---

### Q17. API Testing

**Flow:** HTTP Request (GET/POST/PUT/DELETE) → Server → JSON/XML Response

| | API Testing | UI Testing |
|---|---|---|
| Speed | Very fast | Slower |
| Stability | Stable | Flaky |
| Tools | Postman, REST Assured | Selenium, Cypress |

**Validate:** Status code · Response time < 2s · JSON schema · Auth headers

**Status codes:** `200 OK` `201 Created` `400 Bad Request` `401 Unauthorized` `404 Not Found` `500 Server Error`

---

### Q18. CI/CD Pipeline
```
Commit → Build → Unit Tests → Integration Tests → Code Quality
       → Deploy to Staging → Regression + API Tests → Deploy to Production
```
**Tools:** Jenkins · GitHub Actions · GitLab CI · Docker · Kubernetes

---

## CATEGORY 5 — SDLC & Agile (Q19–Q20)

### Q19. V-Model
```
Requirements       ←→   User Acceptance Testing (UAT)
System Design      ←→   System Testing
High-Level Design  ←→   Integration Testing
Low-Level Design   ←→   Unit Testing
          ↘             ↙
              [CODING]
```
**Why for Nuclear:** Formal V&V per phase · Documentation trail · IEC 61513/IAEA mandate · Exit criteria enforced

---

### Q20. Scrum Framework

**3 Roles:** Product Owner · Scrum Master · Development Team

**3 Artifacts:** Product Backlog · Sprint Backlog · Increment

**5 Ceremonies:**
1. Sprint Planning
2. Daily Stand-up (15 min)
3. Sprint Review
4. Sprint Retrospective
5. Backlog Refinement

> 💡 **Memory:** 3-3-5 | Sprint = 1–4 weeks (typically 2)

---

## CATEGORY 6 — Software Engineering (Q21–Q23)

### Q21. SOLID Principles

| Letter | Principle | One-line Rule |
|---|---|---|
| **S** | Single Responsibility | One class = one reason to change |
| **O** | Open/Closed | Open for extension, closed for modification |
| **L** | Liskov Substitution | Subclass can replace parent without breaking |
| **I** | Interface Segregation | Don't force unused method implementations |
| **D** | Dependency Inversion | Depend on abstractions, not concretions |

---

### Q22. Functional vs Non-Functional Requirements

**Functional (WHAT):** Display reactor temp every 5s · Trigger shutdown at 300°C · Login with credentials

**Non-Functional (HOW WELL):**
- Performance: < 100ms for safety alerts
- Availability: 99.999% uptime (five nines)
- Security: AES-256 encryption
- Reliability: MTBF ≥ 50,000 hours

---

### Q23. Git Workflow
```bash
git init / git clone <url>     # Start
git status                     # Check changes
git add . && git commit -m ""  # Stage & commit
git push origin main           # Push to remote
git pull                       # Get latest
git branch <name>              # Create branch
git checkout <name>            # Switch branch
git merge <name>               # Merge branch
git log                        # View history
```

---

## CATEGORY 7 — Database & SQL (Q24–Q27)

### Q24. Normalization

| Form | Rule | Fix |
|---|---|---|
| **1NF** | Atomic values only | Split multi-value cells into rows |
| **2NF** | No partial dependency | Move partial-dependent cols to own table |
| **3NF** | No transitive dependency | Move transitively-dependent cols to own table |

---

### Q25. Key SQL Queries
```sql
-- Filter + condition
SELECT * FROM Employee WHERE Dept='QA' AND Salary > 50000;

-- Group & count
SELECT Dept, COUNT(*) AS Total FROM Employee GROUP BY Dept;

-- Having (filter on aggregate)
SELECT Dept, AVG(Salary) FROM Employee GROUP BY Dept HAVING AVG(Salary) > 40000;

-- 2nd highest salary
SELECT MAX(Salary) FROM Employee WHERE Salary < (SELECT MAX(Salary) FROM Employee);

-- Update with calculation
UPDATE Employee SET Salary = Salary * 1.10 WHERE Dept = 'QA';
```

---

### Q26. ACID Properties

| Property | Meaning | Nuclear Example |
|---|---|---|
| **Atomicity** | All or nothing | Reactor alert log: fully written or rolled back |
| **Consistency** | Valid state always | Balance never goes negative |
| **Isolation** | No interference | Two operators updating settings simultaneously |
| **Durability** | Persists after crash | Alert record survives system reboot |

---

### Q27. SQL vs NoSQL

| | SQL | NoSQL |
|---|---|---|
| Schema | Fixed | Flexible |
| Scalability | Vertical | Horizontal |
| Transactions | Full ACID | Eventually consistent |
| Examples | MySQL, PostgreSQL | MongoDB, Redis, Cassandra |
| Best for | Complex queries | High-volume fast writes |

**NPCBL:** SQL for audit trails & personnel records · NoSQL for sensor data streams

---

## CATEGORY 8 — Networking & REST API (Q28–Q30)

### Q28. OSI 7 Layers
> **Mnemonic:** *Please Do Not Throw Sausage Pizza Away*

| Layer | Name | Examples |
|---|---|---|
| 7 | Application | HTTP, FTP, SMTP, DNS |
| 6 | Presentation | SSL/TLS, JPEG |
| 5 | Session | NetBIOS |
| 4 | Transport | TCP, UDP |
| 3 | Network | IP, routers |
| 2 | Data Link | Ethernet, switches |
| 1 | Physical | Cables, hubs |

---

### Q29. TCP vs UDP

| | TCP | UDP |
|---|---|---|
| Connection | 3-way handshake | Connectionless |
| Reliability | Guaranteed delivery | No guarantee |
| Speed | Slower | Faster |
| Use | Web, files, email | Video, VoIP, gaming |

**NPCBL:** Safety commands → TCP | Sensor streaming → UDP

---

### Q30. REST API

**HTTP Methods:** `GET` Read · `POST` Create · `PUT` Update · `PATCH` Partial update · `DELETE` Remove

**Status Codes:**
- `2xx` Success: 200 OK, 201 Created
- `4xx` Client: 400 Bad Request, 401 Unauthorized, 404 Not Found
- `5xx` Server: 500 Internal Server Error

---

## CATEGORY 9 — Quality Standards (Q31–Q35)

### Q31. ISO 9001:2015
**7 Principles:** Customer Focus · Leadership · People Engagement · Process Approach · Improvement · Evidence-based Decisions · Relationship Management

**Key Clauses:** Clause 8 = Operations · Clause 9 = Performance Evaluation · Clause 10 = Improvement (NCRs)

---

### Q32. IEC 61513 ⚛️
**Scope:** Entire I&C lifecycle in nuclear plants (design → decommissioning)

**Key Requirements:**
- Safety classification: Category A / B / C
- Mandatory V&V at each lifecycle phase
- Formal documentation for all activities
- Defense-in-Depth principle
- Strict change management — no undocumented changes
- Aligns with IEC 60880 (software)

> 💡 Non-compliance = plant shutdown + IAEA violation

---

### Q33. CMMI — 5 Maturity Levels

| Level | Name | Description |
|---|---|---|
| 1 | Initial | Chaotic, ad-hoc, hero-dependent |
| 2 | Managed | Basic project management |
| 3 | Defined | Org-wide standard processes |
| 4 | Quantitatively Managed | Statistical control |
| 5 | Optimizing | Continuous improvement |

> **NPCBL target:** Level 3 or higher

---

### Q34. ISO/IEC 25010 — 8 Quality Characteristics
1. **Functional Suitability** — does it do what it should?
2. **Performance Efficiency** — speed, resources, capacity
3. **Compatibility** — works with other systems
4. **Usability** — ease of use
5. **Reliability** — works correctly over time
6. **Security** — protects data
7. **Maintainability** — easy to modify
8. **Portability** — transferable to other environments

---

### Q35. Non-Conformance Report (NCR)

**Process:** Detection → Documentation → Disposition → Corrective Action → Verification → Closure

**Sample NCR:**
```
NCR-2026-QA-007 | Date: 04 Jun 2026
Project: NPCBL Control System v2.1
Issue: Alarm audio alert NOT triggered when temp > 280°C
Requirement: REQ-ALARM-003 — alert within 500ms
Severity: CRITICAL
Disposition: Rework
Action: Fix trigger logic in SafetyMonitor.java
Close Date: 10 Jun 2026
```

---

## CATEGORY 10 — Nuclear Context (Q36–Q37)

### Q36. Defense in Depth (DiD) ⚛️

**5 Physical Levels:**
1. Prevention of abnormal operation
2. Control of abnormal operation
3. Control of accidents (emergency cooling)
4. Mitigation of severe accidents (containment)
5. Off-site emergency response

**Software Application:**
- V&V per IEC 61513/60880
- Diversity: independent software/hardware backups
- Isolation: safety system ≠ operational network
- No single point of failure
- Manual override always available

---

### Q37. Rooppur Nuclear Power Plant ⚛️

| Field | Detail |
|---|---|
| Location | Rooppur, Ishwardi, Pabna, Bangladesh |
| Developer | ROSATOM (Russia) |
| Owner | NPCBL |
| Regulator | BAERA |
| Reactor | VVER-1200 (pressurized water reactor) |
| Units | 2 reactors |
| Capacity | 1,200 MW each = **2,400 MW total** |
| Fuel | Enriched uranium (Russia-supplied) |
| Cooling | Padma (Ganges) river |
| Design life | 60 years |

**VVER-1200 Safety:** Passive cooling (gravity) · Double containment · Core catcher

**Significance:** ~10% of Bangladesh's electricity · Largest infrastructure project in history

---

## CATEGORY 11 — MS Office (Q38–Q40)

### Q38. Excel Formulas for Test Data
```excel
=COUNTIF(B2:B501, "Pass")                    → Count passed
=COUNTIF(B2:B501, "Fail")                    → Count failed
=COUNTIF(B2:B501,"Pass") / 500 * 100         → Pass rate %
=AVERAGE(C2:C501)                            → Avg execution time
=AVERAGEIF(B2:B501, "Fail", C2:C501)         → Avg time for failures
=VLOOKUP("TC-045", A2:C501, 2, FALSE)        → Find test status
=IF(B2="Pass", "Green", "Red")               → Classify result
```
**Conditional Formatting:** Home → Conditional Formatting → Highlight Cells → Equal To "Fail" → Red Fill

---

### Q39. Pivot Table for Defect Analysis
**Create:** Insert → PivotTable → New Worksheet → Drag fields

**Useful analyses:**
- Defects per Module → Rows: Module | Values: Count of DefectID
- By Severity & Status → Rows: Severity | Columns: Status | Values: Count
- Monthly trend → Rows: Month | Values: Count

---

### Q40. MS Word & PowerPoint Features

**Word (Top 10):** Styles · TOC · Track Changes (Ctrl+Shift+E) · Comments · Mail Merge · Find & Replace (Ctrl+H) · Macros · Section Breaks · Bibliography · Watermark

**PowerPoint (Top 5):** Slide Master · Transitions & Animations · Presenter View · Embed Excel Charts · Export as PDF/Video

**Key Shortcuts:** `Ctrl+S` Save · `Ctrl+Z` Undo · `Ctrl+B` Bold · `Ctrl+H` Find & Replace · `F5` Start Slideshow

---

## CATEGORY 12 — Math Problems (Q41–Q44)

### Q41. Defect Calculation
```
Total = 8 engineers × 5 defects/day × 10 days = 400 defects
Duplicates (15%) = 60  →  Unique defects = 340
Defect Density = 340 ÷ 500 FP = 0.68 (very high!)
Fix cost = 340 × Tk.500 = Tk.1,70,000
```

---

### Q42. Cumulative Pass Rate
```
Sprint 1: 200 tests, 82% pass → 164 passed, 36 failed
Sprint 2: 50 new tests → 40 passed, 10 failed

Total: 250 tests | 204 passed | 46 failed
Cumulative pass rate = (204 ÷ 250) × 100 = 81.6%
```

---

### Q43. Reliability Math
```
Reliability = 99.9%  →  Failure % = 0.1%
Acceptable failure = 0.1% × 1000 hrs = 1 hour
MTBF = 1000 ÷ 1 = 1000 hours

For 99.999% (five nines):
Failure = 0.001% × 1000 = 0.01 hrs = 36 seconds
MTBF = 100,000 hours ≈ 11.4 years
```

---

### Q44. Effort Estimation (COCOMO)
```
Effort = 2.5 × (KLOC)^1.05
       = 2.5 × (10)^1.05
       = 2.5 × 11.22
       = ~28 person-months

People needed (6 months) = 28 ÷ 6 = 4.67 ≈ 5 people
Verify: 5 × 6 = 30 person-months ≥ 28 ✓
```

---

## CATEGORY 13 — Advanced QA (Q45–Q49)

### Q45. Performance Testing Types

| Type | What | Example |
|---|---|---|
| **Load** | Expected load | 500 concurrent users |
| **Stress** | Beyond limit | Push until crash |
| **Endurance/Soak** | Sustained over time | 200 users for 72 hours |
| **Spike** | Sudden surge | 100 → 2000 users instantly |

**Tools:** JMeter · Gatling · LoadRunner · k6

---

### Q46. Security Testing — OWASP Top 10 (2021)
1. Broken Access Control
2. Cryptographic Failures
3. **Injection** (SQL, Command, LDAP)
4. Insecure Design
5. Security Misconfiguration
6. Vulnerable & Outdated Components
7. Identification & Authentication Failures
8. Software/Data Integrity Failures
9. Security Logging Failures
10. Server-Side Request Forgery (SSRF)

> **NPCBL:** IEC 62645 covers nuclear cybersecurity requirements.

---

### Q47. Shift-Left Testing
**Concept:** Move testing earlier in the SDLC timeline.

```
Traditional: Requirements → Design → Code → [TEST] → Deploy  ❌
Shift-Left:  [TEST at every phase from the start]            ✅
```

**Benefits:** Earlier = cheaper (100× cheaper in requirements vs production) · Faster feedback · Better requirements · Enables CI/CD

---

### Q48. TDD — Red-Green-Refactor
```
🔴 RED    → Write failing test (feature doesn't exist yet)
🟢 GREEN  → Write minimum code to pass the test
🔵 REFACTOR → Clean up code; all tests still pass
```

**Benefits:** High unit test coverage · Confidence to refactor · Simpler, modular code

---

### Q49. Root Cause Analysis — 5 Whys
**Problem:** Dashboard crashed with 50+ users

| Why? | Answer |
|---|---|
| Why did it crash? | DB connection pool exhausted |
| Why exhausted? | Each session opened 3 connections |
| Why 3 connections? | New library used without closing connections |
| Why not closed? | No code review before integration |
| **Why no code review?** | **Code review NOT enforced in sprint checklist** ← ROOT CAUSE |

**Fix:** Enforce mandatory code review + add SonarQube to CI pipeline

---

## CATEGORY 14 — Comprehensive Strategy (Q50)

### Q50. Complete QA Strategy for NPCBL Software

```
Phase 1: Requirements
  → Review SRS (shift-left) · Build RTM skeleton · Classify by safety (IEC 61513 A/B/C)

Phase 2: Test Planning
  → Test Plan (IEEE 829) · Entry/Exit criteria · Risk assessment · Automation plan

Phase 3: Test Design
  → Test cases (Functional + Non-Functional) · BVA+EP · Decision Tables
  → State Transition · JMeter scripts · Update RTM

Phase 4: Environment Setup
  → Configure test server · Prepare test data · Setup JIRA + Selenium + JMeter · CI/CD

Phase 5: Test Execution
  → Smoke test → Functional (Critical→High→Medium→Low)
  → Log defects in JIRA → Regression after each fix
  → Performance tests (Load, Stress, Endurance)
  → Security tests (OWASP Top 10)

Phase 6: Defect Management
  → Track all NCRs (ISO 9001) · Daily triage · RCA on Critical/High bugs
  → No Critical/High open before sign-off

Phase 7: Test Closure
  → Verify Exit Criteria · Test Summary Report
  → Document: defect density, pass rate, coverage
  → Archive artifacts per IEC 61513 · Present metrics to stakeholders
```

**Standards:** ISO 9001 · IEC 61513 · IEC 60880 · IEEE 829 · IAEA guides

---

## Quick Reference Cheat Sheet

### Key Formulas
| Metric | Formula |
|---|---|
| Defect Density | Defects ÷ FP (target ≤ 0.05) |
| Pass Rate | (Passed ÷ Executed) × 100 (target ≥ 95%) |
| DRE | (Defects removed before release ÷ Total) × 100 |
| MTBF | Total time ÷ Number of failures |
| Reliability | (1 − failure rate) × 100% |
| Risk | Probability × Impact |

### Key Standards
| Standard | Covers |
|---|---|
| **IEC 61513** | Nuclear I&C systems lifecycle |
| **IEC 60880** | Nuclear software quality |
| **IEC 62645** | Nuclear cybersecurity |
| **ISO 9001:2015** | Quality Management System |
| **ISO/IEC 25010** | Software product quality model |
| **IEEE 829** | Test documentation |
| **CMMI** | Process maturity (Levels 1–5) |

### Testing Types Summary
| Type | What it finds |
|---|---|
| Unit | Code-level bugs |
| Integration | Interface/interaction bugs |
| System | End-to-end behavior |
| UAT | Business requirement gaps |
| Regression | Bugs introduced by new changes |
| Performance | Speed/load issues |
| Security | Vulnerabilities |
| Exploratory | Unknown/unexpected issues |

---

*Best wishes for your NPCBL exam — aim for 100/100! 🎯*
