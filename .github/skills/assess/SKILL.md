---
name: assess
description: Evaluate which Cynefin domain a topic, feature, or project area belongs to. Updates the Cynefin map and recommends the appropriate working approach.
argument-hint: "topic or area to assess"
---

# Assess Cynefin Domain

Evaluate the Cynefin domain for: **$ARGUMENTS**

## Instructions

1. **Read current state:**
   - Read `docs/cynefin-map.md` for current domain mapping
   - Read `docs/project-journal.md` for recent context (last 10 entries)
   - Check `docs/decisions/` for relevant ADRs
   - Check `docs/probes/` for relevant experiment results

2. **Assess the domain** by answering these questions:

   **Evidence of clarity (Clear domain):**
   - Is cause-and-effect obvious and well-established?
   - Can this be handled by following standardized procedures?
   - Are there established best practices that directly apply?

   **Evidence of complication (Complicated domain):**
   - Is cause-and-effect analyzable but requires expert knowledge?
   - Are there known patterns that need expert judgment to apply?
   - Have probes/experiments confirmed repeatability?

   **Evidence of complexity (Complex domain):**
   - Is cause-and-effect only visible in retrospect?
   - Are there multiple plausible approaches with no clear winner?
   - Is the need itself still a hypothesis?
   - Do we lack validated data/evidence?

   **Evidence of chaos/aporia (Chaotic/Aporetic):**
   - Is there no visible cause-and-effect?
   - Is this completely novel with no comparable precedent?
   - Are current approaches fundamentally broken?

3. **Determine the domain** — When in doubt, default to Complex.

4. **Identify the nearest inflection point:**
   - Alpha (Complex → Complicated): What would confirm repeatability?
   - Beta (Complicated → Clear): What would confirm long-term stability?
   - Delta (Complicated → Clear commitment): Is this ready for standardization?
   - Gamma (Aporetic → Redistribution): What decomposition options exist?

5. **Recommend next steps:**
   - Which agent to use (@probe-runner, @pattern-validator, @solution-builder, @standardizer, @disruptor)
   - Which skill to invoke next (/probe, /validate, /decide, /mob, /pivot)
   - Which perspectives are most relevant

6. **Update docs/cynefin-map.md** — Add or update the row for this area

7. **Log in docs/project-journal.md** — Record the assessment

## Output Format

```
## Cynefin Assessment: [Topic]

**Domain:** [Chaotic | Complex | Liminal | Complicated | Clear]
**Confidence:** [High | Medium | Low]
**Date:** [Today's date]

### Justification
[Why this domain, with specific evidence]

### Nearest Inflection Point
[Which point, and what would trigger the transition]

### Recommended Approach
- **Agent:** [Which agent to use]
- **Next skill:** [Which skill to invoke]
- **Key perspectives:** [Which 2-3 perspective agents to consult first]

### Next Steps
1. [Specific action 1]
2. [Specific action 2]
3. [Specific action 3]
```
