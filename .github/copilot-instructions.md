# Cynefin Dynamics — Digital Product Development Environment

> **Every feature, decision, and line of code starts with understanding where we are.**

This environment uses the [Cynefin Dynamics](https://cynefin.io/wiki/Cynefin_Dynamics) framework to guide digital product development from the earliest idea validation through to scaled production. It is designed for **mob-style collaboration** where business, customer, design, development, data, and cloud perspectives are always present.

## Core Philosophy

1. **Start with the need.** Never build before the need is validated. Every action must trace back to a real need.
2. **Know where you are.** Every topic/area is mapped to a Cynefin domain. The domain determines HOW you work, not WHAT you work on.
3. **Document everything.** Every decision is an ADR in `docs/decisions/`. Every experiment is logged in `docs/probes/`. The journal `docs/project-journal.md` tracks chronological progress.
4. **All perspectives matter.** No significant decision without hearing from business, customer, design, dev, data, and cloud viewpoints.
5. **Dynamics are natural.** Things move between domains. What was chaotic becomes complex, what was complex becomes complicated, and eventually clear. But regression happens too — and that's OK.

## Cynefin Domains

| Domain | Nature | How We Work | Constraints |
|--------|--------|-------------|-------------|
| **Chaotic / Aporetic** | No cause-effect visible, confusion | Act-sense-respond. Radical rethinking. | None / novel |
| **Complex** | Cause-effect only visible in retrospect | Probe-sense-respond. Safe-to-fail experiments. | Enabling |
| **Complicated** | Cause-effect analyzable by experts | Sense-analyze-respond. Build with expertise. | Governing |
| **Clear** | Cause-effect obvious | Sense-categorize-respond. Standardize & automate. | Fixed |
| **Liminal** | Transition zone between domains | Validate stability, check inflection points. | Mixed |

## Dynamic Lines

- **Blue Line:** Complex → (Alpha) → Complicated → (Beta/Delta) → Clear. Standard maturation path.
- **Purple Line:** Continuous Complex ↔ Aporetic cycling. Innovation, fluid situations.
- **Red Line:** Triggered at Delta when stability cannot be confirmed. Shallow dive into Chaos, then back to Complex.

## Inflection Points

| Point | Transition | Key Question |
|-------|-----------|--------------|
| **Alpha** | Complex → Complicated | Is genuine repeatability achieved? |
| **Beta** | Complicated → Clear? | Has the situation continued to stabilize? |
| **Delta** | Complicated → Clear (commit) or → Aporetic | Is stability truly confirmed? High-commitment. |
| **Gamma** | Aporetic → Redistribution | How to decompose, recompose, and exapt? |

## Working With This Environment

### Starting a Session

1. Read current state: `docs/cynefin-map.md`
2. Check recent activity: `docs/project-journal.md`
3. Use `/assess` to evaluate where new topics belong
4. Use `/status` to get an overview of the entire project

### Skills (Slash Commands)

| Command | Purpose | When to Use |
|---------|---------|-------------|
| `/assess [topic]` | Evaluate Cynefin domain | Starting work on anything new |
| `/probe [hypothesis]` | Design safe-to-fail experiment | In Complex domain |
| `/validate [area]` | Check transition readiness | At inflection points |
| `/decide [title]` | Record decision as ADR | Any significant decision |
| `/mob [topic]` | All 6 perspectives weigh in | Major decisions |
| `/retro` | Retrospective | Regularly, or when stuck |
| `/pivot [reason]` | Trigger Red Line dynamic | When direction is fundamentally wrong |
| `/status` | Show project overview | Start of session |

### Agent Handoff Workflow

This environment uses **agent handoffs** to guide you through the appropriate workflow:

1. **Start with `@navigator`** — assesses the Cynefin domain and hands off to the right agent
2. **Domain agents** do the work — `@probe-runner`, `@solution-builder`, `@standardizer`, `@disruptor`
3. **`@pattern-validator`** operates at inflection points between domains
4. **`@mob-facilitator`** orchestrates all-perspective mob sessions
5. **Perspective agents** provide specialized viewpoints — `@business-strategist`, `@customer-advocate`, `@designer`, `@developer`, `@data-specialist`, `@cloud-infra`

Agents will offer handoff buttons to guide transitions naturally.

## Anti-Patterns to Avoid

- **Premature building** — Jumping to Complicated/Clear work when still in Complex
- **Skipping perspectives** — Making decisions without diverse input
- **Undocumented decisions** — If it's not in `docs/decisions/`, it didn't happen
- **Forcing stability** — The Purple Line (grazing) is a valid mode for innovation
- **Ignoring regression** — Things can move backwards. That's reality, not failure.

## Project Structure

```
docs/
├── decisions/          # Architecture Decision Records (ADRs)
├── probes/             # Safe-to-fail experiment documentation
├── cynefin-map.md      # Current Cynefin domain mapping (single source of truth)
└── project-journal.md  # Chronological log of all activity
```
