# Mob Working Principles

This project uses **mob-style collaboration** where all relevant perspectives are present for significant decisions. This is not optional — it's how we ensure we don't build the wrong thing, the wrong way, for the wrong reasons.

## Core Principle

> No significant decision should be made from a single perspective. Business, customer, design, development, data, and cloud viewpoints must all be heard.

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
2. **Each perspective agent comments** from their viewpoint:
   - Business Strategist: value, market, revenue implications
   - Customer Advocate: user needs, experience, adoption
   - Designer: usability, accessibility, service design
   - Developer: feasibility, architecture, technical debt
   - Data Specialist: data implications, metrics, privacy
   - Cloud/Infra: infrastructure, scaling, security, cost
3. **Conflicts are surfaced explicitly** — disagreements are valuable signals, not problems
4. **Synthesis** — common ground, open questions, and recommended next steps
5. **Action items** — probes to run, decisions to record, follow-ups needed

## Conflict Resolution

- **Conflicts in Complex domain:** Run probes to test competing hypotheses. Don't resolve by opinion.
- **Conflicts in Complicated domain:** Defer to the most relevant expert perspective, but document dissent.
- **Conflicts about domain placement:** Navigator agent has final say, but must justify the assessment.
- **Persistent conflicts:** Escalate to `/retro` for deeper analysis. Consider if the conflict signals we're in the wrong domain.

## Perspective Rotation

- Not every perspective will have strong input on every topic. That's fine.
- A perspective saying "no concerns from my viewpoint" is still valuable — it means that angle has been considered.
- If a perspective consistently has nothing to add, consider whether we're asking the right questions.

## Documentation

- Every mob session's output is summarized and logged in `docs/project-journal.md`
- Decisions arising from mob sessions reference the mob session in the ADR context
- Dissenting views are recorded — they may prove prescient later
