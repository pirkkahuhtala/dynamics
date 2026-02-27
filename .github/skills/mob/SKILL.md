---
name: mob
description: Run a mob session with core perspectives (business, customer, architect) always present and optional perspectives invited based on topic relevance. Surfaces conflicts, common ground, and recommends next steps.
argument-hint: "topic for mob evaluation"
---

# Mob Session

Convene perspectives on: **$ARGUMENTS**

## Instructions

You are facilitating a **mob session** with a flexible perspective model. Three core perspectives are always present, and optional perspectives are invited based on topic relevance.

### 1. Set the Stage

Read context:
- `docs/cynefin-map.md` — current domain mapping
- `docs/project-journal.md` — recent activity
- Relevant `docs/decisions/` and `docs/probes/`

Present the topic with current context to all perspectives.

### 2. Select Perspectives

**Always include** the three core perspectives: Business Strategist, Customer Advocate, Architect.

**Evaluate** which optional perspectives are relevant to the topic. State explicitly which optional perspectives you are including and why.

### 3. Gather Perspectives

For each selected perspective, provide an assessment **in their voice**:

**Core (always present):**
1. **Business Strategist** — Value proposition, revenue, market, competitive advantage
2. **Customer Advocate** — User needs, journeys, pain points, adoption
3. **Architect** — System design, technology strategy, integration, NFRs

**Optional (when relevant):**
4. **Developer** — Implementation feasibility, code quality, testing
   - *Invite when:* Building, coding, implementation planning
5. **Designer** — UX/UI, service design, usability
   - *Invite when:* User interfaces, interaction patterns, content, visual design
6. **Data Specialist** — Data model, analytics, metrics, privacy, AI/ML
   - *Invite when:* Data flows, analytics, AI/ML features, data governance
7. **Cloud & Infra** — Infrastructure, scaling, cost, DevOps
   - *Invite when:* Deployment, infrastructure, scaling, cloud services
8. **Security Specialist** — Threats, auth, data protection, compliance
   - *Invite when:* Authentication, sensitive data, external integrations, compliance
9. **Accessibility Specialist** — WCAG, assistive tech, inclusive design
   - *Invite when:* UI components, forms, navigation, content, public-facing features

Each perspective should:
- State their assessment clearly
- Identify their key concern
- Give a recommendation (Support / Modify / Challenge)

### 4. Synthesize

After all selected perspectives have spoken:

**Consensus areas** — Where do all or most perspectives agree?
**Conflicts** — Where do perspectives disagree? These are critical signals.
**Blind spots** — What hasn't been addressed? What question hasn't been asked?
**Open questions** — What do we need to learn before deciding?

### 5. Recommend Actions

Based on the mob session, recommend:
- **Decisions to record** via `/decide`
- **Probes to run** via `/probe` (especially for conflicts that can't be resolved by opinion)
- **Domain assessments needed** via `/assess`
- **Follow-up mob sessions** for deeper dives on specific aspects

### 6. Document

Log the mob session in `docs/project-journal.md` with:
- Topic discussed
- Key perspectives and conflicts
- Decisions and action items

## Output Format

```markdown
## Mob Session: [Topic]

**Date:** [Date]
**Cynefin context:** [Which domain(s) this relates to]
**Perspectives included:** [List all perspectives in this session]
**Optional perspectives rationale:** [Why each optional perspective was or wasn't included]

---

### Core Perspectives

#### Business Strategist
[Assessment, key concern, recommendation]

#### Customer Advocate
[Assessment, key concern, recommendation]

#### Architect
[Assessment, key concern, recommendation]

### Optional Perspectives

_Include sections only for the perspectives invited to this session._

#### Developer
[Assessment, key concern, recommendation]

#### Designer
[Assessment, key concern, recommendation]

#### Data Specialist
[Assessment, key concern, recommendation]

#### Cloud & Infrastructure
[Assessment, key concern, recommendation]

#### Security Specialist
[Assessment, key concern, recommendation]

#### Accessibility Specialist
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
