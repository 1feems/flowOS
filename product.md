# FlowOS — Product Overview

FlowOS is a funding coordination platform for ecosystem grants and equity-free funding programs. It enables teams to design funding rounds, screen applications with AI-assisted pre-filtering, and track funded projects through a structured program registry.

---

## The Problem

Grant programs in Web3 are fragmented and manual. Operators manage applications across Notion, spreadsheets, and forms with no consistent process. Reviews are inconsistent. Funded project outcomes are rarely tracked. There is no way to see what a program actually produced across rounds.

---

## What FlowOS Does

| Feature | Description |
|---|---|
| Program Intent Builder | Define program goals, outcomes, eligibility, and funding scope before launching a round |
| Structured Application Builder | Build application forms aligned with program intent and evaluation criteria |
| AI-Assisted Pre-Filtering | Pre-screen applications against program requirements and rubric criteria — labelled Pass / Needs Revision / Not a Fit before human review |
| Application Intake & Review | Collect and review submissions in a structured workflow with consistent rubrics and AI pre-scores already surfaced |
| Funding Program Registry | A record of every round, funded project, and outcome — so ecosystems can compare programs and improve over time |

---

## Who It's For

| User | Role |
|---|---|
| Grant Operators | Design programs, run rounds, review applications |
| Ecosystem / Growth Leads | Decide where non-dilutive capital goes |
| Foundations / Governance Committees | Approve budgets, accountable for impact |
| Builders / Applicants | Submit via public form — no login required |

---

## How It Works

1. Operator creates a program and defines intent, eligibility, and rubric
2. Operator publishes a round — system generates a public application URL
3. Builder submits via public form — no login required
4. Agent pre-screens the application — Pass / Needs Revision / Not a Fit
5. Operator reviews Pass applications with AI pre-scores already surfaced
6. Operator approves — funded project auto-added to registry with KPI fields

---

## Current Status

Early proof of concept. Prototype in active development.

- Forms: Program Info, Program Round Intent, Application Form, Rubric
- Agent: mock implementation — deterministic outputs based on seeded data
- Registry: programs table and program page
- Public application form at /apply/[round-id]

---

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | Next.js, Tailwind CSS |
| Backend | Next.js API Routes |
| Database | PostgreSQL, Prisma |
| Auth | NextAuth.js |
| Agent | Claude API (structured JSON output) |
| Hosting | Vercel + Railway |

---

## Links

- Figma Prototype: *coming soon*
- Forms Specification: [docs/forms-spec.md](docs/forms-spec.md)
- Product Requirements: [docs/prd.md](docs/prd.md)
- Site Map: [docs/sitemap.md](docs/sitemap.md)
