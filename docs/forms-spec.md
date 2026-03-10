# FlowOS — Forms Specification

Technical reference for agent screening, application intake, and program configuration.

---

## Forms Index

### Operator Forms

| # | Form | Who fills it | When |
|---|---|---|---|
| 1 | Program Info | Operator | Once per program |
| 2 | Program Round Intent | Operator | Each funding cycle |
| 3 | Rubric — User Outcome | Operator | Once per program or round |
| 4 | Rubric — Ecosystem Outcome | Operator | Once per program or round |

### Applicant Forms (Public — no login required)

| # | Form | Who fills it | When |
|---|---|---|---|
| 5 | Pre-Screening | Applicant | Before application loads |
| 6 | Application Form — DeFi / Protocols | Applicant | Per submission |
| 7 | Application Form — Consumer Apps / Wallets | Applicant | Per submission |

---

## OPERATOR FORMS

---

## Form 1 — Program Info

Sets the permanent identity of a grant program. Created once by the operator. All fields are passed to the agent as program-level context when screening applications.

| Field | Type | Required | Agent Use |
|---|---|---|---|
| Program Name | Text | Yes | Program identity label in all agent outputs |
| Ecosystem / Chain | Text | Yes | Agent assesses ecosystem alignment of submitted projects |
| Program Description | Long Text | Yes | Agent reads to understand program purpose and gap being addressed |
| Funding Type | Static | Yes | Context — always Grant in v1 |
| Mechanism | Dropdown | Yes | Context — always Grant in v1. Options: Grant |
| Outcome Focus | Dropdown | Yes | Agent uses to determine which outcome lens to apply. Options: User Outcome, Ecosystem Outcome |
| Area of Focus | Checkbox group | Yes | Agent uses to assess whether submitted project targets the right focus area. User Outcome: Acquisition, Retention, Activation, Other. Ecosystem Outcome: Security, Infrastructure, Interoperability, Developer Tools, Ecosystem Growth, Other |
| Vertical | Dropdown | Yes | Determines application form template. Options: DeFi / Protocols, Consumer Apps / Wallets |
| Eligibility Criterion 1 | Text | Yes | Agent checks independently — sets eligible: true / false |
| Eligibility Criterion 2 | Text | Yes | Agent checks independently — sets eligible: true / false |
| Eligibility Criterion 3 | Text | Yes | Agent checks independently — sets eligible: true / false |
| Eligibility Criterion 4 | Text | Optional | Additional eligibility check |
| Eligibility Criterion 5 | Text | Optional | Additional eligibility check |
| Expected Deliverables | Long Text | Yes | Agent assesses whether proposed deliverables match program expectations |
| Rubric | Dropdown | Yes | Selects rubric agent scores against. Options: User Outcome Rubric, Ecosystem Outcome Rubric |
| Program Lead / Contact | Text | Yes | Internal metadata — not passed to agent |
| Primary Impact Goal | Text | Optional | Agent uses as top-level intent signal for intent_alignment |

---

## Form 2 — Program Round Intent

Filled each funding cycle. Captures round logistics and program intent for the round. Pre-filled fields carry over from Program Info automatically.

| Field | Type | Required | Agent Use |
|---|---|---|---|
| Program Name | Pre-filled from Program Info | — | Context |
| Program Description | Pre-filled from Program Info | — | Context |
| Vertical | Pre-filled from Program Info | — | Context |
| Outcome Focus | Pre-filled from Program Info | — | Context |
| Area of Focus | Pre-filled from Program Info | — | Context |
| Eligibility | Pre-filled from Program Info | — | Agent checks each criterion against submitted application |
| Funding Round ID | Text | Yes | Round identifier — used in all agent output records |
| Grant Type | Dropdown | Yes | Context for agent. Options: Builder Grant, Infrastructure Grant, Seed Grant |
| Round Start Date | Date picker | Yes | Metadata |
| Round End Date | Date picker | Yes | Metadata |
| Total Budget (Token) | Number | Yes | Agent uses to assess budget reasonableness |
| Total Budget (USD) | Number | Optional | Agent uses to assess budget reasonableness |
| Area of Focus (this round) | Checkbox group | Yes | Agent uses as primary intent signal for this round. Options: Acquisition, Retention, Activation, Other |
| Target Applicants | Short Text | Yes | Agent uses for fit assessment — who is this round looking for? |
| Project Type 1 | Editable text | Optional | Agent uses to assess whether submitted project is in scope |
| Project Type 2 | Editable text | Optional | Agent uses to assess whether submitted project is in scope |
| Project Type 3 | Editable text | Optional | Agent uses to assess whether submitted project is in scope |
| Impact Metric 1 | Text | Yes | Agent tags funded projects with these metrics in registry output |
| Impact Metric 2 | Text | Optional | Agent tags funded projects with these metrics in registry output |
| Impact Metric 3 | Text | Optional | Agent tags funded projects with these metrics in registry output |

---

## Form 3 — Rubric — User Outcome

*(To be completed)*

---

## Form 4 — Rubric — Ecosystem Outcome

*(To be completed)*

---

## APPLICANT FORMS (Public)

---

## Form 5 — Pre-Screening

Shown before the full application loads at /apply/[round-id]. All fields auto-populated from operator forms. Applicant must complete all sections to continue.

| Field | Type | Required | Pulls From | Agent Use |
|---|---|---|---|---|
| What type of project are you building? | Dropdown | Yes | Form 1 — Vertical | Loads correct application form template. Agent uses for vertical context |
| Which outcome does your project primarily target? | Dropdown | Yes | Form 1 — Area of Focus | Agent uses as first intent_alignment signal. Options: Acquisition, Retention, Activation |
| Do you meet the following requirements? | Checklist — must check all | Yes | Form 1 — Eligibility Criteria (1, 2, 3) | All checked = eligible: true. Any unchecked = eligible: false |

---

## Form 6 — Application Form — DeFi / Protocols

*(To be completed)*

---

## Form 7 — Application Form — Consumer Apps / Wallets

*(To be completed)*
