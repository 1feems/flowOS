# FlowOS — Product Overview

---

## What It Is

FlowOS is a platform that helps funding programs run better. It gives grant teams a structured way to set up programs, review applications consistently, and keep a record of what they funded and what it produced.

Right now, most grant programs in Web3 are held together with spreadsheets, Notion pages, and email threads. Every round starts from scratch. Reviews are inconsistent. Nobody can tell which programs or tracks actually worked. FlowOS replaces that chaos with a clear, repeatable process.

---

## The Problem

When a grant team receives 50 applications, several things go wrong:

- There is no consistent way to filter out projects that clearly don't fit before reviewers spend time on them
- Every reviewer scores applications differently because the criteria aren't defined clearly enough
- When a round closes, the data from it isn't captured in any useful way — so the next round starts with no learning from the last one
- Applicants who almost qualified receive generic rejections with no guidance on what to fix

These aren't edge cases. They happen in every round at every program operating at scale today.

---

## What FlowOS Does

**Before applications open**, the grant team fills out two forms: one that defines the program (what it funds, who it's for, what a project needs to qualify), and one that sets the specifics for the current round (budget, timeline, goals). Everything else flows from these two forms.

**When applications come in**, an AI agent reads each one against what the program defined and sorts it into one of three outcomes:

- **Pass** — meets the criteria, aligns with what the program is trying to fund, ready for human review
- **Needs Revision** — the project could qualify but the application is missing something specific — the applicant gets clear feedback and can resubmit
- **Not a Fit** — doesn't meet the criteria — recorded with reasons, doesn't go to the review queue

**During review**, the team sees every Pass application with the AI's assessment already filled in — scores against each evaluation criterion, key strengths, key risks, a plain-language summary. Reviewers score applications consistently using the same rubric every time. Human judgment makes every final decision.

**After approval**, the funded project is automatically added to a registry with the KPI fields the program defined. Over time this registry becomes a structured record of what the program funded and what it produced — comparable across rounds.

---

## Who Uses It

**Grant operators** — the people who run the program day to day. FlowOS handles first-pass screening so they spend their time on applications that actually belong in the review queue.

**Ecosystem and growth leads** — the people deciding where funding goes. FlowOS gives them a program-level view of what different rounds and tracks are producing.

**Foundations and governance committees** — accountable for impact. FlowOS gives them structured outcome data, not just spend data.

**Builders and applicants** — submit through a public link, no account needed. If their application needs work, they get specific feedback on what to fix.

---

## Why Now

The volume of grant applications across Web3 ecosystems is growing faster than the teams managing them. Programs that used to receive 20 applications per round now receive 100. The manual process that worked at low volume is breaking at high volume. The teams that figure out how to run structured, AI-assisted review will be able to deploy more capital, more accurately, with less overhead.

---

## Current Status

Working prototype with all core screens built. Forms are validated against real grant program data. The AI screening pipeline is currently running on test data with mocked outputs — the next milestone wires it to a live AI model with structured output.

Grant funding supports building the live AI integration and completing the registry layer.

---

## What FlowOS Does Not Do

FlowOS does not process payments, track milestones after funding, or replace the human judgment of grant reviewers. It handles the coordination work — intake, sorting, consistent evaluation, and record-keeping — so the humans in the process can focus on the decisions that require judgment.
