# FlowOS — Product Overview

FlowOS is a funding coordination and strategy platform for ecosystem grants and equity-free funding programs that connects program design, AI-assisted application screening, and funded project tracking into one system — enabling ecosystems to align funding decisions with their long-term growth strategy.

The platform implements your funding strategy. The services produce it.

---

## The Problem

- There is no clear way to define what a program is funding before intake opens, so every round is built from scratch and nothing carries forward
- Applications arrive with no pre-filtering against program criteria, so teams read everything manually and reviewers work from different standards each round
- There is no structured record of what programs produced, so performance stays invisible and every budget conversation starts without evidence
- Marketing and ecosystem teams have no visibility into what funding programs are building, so there is no way to align or collaborate around shared outcomes

---

## Who It's For

**Users**

| User | What they do in FlowOS |
|---|---|
| Program Operators | Set up programs, configure forms and rubrics, manage the review queue, make funding decisions, track program performance in the registry |
| Grant Committee / Reviewers | Score applications in the review queue using the rubric, with AI pre-scores already surfaced |
| Builders / Applicants | Submit through the public form, receive feedback if revision is needed, resubmit |

**Stakeholders**

| Stakeholder | What they need from FlowOS |
|---|---|
| Foundation Leadership | Program-level view of what rounds and tracks are producing to inform future allocation |
| Protocol Treasury | Structured outcome record linking spend to results for governance reporting and budget justification |

---

## Platform Features

**Form Builder**

- **Program Info Builder** — Set the permanent identity of a funding program: ecosystem, vertical, eligibility criteria, outcome focus, and expected deliverables
- **Round Intent Builder** — Define what a specific round is funding: budget, target applicants, project types in scope, and the impact metrics that will populate the registry
- **Rubric Builder** — Configure the scoring criteria used by both the AI screening agent and human reviewers
- **Application Form Builder — DeFi / Protocols** — Vertical-specific form that loads from the program config and collects the structured information reviewers need
- **Application Form Builder — Consumer Apps / Wallets** — Same structure, tailored for consumer-facing projects

**AI-Assisted Pre-Filtering**
Every application is automatically evaluated against the program's eligibility criteria, stated intent, round goals, expected deliverables, and rubric — before any human reviews it. Each submission comes back with a triage decision (Pass / Needs Revision / Not a Fit), a recommend approve / decline label, preliminary scores per rubric criterion, strengths, risks, and a plain-language summary. Needs Revision applications receive specific actionable feedback so applicants can resubmit. Human reviewers make every final decision.

**Structured Review Queue**
Pass applications enter a structured queue with the AI evaluation and recommendation already surfaced. Reviewers score against the same rubric every round — consistent and comparable across rounds.

**Program Registry**

- **Program-level view** — Each round is recorded with its ID, dates, total applications, approved grants, total allocated budget, and pass rate — so operators can see how a round performed at a glance
- **Project-level profiles** — Approved projects are automatically added with grant type, approved amount, decision date, and the KPI metric slots defined at the program level — a structured record of what each round funded and what it was expected to produce

---

## How It Works

**1. Program Intent & Form Builder**
- Fills out the Program Info Builder — program identity, ecosystem, eligibility criteria, outcome focus, vertical, expected deliverables
- Fills out the Round Intent Builder — what this round is funding, budget, target applicants, project types in scope, impact metrics
- Configures the Rubric — scoring criteria used by both the AI agent and human reviewers
- Publishes the round — system generates a public application link at /apply/[round-id]

**2. Builder applies**
- Opens the public link — no account required
- Completes Pre-Screening — 3 questions pulled from the program config to confirm fit before the full form loads
- Completes the Application Form — vertical-specific template (DeFi / Protocols or Consumer Apps / Wallets)
- Submits — receives confirmation and application ID

**3. AI screens the application**
- Every submission is automatically evaluated against the program's eligibility criteria, stated intent, round goals, expected deliverables, and rubric
- Returns Pass / Needs Revision / Not a Fit with a recommend approve / decline label, pre-scores per rubric criterion, strengths, risks, and a plain-language summary
- Needs Revision applications receive specific actionable feedback so applicants can resubmit

**4. Operator reviews and decides**
- Pass applications enter the review queue with the AI evaluation and recommendation already surfaced
- Reviewer scores against the rubric — same criteria applied every round
- Operator clicks Approve

**5. Approved Grant Profile created — Registry updated**
- Approved Grant Profile is auto-created — program, round, grant type, approved amount, decision date, and KPI metric slots defined at the round level
- Registry row updates automatically — program-level view reflects total applications, approved grants, total allocated, and pass rate
- Every round adds to the record — performance is visible and comparable across rounds over time

**How the Registry Works**
- Every approved project is automatically added when an operator clicks Approve — no manual entry
- Each project record contains: program, round, grant type, approved amount, decision date, and the KPI metric slots defined at the round level
- The program-level view shows: round ID, open/close dates, total applications, approved grants, total allocated, average grant size, and pass rate
- KPI fields are pre-defined at the round level — the same metrics apply to every funded project in that round, making outcomes comparable
- Operators update KPI fields as funded projects deliver — creating a structured record of what each round produced
- Each new round adds to the same registry — so performance is visible and comparable across rounds and tracks over time

---

## Services

The platform implements your funding strategy. The services help you build it.

| Service | What it is | When |
|---|---|---|
| Program Design | Define program goals, tracks, eligibility, rubric, and KPIs — produces the intent config that drives FlowOS | Available now |
| Program Assessment | Audit an existing program — where is the Design → Fund → Assess loop broken and what needs to change | Available now |
| Round Strategy | Define what to fund in a specific round — tracks, budget split, outcome targets | Available now |
| Impact Reporting | Structured report after a round closes — what the capital produced, what to change next round | Coming |
| Cross-Program Benchmarking | Compare outcomes across programs or chains | Coming |
| Reviewer Calibration | Reduce scoring variance across distributed review teams | Coming |

---

## Built for Crypto Ecosystems

- Permissionless applications mean anyone can apply with no prior relationship — structured intake is essential at scale
- Small teams managing high volume need the process to do more of the work
- Decentralised review committees need a shared evaluation framework to make consistent decisions
- On-chain data means outcome verification can eventually be pulled directly, not self-reported
- Funded project reputation is public and portable — the registry is built to surface track record as part of future evaluation

---

## Current Status

Working prototype with all core screens built. Forms validated against real grant program data. AI screening pipeline runs on test data with mocked outputs — next milestone wires it to a live AI model with structured JSON output.

Grant funding supports building the live AI integration and completing the registry layer.
