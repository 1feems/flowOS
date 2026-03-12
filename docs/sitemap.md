# FlowOS — Sitemap & System Overview

---

## Sitemap

### Operator (Authenticated)

**Dashboard** — overview, applications to review, active programs, recent activity

**Create Program**
- Program Info Form
- Program Round Intent Form
- Application Form Setup
- Rubric Setup
- Review & Publish

**Applications**
- Applications Queue
- Application Detail
- AI Evaluation Panel
- Decision Screen
- Funded Applications

**Registry**
- Programs Table
- Program Page

---

### Public (No Login Required)

**/apply/[round-id]**
- Pre-Screening
- Application Form
- Submission Confirmation

---

## System Overview

```
OPERATOR SETUP
  Program Info Form       →  program config: ecosystem, eligibility, rubric
  Program Round Intent    →  round config: dates, budget, goals, metrics
  Application Form        →  field template per vertical
  Rubric                  →  scoring criteria + weights

PUBLIC FORM → INTAKE
  Builder submits         →  application linked to program + round
  Confirmation            →  application ID returned to builder

AGENT PIPELINE
  Context loaded          →  program intent + rubric pulled by round
  Application evaluated   →  fields scored against program context
  Triage result           →  Pass / Needs Revision / Not a Fit
  Queue updated           →  application appears in operator review queue

OPERATOR REVIEW
  Decision made           →  Approve / Reject / Request Info
  On approval             →  Grant Profile auto-created in registry

REGISTRY
  Program view            →  rounds, funded projects, KPI fields
```

---

## User Flow

**Operator — Setting Up a Program**
1. Log in → create a new program
2. Fill in Program Info — eligibility, outcome focus, vertical
3. Configure the Round — budget, target applicants, success metrics
4. Set up the Application Form and Rubric
5. Publish — system generates a public `/apply/[round-id]` URL

**Builder — Submitting an Application**
1. Open the public apply link — no login required
2. Complete Pre-Screening — basic eligibility check
3. Fill in the Application Form
4. Submit — receive confirmation with application ID

**Operator — Reviewing Applications**
1. Open Applications Queue — applications arrive pre-labeled by AI
2. Open Application Detail — AI evaluation panel surfaces rubric scores, strengths, risks
3. Make decision — Approve / Reject / Request Info
4. Approved projects auto-added to the Registry
