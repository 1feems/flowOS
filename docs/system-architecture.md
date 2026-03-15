
# Mkondo — System Architecture

## Purpose

This page outlines the current public system architecture for Mkondo. It shows how the product is structured today, how the workflow is designed, and which parts are currently functional versus mocked in the proof-of-concept build.

---

## Stack

| Layer | Technology |
|---|---|
| Frontend | Next.js, React, Tailwind CSS |
| Product UI | Multi-step operator workflow and structured review surfaces |
| Backend Pattern | Next.js application architecture |
| Data Layer | Structured program, round, application, rubric, and registry records |
| AI Layer | Agent evaluation flow designed for structured scoring and triage |
| Current State | Proof-of-concept build with mocked agent outputs |

---

## System Overview

```text
PROGRAM SETUP
  Program Info           → ecosystem, grant type, goals, verticals
  Eligibility            → qualification criteria and exclusions
  Round Intent           → round goals, target projects, metrics, expected outcomes
  Application Builder    → structured template by vertical
  Rubric                 → criteria, scoring logic, and weighting

APPLICATION FLOW
  Applicant submission   → structured proposal form
  Application record     → linked to program and round
  Review context         → application compared against round intent and rubric

AGENT EVALUATION
  Program context loaded → goals, eligibility, expected outcomes, rubric
  Application assessed   → structured pre-evaluation
  Triage returned        → Pass / Needs Revision / Not a Fit
  Review summary created → scores, strengths, risks, summary

OPERATOR REVIEW
  Application queue      → filtered by triage result
  Application detail     → completed application + AI evaluation
  Human decision         → approve, reject, or request more information

REGISTRY LAYER
  Program profile        → program setup and goals
  Registry views         → rounds, projects, and outcome structure
  Funded project record  → intended output of approved applications
## Data Model

| Entity | Description |
|---|---|
| Program | Stores core program configuration, goals, and structure |
| Round | Stores round-level budget, metrics, outcomes, and target projects |
| Application Template | Defines the structure applicants complete for a specific vertical |
| Rubric | Stores evaluation criteria, scoring logic, and weighting |
| Application | Stores submitted applicant data and structured responses |
| Agent Evaluation | Stores triage label, scores, strengths, risks, and summary |
| Review | Stores reviewer scoring and final decision |
| Registry Record | Represents approved projects and program-level outcome tracking |

---

## Agent Design

The Mkondo agent is designed as a program-intent-driven evaluation layer. It does not evaluate applications against a generic grant checklist. It evaluates each submission against the specific program setup, round intent, eligibility logic, expected outcomes, and rubric configured by the operator.

### Agent Inputs

- Program Info
- Eligibility criteria
- Round Intent
- Application responses
- Rubric criteria and weights

### Agent Outputs

| Output | Description |
|---|---|
| Triage label | Pass / Needs Revision / Not a Fit |
| Eligibility result | Whether the submission meets the defined gate criteria |
| Rubric pre-scores | Preliminary scoring against each criterion |
| Strengths | Positive signals identified in the application |
| Risks | Concerns or execution risks surfaced in review |
| Summary | Plain-language summary of the submission |
| Review support | Structured context for human decision-making |

### Decision Logic

The agent supports review, but does not make final funding decisions. Human reviewers remain responsible for approvals, rejections, and requests for more information.

---

## Current Functional State

### Functional

- Multi-step operator setup flow
- Program and round configuration
- Consumer and DeFi application templates
- Rubric configuration
- Application detail and review views
- AI evaluation surfaces in the review flow
- Program profile view
- Registry prototype views

### Mocked

- Live AI model call
- Persistent backend data layer across the full workflow
- Public applicant intake infrastructure
- Automatic registry creation on approval
- Full end-to-end production data flow

---

## Build Direction

The current architecture is designed to support a full structured funding workflow:

- define the program
- configure the round
- collect structured applications
- evaluate submissions against intent
- support human review
- carry approved applications into a registry layer

The proof-of-concept build focuses on validating that workflow end to end before deeper infrastructure and live model integration are added.

---

## Next Technical Steps

- Replace mocked agent outputs with live model integration
- Connect application intake to persistent backend records
- Link approved applications to registry creation logic
- Expand structured vertical templates
- Strengthen registry reporting across rounds and funded projects
