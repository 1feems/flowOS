# Mkondo — Product Requirements Document

Early Proof of Concept

## 01 — Product Overview

Mkondo is a funding coordination platform that helps ecosystems design clear grant programs, run AI-assisted application intake and review, and maintain a registry of programs, rounds, funded projects, and their impact metrics.

The goal is to turn fragmented grant activity into a structured lifecycle so ecosystems can direct capital more deliberately and learn from each funding round.

### What Mkondo Enables

| Action | What it means |
|---|---|
| Design | Define program intent, goals, tracks, and eligibility in a structured schema |
| Screen | Pre-filter applications using an AI triage system that labels submissions Pass / Needs Revision / Not a Fit |
| Review | Evaluate applications with consistent rubrics rather than ad-hoc criteria |
| Learn | Maintain a registry of programs, rounds, and funded projects with defined impact metrics |

### What Mkondo Does Not Cover

Mkondo does not handle milestone tracking, payment processing, or full grant operations. Its focus is on structured program design, AI-assisted triage, consistent application review, and a registry that records program outputs.

## 02 — Problem Statement

Mkondo serves crypto and Web3 ecosystems that run non-dilutive funding programs, including foundations, DAOs, L2 ecosystems, and treasuries, along with the operators who manage those programs.

### Common Breakdowns in Funding Programs

| Problem | Description |
|---|---|
| No unified lifecycle | Program information is spread across forums, documents, forms, and spreadsheets, with no consistent flow from program design to application review and outcomes |
| Inconsistent review | Applications are evaluated against inconsistent criteria, making decisions slower and difficult to compare across rounds |
| Limited outcome visibility | Ecosystems often publish spend data but rarely track structured outcomes, making it hard to understand program impact |
| No program-level learning | Data about funded projects and rounds is fragmented, preventing ecosystems from comparing results or improving programs over time |

## 03 — Target Users

| User | Role | What Mkondo provides |
|---|---|---|
| Grant / Ecosystem Funding Operators | Design programs, run rounds, coordinate reviewers | Structured program setup, AI triage of applications, and a review queue |
| Ecosystem / Growth Leads | Decide where non-dilutive capital is deployed | Registry views and metrics to compare rounds and program tracks |
| Foundations / Governance Committees | Approve budgets and assess funding impact | High-level visibility into funded projects and reported outcomes |
| Builders / Applicants | Submit funding applications | Public application forms with structured feedback if revisions are needed |

## 04 — Product Scope

### In Scope

- Program creation workflow: Program Intent Form, Application Form setup, and Rubric setup
- Public application form for builders with no login required
-  Application intake flow to validate submissions and support screening
- Screening agent that triages applications as Pass / Needs Revision / Not a Fit based on program intent
- Operator review queue displaying the application, AI evaluation summary, rubric scoring, and decision tools
- Program registry storing programs, rounds, funded projects, and KPI rollups

### Out of Scope

- Grantee milestone tracking
- Payment processing or on-chain disbursements
- Multi-tenant architecture
- Full authentication system
- Real-time collaboration between reviewers
- Mobile-optimized interfaces

## 05 — Key User Flows

### Core Demonstration Flow

1. An operator creates a program and defines KPIs in the registry.
2. A builder submits an application using the public form URL with no login required.
3. The screening agent evaluates eligibility and program fit, returning Pass, Needs Revision, or Not a Fit.
4. The operator approves the application, which creates a grant profile and updates the registry.
5. The registry displays the funded project with KPI fields ready to be populated.

### Operator Flow

1. Create a program with name, ecosystem, mission, budget, eligibility, and logo.
2. Create a round with dates, funding range, tracks, and application limits.
3. Complete the Program Intent Form defining goals, outcomes, and evaluation criteria.
4. Configure the application form using a template and required fields.
5. Set the rubric with criteria, scoring ranges, and weights.
6. Publish the program, generating a public application URL.
7. Share the application link for builder submissions.
8. Receive applications in the review queue after agent screening.
9. Review Pass applications with the full submission, AI evaluation summary, and rubric.
10. Make a final decision: Approve, Reject, or Request additional information.

### Builder Flow

1. Receive the application link from the program page or operator.
2. Open the public application form without creating an account.
3. Complete initial eligibility questions before the full form appears.
4. Submit the completed application.
5. Receive a confirmation screen with an application ID.
6. If labeled Needs Revision, receive structured feedback and resubmit.

## 06 — Core Features

### Program Intent Builder

Operators define program goals, target applicants, eligibility criteria, tracks, and KPI metrics through a structured form before applications open. This configuration determines the application template, screening criteria, evaluation rubric, and registry KPI fields.

### Application Intake

Each round generates a public application form URL. Builders submit applications without logging in. The intake flow is designed to validate required fields, capture submissions, return a confirmation with an application ID, and support the screening process.

### Application Intake and Review

Applications labeled Pass enter the operator review queue. Reviewers see the full submission, the agent’s evaluation summary and preliminary scores, and the rubric criteria. Human reviewers score each criterion and make the final decision.

### Funding Program Registry

The registry stores records for programs, rounds, and tracks. Approved applications automatically create a funded project entry with KPI fields defined at the program level. Registry views summarize program activity across rounds.

## 07 —  AI-Assisted Pre-Filtering AGent

Triages incoming applications before human review. Each submission receives a structured assessment and is labeled Pass, Needs Revision, or Not a Fit, helping reviewers quickly identify which applications should move forward for full evaluation.

Further technical details are maintained in the private repository.

### Agent Output Fields

| Field | Description |
|---|---|
| triage_label | Pass / Needs Revision / Not a Fit |
| confidence | High / Medium / Low |
| eligible | true / false |
| rubric_pre_scores | Preliminary score per rubric criterion with rationale |
| overall_pre_score | Weighted rubric score |
| intent_alignment | 1–5 score representing fit with program goals |
| strengths | 2–4 summarized strengths |
| risks | 2–4 identified risks |
| revision_feedback | Returned for Needs Revision applications |
| not_a_fit_reason | Recorded for Not a Fit applications |
| tags | Outcome tags used by the registry |
| summary | 2–3 sentence summary of the application |

The agent does not make approval decisions. Human reviewers evaluate Pass applications and make final funding decisions.

## 08 — Grant Registry

### Program-Level View Per Round

- Round ID, Grant Type, Open Date, Close Date
- Total applications, approved grants, total allocated funds, average grant size
- Top tracks, pass rates, and common screening flags

### Per-Grant Profile (Created on Approval)

- Program, round, and track information
- Grant type, approved amount, decision date, and status
- KPI metric slots defined at the program level
- Optional external ID link for cross-platform tracking


## 09 — Current State

### Existing Components

- Working prototype with core screens, including Dashboard, Applications Queue, Application Detail, AI evaluation views, and registry views
- Functional operator-side form flows for Program Info, Program Intent, Application Form setup, and Rubric setup
- Mock screening agent pipeline producing structured results for application review
- Registry prototype with program and funded project views

### Mocked vs Functional Components

The screening layer currently runs on deterministic mock outputs. Live LLM integration, application intake infrastructure, and deeper backend functionality are planned for later implementation.


### Mocked vs Functional Components

The screening agent currently produces deterministic mock outputs. Integrating a live LLM call using the Claude API will replace the mocked responses with structured JSON output.

## 10 — Risks

| Risk | Mitigation |
|---|---|
| Screening quality depends on the quality of the intent form | Use structured templates with examples and validation |
| Operator adoption requires changes to existing workflows | Provide documentation and operator playbooks |
| Builder completion rates for application forms | Include clear guidance and a revision flow with actionable feedback |
| KPI fields may remain empty | Registry design highlights missing metrics to encourage completion |


## 11 — Roadmap (Post v1)

- Replace mocked outputs with live LLM screening via the Claude API
- Form builder UI for configurable application forms without code
- Support for multiple programs operating within the same environment
- Cross-round registry analysis to compare outcomes across programs and tracks
- External integrations such as on-chain registry hooks and data export (CSV / API)
