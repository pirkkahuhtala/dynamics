---
name: pivot
description: Trigger the Red Line dynamic — radical rethinking when stability cannot be confirmed or the current direction is fundamentally wrong. Passes through Aporia and optionally a shallow dive into Chaos.
allowed-tools: Read, Glob, Grep, Write, Edit
argument-hint: "reason for pivot or area to rethink"
---

# Pivot — Red Line Dynamic

Trigger radical rethinking for: **$ARGUMENTS**

## Instructions

This skill triggers the **Red Line dynamic** from Cynefin Dynamics. This is a significant action — it means the current direction for an area cannot continue and needs fundamental rethinking.

### 1. Confirm the Need

Read context:
- `docs/cynefin-map.md` — current state
- `docs/project-journal.md` — history leading to this point
- Relevant `docs/decisions/` and `docs/probes/`

Verify that pivot is justified:
- Has a `/validate` (Delta check) failed?
- Is the current approach fundamentally blocked?
- Have repeated probes failed to produce stable patterns?
- Have external circumstances changed radically?

**If the situation can be addressed with more probes or iteration, recommend that instead.** Pivot is a last resort, not a first response.

### 2. Document the Trigger

Record why the pivot is happening:
- What was tried?
- What evidence shows it's not working?
- What are we giving up?
- What constraints remain (invariants)?

### 3. Invoke the Disruptor

Delegate to the `disruptor` agent for the full Aporia → Decomposition → Recomposition → Chaos Dive → Emergence cycle.

The disruptor will:
1. Challenge all assumptions
2. Decompose the current approach
3. Recompose in new ways (including exaptation)
4. Generate 3+ new directions
5. Recommend which to explore

### 4. Run a Mob Session

After the disruptor produces new directions, invoke `/mob` to evaluate them from all perspectives. This is mandatory — radical changes need maximum diverse input.

### 5. Record and Update

- Create an ADR via `/decide` recording the pivot decision
- Update `docs/cynefin-map.md` — affected areas return to Complex
- Log in `docs/project-journal.md` — mark this as a Red Line event
- Design new probes via `/probe` for the chosen new direction

## Output Format

```markdown
## Pivot Event: [Title]

**Date:** [Date]
**Trigger:** [What caused this pivot]
**Affected areas:** [Which Cynefin map areas are affected]

### Why Pivot?
[Evidence that the current direction cannot continue]

### What We're Leaving Behind
[What approaches/decisions are being abandoned]

### Invariants (What Must Remain True)
[Constraints that survive the pivot]

### Disruptor Analysis
[Summary of new directions generated — see full disruption report]

### Mob Session Results
[Summary of all-perspective evaluation — see full mob report]

### New Direction
[The chosen path forward]

### Immediate Next Steps
1. [First probe to design]
2. [Second probe to design]
3. [Other actions]

### Cynefin Map Updates
| Area | Previous Domain | New Domain | Reason |
|------|----------------|------------|--------|
| [Area] | [Domain] | Complex | Pivot — returning to probing |
```

## Safety Rails

- **Pivot affects the Cynefin map.** Areas involved in pivot ALWAYS return to Complex.
- **Nothing is permanently lost.** Previous approaches are documented. We can return to them.
- **Multiple new directions.** The disruptor generates options. We don't commit to one immediately.
- **Probes first.** After pivot, we probe the new direction. We don't build.
- **Mob validates.** All perspectives must weigh in on new directions.
