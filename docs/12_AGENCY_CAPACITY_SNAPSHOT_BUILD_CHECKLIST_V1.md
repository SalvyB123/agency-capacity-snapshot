# Project Build Checklist — Agency Capacity Snapshot (Version 1)

This checklist translates the **PRD** into a concrete, executable build plan.  
If any item below is incomplete, **Version 1 is not finished**.

This checklist is **project-specific** and sits underneath the Standard Build Checklist.

---

## Phase A — Foundation & Setup

**Objective:** Establish a production-grade baseline.

- [ ] Git repository created for this project
- [ ] Next.js app scaffolded (App Router, TypeScript, Tailwind)
- [ ] Project runs locally without errors
- [ ] Supabase project created
- [ ] Environment variables configured locally and in Vercel
- [ ] App deployed to a live URL
- [ ] Basic logged-out / logged-in experience confirmed

**Exit criteria:**  
A user can log in to a live deployed app.

---

## CI & Quality Gates (Applies to All Phases)

**Objective:** Prevent broken or unverified changes reaching `main`.

- [ ] GitHub Actions workflow configured for this repository
- [ ] CI runs automatically on every pull request to `main`
- [ ] CI includes:
  - [ ] Linting
  - [ ] Type checking (where applicable)
  - [ ] Backend tests
  - [ ] Frontend tests
  - [ ] Production build
- [ ] Cypress E2E tests added once meaningful UI flows exist
- [ ] Cypress tests run locally before being relied on in CI
- [ ] Pull requests are not merged with failing checks

**Rules:**
- Local testing is mandatory before opening a PR  
- CI exists to catch regressions, not replace local responsibility  
- If tests only pass in CI but not locally, the work is not complete  

**Exit criteria:**  
Any change merged to `main` has been verified locally and validated by CI.

---

## Phase B — Authentication & Security

**Objective:** Ensure safe, scoped access from day one.

- [ ] Supabase Auth configured (email/password or magic link)
- [ ] User profile table created and linked to auth user
- [ ] Protected routes enforced (unauthenticated users blocked)
- [ ] Organisation / tenant concept defined (even if single-org V1)
- [ ] Row Level Security enabled on all client-accessible tables
- [ ] RLS policies tested with at least two users

**Exit criteria:**  
Users can only see their own organisation’s data.

---

## Phase C — Data Model (Capacity Planning)

**Objective:** Define the minimum data needed to support the PRD.

- [ ] `team_members` table created
- [ ] Capacity assumptions defined (e.g. days per week)
- [ ] `allocations` table created (member, week, effort)
- [ ] Time horizon logic defined (4–6 weeks forward)
- [ ] Seed data added for:
  - [ ] Team members
  - [ ] Existing allocations
- [ ] Data model documented in plain English

**Exit criteria:**  
The database can represent a realistic capacity picture without workarounds.

---

## Phase D — UI Intent & Primary Screen

**Objective:** Build the one screen that matters.

- [ ] Primary screen identified: **Capacity Overview**
- [ ] Rows = team members
- [ ] Columns = weeks (next 4–6 weeks)
- [ ] Visual hierarchy supports fast scanning
- [ ] Clear empty states when no data exists
- [ ] Loading states handled clearly
- [ ] UI intentionally simple (internal ops tool)

**Exit criteria:**  
An Ops Director can understand capacity at a glance.

---

## Phase E — Core Capacity Logic

**Objective:** Make capacity trustworthy and explainable.

- [ ] Weekly capacity calculated per team member
- [ ] Allocations correctly subtract from availability
- [ ] Over-capacity thresholds defined and applied
- [ ] Under-utilisation thresholds defined and applied
- [ ] Calculations explained clearly in code comments or docs

**Exit criteria:**  
Capacity numbers are predictable and easy to reason about.

---

## Phase F — Scenario Simulation (Manual)

**Objective:** Support “what if we add this work?” decisions.

- [ ] Scenario input supports:
  - [ ] Start week
  - [ ] Duration (weeks)
  - [ ] Effort (days per week or total days)
- [ ] Scenario does not persist to the database
- [ ] Scenario overlays existing capacity view
- [ ] Scenario can be removed instantly
- [ ] Real data remains unchanged

**Exit criteria:**  
User can add and remove hypothetical work without risk.

---

## Phase G — Risk Signposting (Rules-Based)

**Objective:** Highlight problems without solving them.

- [ ] Individual overload clearly flagged
- [ ] Sustained overload across weeks flagged
- [ ] At-risk capacity visually distinct
- [ ] No optimisation or auto-balancing logic present
- [ ] Risk logic documented in plain language

**Exit criteria:**  
Risks are obvious without interpretation.

---

## Phase H — AI-Assisted Summary (Optional)

**Objective:** Use AI to assist thinking, not decision-making.

- [ ] AI summary is user-triggered only
- [ ] AI calls are server-side
- [ ] AI output is clearly labelled
- [ ] AI summarises:
  - [ ] Key risks
  - [ ] Impact of scenario (if present)
- [ ] App functions fully with AI disabled

**Exit criteria:**  
AI adds value but is never required.

---

## Phase I — Acceptance & Handover

**Objective:** Deliver professionally.

- [ ] App deployed and stable
- [ ] Acceptance walkthrough completed
- [ ] Known limitations documented
- [ ] V2 ideas captured separately
- [ ] README / handover notes written
- [ ] Decision log completed for key build choices

### Client Walkthrough Readiness
- [ ] 10–15 minute client walkthrough script prepared
- [ ] Key decisions the tool supports are explicitly demonstrated
- [ ] Limitations explained clearly and confidently
- [ ] Likely client questions anticipated and answered

**Exit criteria:**  
The app could be handed to a real client with confidence.

---

## Operational Safety Checks

- [ ] App behaves predictably with incomplete or imperfect data
- [ ] No irreversible actions exist in Version 1
- [ ] Any destructive actions require explicit confirmation
- [ ] Error states explain what happened and what to do next
- [ ] User cannot accidentally corrupt core data through normal usage

---

## Final Validation

- [ ] Ops Director can answer “Can we take this work on?” in under 5 minutes
- [ ] Spreadsheet reconciliation no longer required
- [ ] Scope matches PRD exactly
- [ ] No out-of-scope features present
- [ ] Delivery aligns with consultancy positioning

---

*This checklist ensures Version 1 is clear, safe, focused, and client-ready — not overbuilt.*