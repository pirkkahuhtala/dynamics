---
applyTo: "**"
---

# Mob Working Principles

This project uses **mob-style collaboration** where all relevant perspectives are present for significant decisions. This is not optional — it's how we ensure we don't build the wrong thing, the wrong way, for the wrong reasons.

## Core Principle

> No significant decision should be made from a single perspective. Three core perspectives — business, customer, and architecture — must always be heard. Additional specialist perspectives are invited based on topic relevance.

## When to Mob

### Mandatory Mob (use `/mob`)
- **New feature/area assessment** — before any work begins
- **Architecture decisions** — before recording an ADR
- **Inflection point transitions** — Alpha, Beta, Delta, Gamma
- **Pivot/Red Line decisions** — before triggering `/pivot`
- **Business model changes** — any shift in value proposition, revenue, or market

### Recommended Mob
- **Probe design** — when designing safe-to-fail experiments
- **Sprint/cycle planning** — what to work on next
- **Retrospectives** — reflecting on progress and learnings

### Not Required
- **Implementation details** within established patterns (Complicated/Clear)
- **Bug fixes** in well-understood areas
- **Documentation updates** that don't change decisions

## How Mob Works

1. **Topic is presented** with current context (Cynefin domain, relevant decisions, recent probes)
2. **Core perspectives always comment** from their viewpoint:
   - Business Strategist: value, market, revenue implications
   - Customer Advocate: user needs, experience, adoption
   - Architect: system design, technology strategy, integration, non-functional requirements
3. **Optional perspectives are invited** based on topic relevance:
   - Developer: implementation feasibility, code quality, testing *(when building/coding)*
   - Designer: usability, service design *(when UI/UX is involved)*
   - Data Specialist: data implications, metrics, privacy *(when data flows are affected)*
   - Cloud/Infra: infrastructure, scaling, cost *(when deployment/ops is relevant)*
   - Security Specialist: threats, auth, data protection, compliance *(when security-sensitive)*
   - Accessibility Specialist: WCAG, assistive tech, inclusive design *(when UI/content is involved)*
4. **Conflicts are surfaced explicitly** — disagreements are valuable signals, not problems
5. **Synthesis** — common ground, open questions, and recommended next steps
6. **Action items** — probes to run, decisions to record, follow-ups needed

## Conflict Resolution

- **Conflicts in Complex domain:** Run probes to test competing hypotheses. Don't resolve by opinion.
- **Conflicts in Complicated domain:** Defer to the most relevant expert perspective, but document dissent.
- **Conflicts about domain placement:** Navigator agent has final say, but must justify the assessment.
- **Persistent conflicts:** Escalate to `/retro` for deeper analysis. Consider if the conflict signals we're in the wrong domain.

## Perspective Composition

- **Core perspectives (business, customer, architect) are always present.** Their input is required for every mob session.
- **Optional perspectives are selected by the Mob Facilitator** based on the topic. The rationale for inclusion or exclusion is documented.
- Not every optional perspective will be relevant to every topic. That's expected and efficient.
- An optional perspective saying "no concerns from my viewpoint" is still valuable — it means that angle has been considered.
- If a core perspective consistently has nothing to add, consider whether we're asking the right questions.

## Documentation

- Every mob session's output is summarized and logged in `docs/project-journal.md`
- Decisions arising from mob sessions reference the mob session in the ADR context
- Dissenting views are recorded — they may prove prescient later
