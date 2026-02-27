---
applyTo: "**"
---

# Documentation Rules

Every action, decision, and learning must be documented. If it's not written down, it didn't happen.

## Decision Records (ADRs)

- **Location:** `docs/decisions/NNNN-title.md`
- **When:** Any significant decision — technology choices, architecture, business model pivots, process changes, scope decisions
- **How:** Use `/decide [title]` to create a properly formatted ADR
- **Numbering:** Sequential, zero-padded to 4 digits (0001, 0002, ...)
- **Status lifecycle:** Proposed → Accepted → Superseded/Deprecated/Amended
- **Required fields:** Date, Status, Cynefin Domain, Context, Decision, Consequences, Perspectives Consulted

## Probe Documentation

- **Location:** `docs/probes/NNNN-title.md`
- **When:** Every safe-to-fail experiment in Complex domain
- **How:** Use `/probe [hypothesis]` to create a probe document
- **Required fields:** Hypothesis, Success Criteria, Failure Criteria, Dampening Strategy, Timeline, Results, Learnings
- **Status lifecycle:** Planned → Running → Completed (Success/Failure/Inconclusive)

## Project Journal

- **Location:** `docs/project-journal.md`
- **When:** Every session, every significant event
- **Format:** Reverse chronological (newest first), with date, event description, Cynefin domain context, and references to decisions/probes
- **What to log:** Session starts/ends, decisions made, probes launched/completed, domain transitions, retrospectives, mob sessions

## Cynefin Map

- **Location:** `docs/cynefin-map.md`
- **When:** Updated whenever a topic is assessed, transitions between domains, or during retrospectives
- **Format:** Table with columns: Area, Domain, Last Assessed, Inflection Point, Next Step
- **Rule:** The map is the single source of truth for where each project area sits in the Cynefin framework

## Code Documentation

- **Architecture decisions** reference the relevant ADR number
- **Complex probe code** is clearly marked as experimental with the probe number
- **Comments explain WHY, not WHAT** — the Cynefin domain context is part of the "why"

## Review Triggers

- At every **inflection point** (Alpha, Beta, Delta, Gamma), review and update all relevant documentation
- At every **retrospective** (`/retro`), verify the Cynefin map is current
- When **onboarding** new perspectives or team members, the documentation should tell the full story
