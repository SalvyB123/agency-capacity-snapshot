# Product Definition (PRD) — Version 1

## Product Name
**Agency Capacity Snapshot** (working title)

---

## Product Goal
Enable the Operations Director to confidently decide whether new work can be accepted in under five minutes, using a trusted, forward-looking view of team capacity.

---

## Target User
**Primary user:** Operations Director  
Version 1 is designed for one primary user only.

---

## Core User Job
Understand whether the team has real capacity over the next 4–6 weeks, and what the impact of new work would be — without manually fixing a spreadsheet.

---

## Version 1 Must-Haves (Non-Negotiable)

### 1. Capacity Overview
- A single view showing:
  - Team members
  - Weekly capacity over the next 4–6 weeks
  - Known allocations (retainers + confirmed projects)
- Clear visual indication of:
  - Under-utilisation
  - At-risk capacity
  - Over-allocation
- This view must be trusted more than the existing spreadsheet.

---

### 2. Scenario Simulation (Manual)
- Ability to add a hypothetical piece of work:
  - Start week
  - Duration (in weeks)
  - Rough effort (e.g. days per week or total days)
- Scenario does **not** auto-assign people.
- Scenario can be removed instantly.
- Scenario does **not** persist or affect real data.

---

### 3. Risk Signposting (Rules-Based)
- Clear flags when:
  - Individuals exceed safe capacity thresholds
  - Teams are consistently overloaded
- No optimisation logic.
- No automatic rebalancing.

The product highlights problems; it does not solve them.

---

### 4. AI-Assisted Summary (Optional)
- User-triggered only.
- Supports questions such as:
  - “What are the main capacity risks?”
  - “What changes if we add this work?”
- AI output is:
  - Read-only
  - Clearly labelled as AI-generated
  - Non-binding

If AI is unavailable, all core functionality must still work.

---

## Explicitly Out of Scope (Version 1)

The following are intentionally excluded:

- Automatic resource assignment
- Task-level or project management
- Payroll or financial data
- Time tracking input or approvals
- Live integrations with external systems
- Real-time updates from delivery staff
- Client-facing views
- Notifications or alerts
- Optimisation or recommendation engines
- Mobile-first optimisation

Anything not listed in “Must-Haves” is out of scope by default.

---

## Non-Goals (Version 1)

Version 1 is not intended to:
- Optimise team utilisation
- Recommend staffing decisions
- Replace project management tools
- Act as a source of record for time tracking
- Eliminate the need for human judgement

These may be valid future directions, but are intentionally excluded to keep Version 1 focused and adoptable.

---

## Data Assumptions & Ownership

- Capacity data is provided and maintained by the business.
- The product does not infer availability or utilisation automatically.
- Outputs reflect the inputs at the time of viewing.
- Responsibility for data accuracy remains with the Operations team.

The product is designed to make capacity visible and assessable — not to validate or correct underlying data.

---

## User Journeys (Written)

### Journey 1 — Weekly Capacity Check
1. User logs in
2. Views capacity overview for the next 4–6 weeks
3. Scans for upcoming pressure points
4. Leaves without editing data

---

### Journey 2 — New Work Decision
1. User opens scenario simulation
2. Adds a hypothetical piece of work
3. Sees immediate impact on capacity
4. Reviews risk indicators
5. Optionally requests AI summary
6. Removes scenario
7. Makes an external decision (accept / decline work)

---

## AI Role (Strict)

- **AI assists with:**
  - Summarising risks
  - Explaining trade-offs
  - Answering “what if” questions

- **AI is triggered by:**
  - Explicit user action only

- **AI output is presented as:**
  - Read-only text
  - Clearly labelled as AI-generated insight

- **If AI fails or is disabled:**
  - The product remains fully usable
  - No workflows are blocked

AI accelerates thinking; it does not replace it.

---

## Success Criteria (Version 1)

Version 1 is successful when:
- The Operations Director can answer “Can we take this work on?” in under five minutes
- Capacity can be assessed without spreadsheet reconciliation
- The application is live and deployed
- The tool is used in at least one real operational decision
- Known limitations are documented and accepted

---

## Known Limitations (Accepted)

- Capacity accuracy depends on manual inputs
- No automatic updates from time tracking
- No historical analysis or reporting
- No optimisation or recommendations

These are conscious trade-offs to prioritise speed, clarity, and adoption.

---

## Definition of Done

Version 1 is considered complete when:
- All must-haves are implemented
- All out-of-scope items are excluded
- The application is deployed and accessible
- Acceptance criteria are met
- Handover notes and known limitations are documented