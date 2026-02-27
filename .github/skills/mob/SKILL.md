---
name: mob
description: Run a mob session where all six perspective agents evaluate a topic from their viewpoint. Surfaces conflicts, common ground, and recommends next steps.
argument-hint: "topic for mob evaluation"
---

# Mob Session

Convene all perspectives on: **$ARGUMENTS**

## Instructions

You are facilitating a **mob session** where all six perspective agents evaluate the given topic. This is the core collaboration mechanism of this environment.

### 1. Set the Stage

Read context:
- `docs/cynefin-map.md` — current domain mapping
- `docs/project-journal.md` — recent activity
- Relevant `docs/decisions/` and `docs/probes/`

Present the topic with current context to all perspectives.

### 2. Gather Perspectives

For each of the six perspectives, provide an assessment **in their voice**:

1. **Business Strategist** — Value proposition, revenue, market, competitive advantage
2. **Customer Advocate** — User needs, journeys, pain points, adoption
3. **Designer** — UX/UI, service design, accessibility, usability
4. **Developer** — Architecture, feasibility, technical debt, implementation
5. **Data Specialist** — Data model, analytics, metrics, privacy, AI/ML
6. **Cloud & Infra** — Infrastructure, scaling, security, cost, DevOps

Each perspective should:
- State their assessment clearly
- Identify their key concern
- Give a recommendation (Support / Modify / Challenge)

### 3. Synthesize

After all perspectives have spoken:

**Consensus areas** — Where do all or most perspectives agree?
**Conflicts** — Where do perspectives disagree? These are critical signals.
**Blind spots** — What hasn't been addressed? What question hasn't been asked?
**Open questions** — What do we need to learn before deciding?

### 4. Recommend Actions

Based on the mob session, recommend:
- **Decisions to record** via `/decide`
- **Probes to run** via `/probe` (especially for conflicts that can't be resolved by opinion)
- **Domain assessments needed** via `/assess`
- **Follow-up mob sessions** for deeper dives on specific aspects

### 5. Document

Log the mob session in `docs/project-journal.md` with:
- Topic discussed
- Key perspectives and conflicts
- Decisions and action items

## Output Format

```markdown
## Mob Session: [Topic]

**Date:** [Date]
**Cynefin context:** [Which domain(s) this relates to]

---

### Business Strategist
[Assessment, key concern, recommendation]

### Customer Advocate
[Assessment, key concern, recommendation]

### Designer
[Assessment, key concern, recommendation]

### Developer
[Assessment, key concern, recommendation]

### Data Specialist
[Assessment, key concern, recommendation]

### Cloud & Infrastructure
[Assessment, key concern, recommendation]

---

### Synthesis

**Consensus:**
- [What most/all perspectives agree on]

**Conflicts:**
- [Perspective A vs Perspective B on topic X — why each side matters]

**Blind Spots:**
- [What hasn't been considered]

**Open Questions:**
- [What we need to learn]

### Recommended Actions

| # | Action | Type | Priority |
|---|--------|------|----------|
| 1 | [Action] | [/decide, /probe, /assess, /mob] | [High/Medium/Low] |
| 2 | [Action] | [...] | [...] |

### Conflicts Requiring Resolution
[For each conflict, recommend: probe it, escalate it, or accept one side with documented reasoning]
```

## Facilitation Principles

- **Every voice matters.** Even if a perspective has nothing to add, note it — it means that angle was considered.
- **Conflicts are valuable.** Don't smooth them over. They reveal complexity and risk.
- **Don't resolve by opinion.** If perspectives disagree, recommend a probe to generate evidence.
- **Keep it focused.** One topic per mob session. Deep, not wide.
- **Be honest about uncertainty.** "We don't know" is a valid and important finding.
