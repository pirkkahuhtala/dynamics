---
name: validate
description: Check whether a pattern or area is stable enough to transition between Cynefin domains. Operates at Alpha, Beta, and Delta inflection points.
argument-hint: "area or pattern to validate"
---

# Validate Domain Transition

Validate transition readiness for: **$ARGUMENTS**

## Instructions

1. **Read context:**
   - Read `docs/cynefin-map.md` — identify current domain for this area
   - Read ALL probes in `docs/probes/` related to this area
   - Read relevant `docs/decisions/` for constraints and history
   - Read `docs/project-journal.md` for recent activity

2. **Determine which inflection point** is being evaluated:

### Alpha (Complex → Complicated)
Ask:
- Do we have **3+ probes** with consistent results for this area?
- Were the probes **independent** (different approaches testing the same hypothesis)?
- Can we now **explain the cause-and-effect** (not just observe the outcome)?
- Are results **repeatable** — would running the probe again produce the same result?
- Check for **disconfirming evidence** — any probes that contradicted the pattern?

### Beta (Complicated → Clear, or back to Complex)
Ask:
- Has the solution been **stable for a meaningful period**?
- Are there **exceptions or variations** still appearing?
- Have **edge cases** been handled?
- Is the solution **well-understood** by everyone, not just original builders?
- Could this be operated by someone **without deep expertise**?

### Delta (Complicated → Clear, commitment decision)
Ask:
- Everything from Beta, PLUS:
- Are we **confident enough to standardize and automate**?
- Do we understand the **cost of reverting** if we're wrong?
- Is the apparent stability **genuine, or maintained by informal workarounds**?
- Have we consulted **all relevant perspectives**?
- Is there a **business justification** for the commitment to standardization?

3. **Produce a validation report** with clear verdict

4. **Update docs/cynefin-map.md** if a transition is recommended

5. **Log in docs/project-journal.md**

## Output Format

```
## Validation Report: [Area/Pattern]

**Current domain:** [Complex / Complicated]
**Inflection point:** [Alpha / Beta / Delta]
**Date:** [Date]

### Evidence Reviewed
| Source | Finding | Supports Transition? |
|--------|---------|---------------------|
| [Probe/Decision/Observation] | [Summary] | [Yes/No/Partial] |

### Consistency Analysis
[Are results consistent across multiple sources?]

### Stability Analysis
[Have results held over time and different conditions?]

### Risk Analysis
[What could go wrong if we transition prematurely?]
[What's the cost of being wrong?]

### Disconfirming Evidence
[Actively sought evidence against transition]

### Verdict: [TRANSITION / STAY / RETHINK]

**Confidence:** [High / Medium / Low]
**Justification:** [Clear reasoning]

### If TRANSITION:
- Recommended domain: [Complicated / Clear]
- First actions in new domain: [What to do first]
- Governing constraints to establish: [What rules/standards to set]
- Record decision via `/decide`

### If STAY:
- What's missing: [What additional evidence is needed]
- Recommended probes: [Specific experiments to run]
- Re-evaluate when: [Trigger for next validation]

### If RETHINK:
- Why: [What's fundamentally wrong]
- Consider: `/pivot` for radical rethinking
- Or: `/mob` for fresh perspectives
```
