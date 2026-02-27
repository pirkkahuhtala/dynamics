---
name: decide
description: Record a decision as an Architecture Decision Record (ADR) in docs/decisions/. Every significant decision must be captured for future reference.
argument-hint: "decision title"
---

# Record Decision (ADR)

Record decision: **$ARGUMENTS**

## Instructions

1. **Read context:**
   - Read `docs/cynefin-map.md` — identify the Cynefin domain for this decision
   - Read `docs/decisions/` — check existing decisions for related ADRs
   - Read `docs/project-journal.md` for recent context

2. **Determine the next ADR number:**
   - Check existing files in `docs/decisions/`
   - Next sequential number, zero-padded to 4 digits
   - Format: `NNNN-descriptive-title.md`

3. **Gather decision context:**
   - What triggered this decision?
   - What alternatives were considered?
   - What perspectives were consulted? (Reference mob sessions if applicable)
   - What probes informed this decision?
   - What are the consequences (positive and negative)?

4. **Create the ADR** at `docs/decisions/NNNN-title.md`

5. **Log in docs/project-journal.md**

## ADR Template

```markdown
# ADR NNNN: [Title]

**Date:** [Date]
**Status:** Proposed
**Cynefin Domain:** [Chaotic | Complex | Complicated | Clear]
**Deciders:** [Which agents/perspectives contributed]

## Context

[What is the situation that requires a decision? What forces are at play?
Reference relevant probes, mob sessions, and previous ADRs.]

## Decision

[What is the decision? State it clearly and unambiguously.]

## Alternatives Considered

### Alternative 1: [Name]
- **Pros:** [Advantages]
- **Cons:** [Disadvantages]
- **Why rejected:** [Reason]

### Alternative 2: [Name]
- **Pros:** [Advantages]
- **Cons:** [Disadvantages]
- **Why rejected:** [Reason]

## Consequences

### Positive
- [Positive consequence 1]
- [Positive consequence 2]

### Negative
- [Negative consequence 1]
- [Negative consequence 2]

### Risks
- [Risk 1 and mitigation]
- [Risk 2 and mitigation]

## Perspectives Consulted

| Perspective | Input | Concern |
|-------------|-------|---------|
| [Agent name] | [Summary of input] | [Key concern if any] |

## Related

- **Probes:** [Links to relevant probes]
- **Previous ADRs:** [Links to related decisions]
- **Cynefin map area:** [Which area this affects]

## Review Trigger

[When should this decision be revisited? What would indicate it needs to change?]
```

## ADR Status Lifecycle

- **Proposed** — Decision is written but not yet confirmed
- **Accepted** — Decision is confirmed and active
- **Superseded** — Replaced by a newer ADR (link to it)
- **Deprecated** — No longer relevant
- **Amended** — Modified (with amendment date and reason noted)

## Reminders

- **Be specific.** "We will use React" is better than "We will use a frontend framework"
- **Include alternatives.** Show that options were considered, not just the winner.
- **Note dissent.** If a perspective disagreed, record it. They may be right later.
- **Define review triggers.** No decision is permanent — state when to revisit.
- **Link everything.** ADRs don't exist in isolation — connect to probes, other ADRs, Cynefin map.
