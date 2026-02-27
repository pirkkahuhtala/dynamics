---
name: probe
description: Design a safe-to-fail experiment for testing hypotheses in the Complex domain. Creates a probe document in docs/probes/.
argument-hint: "hypothesis to test"
---

# Design Safe-to-Fail Probe

Design a safe-to-fail experiment to test: **$ARGUMENTS**

## Instructions

1. **Read context:**
   - Read `docs/cynefin-map.md` — confirm the area is in Complex domain
   - Read `docs/probes/` — check existing probes to avoid duplication and build on learnings
   - Read relevant `docs/decisions/` for constraints

2. **If the area is NOT in Complex domain**, warn and suggest the appropriate skill instead:
   - Complicated → suggest `/decide` or building with `@solution-builder`
   - Clear → suggest `/decide` or automation with `@standardizer`
   - If domain hasn't been assessed → suggest `/assess` first

3. **Design the probe** with ALL of these elements:

   - **Hypothesis:** State clearly what we believe to be true
   - **Success criteria:** Specific, observable, measurable outcomes that would confirm the hypothesis
   - **Failure criteria:** Specific outcomes that would disprove it (equally important!)
   - **Dampening strategy:** How to stop/reverse the experiment if it goes wrong
   - **Timeline:** How long to run (keep it short — days, not months)
   - **Effort:** Keep it minimal — this is a probe, not a product
   - **Approach:** Concrete steps to execute the probe
   - **Metrics:** What to measure during and after

4. **Determine the probe number:**
   - Check existing files in `docs/probes/` to find the next sequential number
   - Format: `NNNN-descriptive-title.md` (e.g., `0001-user-signup-speed.md`)

5. **Create the probe document** at `docs/probes/NNNN-title.md`

6. **Log in docs/project-journal.md** — Record that a new probe was designed

## Probe Document Template

```markdown
# Probe NNNN: [Title]

**Status:** Planned
**Date created:** [Date]
**Cynefin domain:** Complex
**Related area:** [Area on Cynefin map]
**Related probes:** [Links to related probes, if any]

## Hypothesis

[What we believe to be true. State it as a testable claim.]

## Success Criteria

- [ ] [Observable outcome 1]
- [ ] [Observable outcome 2]
- [ ] [Observable outcome 3]

## Failure Criteria

- [ ] [What would disprove the hypothesis]
- [ ] [What would indicate we should stop]

## Dampening Strategy

[How to stop or reverse this experiment if it goes wrong or is taking too long]

## Timeline

- **Start:** [Date]
- **Evaluate by:** [Date]
- **Maximum duration:** [Duration]

## Effort

[Estimated effort — keep it small]

## Approach

1. [Step 1]
2. [Step 2]
3. [Step 3]

## Metrics

| Metric | Target | How to Measure |
|--------|--------|---------------|
| [Metric 1] | [Target] | [Method] |

## Results

_To be filled after probe completion_

**Status:** [Success / Failure / Inconclusive]

### Observations
- [What happened]

### Learnings
- [What we learned]

### Recommendation
- [ ] More probes needed (stay in Complex)
- [ ] Pattern emerging — consider `/validate` (Alpha inflection)
- [ ] Hypothesis disproved — new direction needed
- [ ] Consider `/mob` for fresh perspectives
```

## Reminders

- **Keep it small.** A probe should take hours to days, not weeks.
- **Multiple probes are better than one.** Design 2-3 probes testing related hypotheses.
- **Failure is success.** A disproven hypothesis eliminates a path — that's valuable.
- **Document everything.** Future decisions depend on probe results.
