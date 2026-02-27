---
name: retro
description: Conduct a retrospective — review the Cynefin map, assess progress, identify domain transitions, and surface what has been learned. Use regularly and when feeling stuck.
---

# Retrospective

Conduct a project retrospective.

## Instructions

### 1. Gather Full Context

Read ALL of these:
- `docs/cynefin-map.md` — current domain mapping
- `docs/project-journal.md` — full activity history
- `docs/decisions/` — all ADRs (scan titles and statuses)
- `docs/probes/` — all probes (scan titles and statuses)

### 2. Assess Each Area on the Cynefin Map

For every area listed in `docs/cynefin-map.md`:

- **Has the domain changed?** Based on recent probes and decisions, should this area be reassigned?
- **Is an inflection point near?** Alpha, Beta, Delta, or Gamma?
- **Are there stalled areas?** Areas with no recent activity or progress?
- **Are there regression signals?** Areas that might be moving back from Complicated to Complex?

### 3. Review the Dynamics

**Blue Line (Progressing to Stability):**
- Which areas are on the Blue Line path?
- What's next on the path for each?

**Purple Line (Grazing Dynamic):**
- Are any areas in a continuous Complex ↔ Aporetic cycle?
- Is this expected (innovation) or concerning (inability to stabilize)?

**Red Line (Radical Change):**
- Are there areas where a Delta check has failed or is likely to fail?
- Should `/pivot` be triggered for any area?

### 4. Review Probes

- **Open probes:** Which are still running? Are they on schedule?
- **Completed probes:** Have learnings been applied? Are follow-up actions taken?
- **Probe patterns:** Are we probing the right things? Are probes producing useful learning?

### 5. Review Decisions

- **Recent ADRs:** Are they being followed? Any that need to be revisited?
- **Superseded decisions:** Are there decisions that should be superseded based on new learning?
- **Missing decisions:** Are there de facto decisions that haven't been recorded?

### 6. Meta-Assessment

- **What have we learned?** Biggest insights since last retro
- **What surprised us?** Unexpected findings or outcomes
- **What are we avoiding?** Hard questions or areas we're not addressing
- **What needs attention?** Urgent items or areas at risk

### 7. Update and Recommend

- Update `docs/cynefin-map.md` with any domain changes
- Log the retrospective in `docs/project-journal.md`
- Recommend specific next actions

## Output Format

```markdown
## Retrospective: [Date]

### Cynefin Map Changes
| Area | Previous Domain | Current Domain | Reason |
|------|----------------|----------------|--------|
| [Area] | [Domain] | [Domain] | [Why] |

### Dynamic Lines Active
- **Blue Line:** [Areas progressing toward stability]
- **Purple Line:** [Areas in innovation/grazing cycle]
- **Red Line:** [Areas needing radical rethinking]

### Probe Status
| Probe | Status | Key Learning |
|-------|--------|-------------|
| [Probe] | [Running/Completed/Stalled] | [Learning] |

### Decision Review
- **On track:** [ADRs being followed]
- **Needs revisiting:** [ADRs that may be out of date]
- **Missing:** [Decisions not yet recorded]

### Key Insights
1. [Insight 1]
2. [Insight 2]
3. [Insight 3]

### What We're Avoiding
- [Hard question or area we haven't addressed]

### Recommended Actions
| # | Action | Priority | Skill |
|---|--------|----------|-------|
| 1 | [Action] | [High/Med/Low] | [/assess, /probe, /validate, /decide, /mob, /pivot] |
```
