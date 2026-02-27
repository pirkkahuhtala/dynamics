# Cynefin Dynamics — Digital Product Development Environment

> **Every feature, decision, and line of code starts with understanding where we are.**

This environment uses the [Cynefin Dynamics](https://cynefin.io/wiki/Cynefin_Dynamics) framework to guide digital product development from the earliest idea validation through to scaled production. It is designed for **mob-style collaboration** where business, customer, design, development, data, and cloud perspectives are always present.

## Core Philosophy

1. **Start with the need.** Never build before the need is validated. Every action must trace back to a real need.
2. **Know where you are.** Every topic/area is mapped to a Cynefin domain. The domain determines HOW you work, not WHAT you work on.
3. **Document everything.** Every decision is an ADR in `docs/decisions/`. Every experiment is logged in `docs/probes/`. The journal `docs/project-journal.md` tracks chronological progress.
4. **All perspectives matter.** No significant decision without hearing from business, customer, design, dev, data, and cloud viewpoints.
5. **Dynamics are natural.** Things move between domains. What was chaotic becomes complex, what was complex becomes complicated, and eventually clear. But regression happens too — and that's OK.

## Cynefin Dynamics Overview

### Domains

| Domain | Nature | How We Work | Constraints |
|--------|--------|-------------|-------------|
| **Chaotic / Aporetic** | No cause-effect visible, confusion | Act-sense-respond. Radical rethinking. Decompose & recompose. | None / novel |
| **Complex** | Cause-effect only visible in retrospect | Probe-sense-respond. Multiple safe-to-fail experiments. | Enabling constraints |
| **Complicated** | Cause-effect analyzable by experts | Sense-analyze-respond. Build with expertise. | Governing constraints |
| **Clear** | Cause-effect obvious | Sense-categorize-respond. Standardize & automate. | Fixed constraints |
| **Liminal** | Transition zone between domains | Validate stability, check inflection points. | Mixed |

### Dynamic Lines

- **Blue Line (Progressing to Stability):** Complex → (Alpha) → Complicated → (Beta/Delta) → Clear. The standard maturation path.
- **Purple Line (Grazing Dynamic):** Continuous Complex ↔ Aporetic cycling. For innovation, early startups, fluid situations that never stabilize.
- **Red Line (Radical Change):** Triggered at Delta when stability cannot be confirmed. Shallow dive into Chaos via Aporia, then back to Complex.

### Inflection Points

| Point | Transition | Key Question |
|-------|-----------|--------------|
| **Alpha** | Complex → Complicated | Is genuine repeatability & certainty achieved? Are probes producing consistent results? |
| **Beta** | Complicated → Clear (or back to Complex) | Has the situation continued to stabilize? Are there exceptions and variations emerging? |
| **Delta** | Complicated → Clear (commitment) or → Aporetic (radical rethink) | Is stability truly confirmed? This is a high-commitment move — can we afford to be wrong? |
| **Gamma** | Aporetic → Redistribution | How should we decompose, recompose, and exapt? What radical new possibilities exist? |

## Working With This Environment

### Starting a Session

1. Always read the current state: @docs/cynefin-map.md
2. Check recent activity: @docs/project-journal.md
3. Use `/assess` to evaluate where new topics belong on the Cynefin map
4. Use `/status` to get an overview of the entire project

### Key Commands

| Command | Purpose | When to Use |
|---------|---------|-------------|
| `/assess [topic]` | Evaluate Cynefin domain for a topic | Starting work on anything new |
| `/probe [hypothesis]` | Design a safe-to-fail experiment | In Complex domain — testing unknowns |
| `/validate [area]` | Check if pattern is stable enough to transition | At Alpha/Beta/Delta inflection points |
| `/decide [title]` | Record a decision as ADR | Any significant decision |
| `/mob [topic]` | Get all 6 perspectives on a topic | Major decisions, design reviews, architecture |
| `/retro` | Retrospective — where are we, what did we learn | End of sprint/cycle, when feeling stuck |
| `/pivot [reason]` | Trigger radical rethinking (Red Line) | When Delta check fails, things aren't working |
| `/status` | Show project Cynefin map and current state | Start of session, orientation |

### Domain-Specific Agents

The Navigator agent (`navigator`) orchestrates work by assessing the Cynefin domain and recommending the right agent:

- **Complex domain** → `probe-runner` — designs and runs safe-to-fail experiments
- **Liminal (Alpha)** → `pattern-validator` — checks if patterns are genuinely repeatable
- **Complicated domain** → `solution-builder` — builds solutions with expertise
- **Clear domain** → `standardizer` — automates, documents, hardens processes
- **Aporetic/Chaotic** → `disruptor` — radical rethinking in isolated worktree

### Perspective Agents

Six perspectives always available for mob-style consultation:

- `business-strategist` — Value proposition, business model, market, revenue
- `customer-advocate` — User needs, journeys, pain points, Jobs-to-be-Done
- `designer` — UX/UI, service design, accessibility, prototyping
- `developer` — Architecture, tech choices, code quality, feasibility
- `data-specialist` — Data model, analytics, metrics, AI/ML, privacy
- `cloud-infra` — Cloud services, infrastructure, scaling, security, cost, DevOps

### Rules

- @.claude/rules/cynefin-principles.md — Core Cynefin rules that govern all work
- @.claude/rules/documentation.md — What must be documented and where
- @.claude/rules/mob-working.md — How mob-style collaboration works

## Anti-Patterns to Avoid

- **Premature building** — Jumping to Complicated/Clear work when still in Complex. If you haven't validated the need, you're in Complex.
- **Skipping perspectives** — Making technical decisions without business/customer input, or business decisions without technical feasibility check.
- **Undocumented decisions** — If it's not in `docs/decisions/`, it didn't happen.
- **Forcing stability** — Not everything will stabilize. The Purple Line (grazing) is a valid operating mode for innovation.
- **Ignoring regression** — Things that were Complicated can become Complex again. That's not failure, it's reality.

## Project Structure

```
docs/
├── decisions/          # Architecture Decision Records (ADRs)
├── probes/             # Safe-to-fail experiment documentation
├── cynefin-map.md      # Current Cynefin domain mapping for all areas
└── project-journal.md  # Chronological log of all activity
```
