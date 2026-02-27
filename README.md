# Cynefin Dynamics — Claude Code Environment

A `.claude` environment template that uses the [Cynefin Dynamics](https://cynefin.io/wiki/Cynefin_Dynamics) framework to guide digital product development — from early idea validation through to scaled production.

Every perspective (business, customer, design, development, data, cloud) is always present. Every decision is documented. Every experiment is tracked.

## What is this?

This is a **Claude Code project template** that provides structure, agents, skills, and rules for building digital products using the Cynefin sense-making framework. Instead of jumping straight to coding, the environment guides you through:

1. **Understanding where you are** — mapping each area of your project to a Cynefin domain
2. **Working the right way** — probing when uncertain, building when confident, automating when clear
3. **Hearing all perspectives** — mob-style collaboration with 6 specialist viewpoints
4. **Documenting everything** — decisions, experiments, and learnings are always recorded

## Quick Start

### Prerequisites

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) installed and configured

### Setup

1. Copy this repository (or the `.claude/` and `docs/` folders) into your project root
2. Open the project with Claude Code
3. Start with `/status` to see the empty Cynefin map
4. Use `/assess [your first topic]` to begin mapping your project

### First Session Example

```
You: /status
→ Shows an empty Cynefin map, ready to start

You: /assess core value proposition
→ Navigator evaluates the domain (likely Complex — still unvalidated)
→ Cynefin map is updated
→ Recommends next steps (probably /probe or /mob)

You: /mob should we build a B2B SaaS or a marketplace?
→ All 6 perspectives weigh in
→ Conflicts and consensus are surfaced
→ Action items generated

You: /probe users will pay €50/month for automated reporting
→ Designs a safe-to-fail experiment
→ Documented in docs/probes/

You: /decide use Next.js for frontend
→ Records an ADR in docs/decisions/
→ Includes context, alternatives, and consequences
```

## Commands

| Command | Purpose | When to Use |
|---------|---------|-------------|
| `/status` | Show Cynefin map and project overview | Start of every session |
| `/assess [topic]` | Evaluate which Cynefin domain a topic belongs to | Starting work on anything new |
| `/probe [hypothesis]` | Design a safe-to-fail experiment | In Complex domain — testing unknowns |
| `/validate [area]` | Check if a pattern is stable enough to transition | At inflection points (Alpha/Beta/Delta) |
| `/decide [title]` | Record a decision as an ADR | Any significant decision |
| `/mob [topic]` | Get all 6 perspectives on a topic | Major decisions, architecture, pivots |
| `/retro` | Retrospective — review progress and learnings | Regularly, or when feeling stuck |
| `/pivot [reason]` | Trigger radical rethinking (Red Line dynamic) | When current direction is fundamentally wrong |

## How It Works

### The Cynefin Domains

Your project areas move through domains as understanding grows:

```
┌─────────────────────────────┬─────────────────────────────┐
│                             │                             │
│   COMPLEX                   │   COMPLICATED               │
│   "We don't know yet"       │   "Experts can figure out"  │
│                             │                             │
│   → Run safe-to-fail probes │   → Build with expertise    │
│   → Multiple experiments    │   → Architecture decisions  │
│   → Embrace failure         │   → Governing constraints   │
│                             │                             │
│         ──── Alpha ────────►│                             │
│                             │                             │
├─ ─ ─ ─ APORIA ─ ─ ─ ─ ─ ─ ─┼─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ┤
│                             │                             │
│   CHAOTIC                   │   CLEAR                     │
│   "Nothing makes sense"     │   "We know exactly how"     │
│                             │                             │
│   → Act first, analyze later│   → Standardize & automate  │
│   → Radical rethinking      │   → CI/CD, IaC, runbooks    │
│                             │                             │
│                             │◄──── Delta ─────────────────│
│                             │                             │
└─────────────────────────────┴─────────────────────────────┘
```

### Three Dynamic Lines

- **Blue Line** — The standard maturation path: Complex → Complicated → Clear
- **Purple Line** — Continuous innovation cycle: Complex ↔ Aporetic (for areas that never stabilize)
- **Red Line** — Radical change: triggered when stability can't be confirmed, dives through Chaos back to Complex

### Inflection Points

| Point | Transition | Key Question |
|-------|-----------|--------------|
| **Alpha** | Complex → Complicated | Are probes producing consistent, repeatable results? |
| **Beta** | Complicated → Clear? | Has the solution stabilized? Any exceptions still appearing? |
| **Delta** | Complicated → Clear (commit) | Is this truly stable enough to standardize? High-cost commitment. |
| **Gamma** | Aporetic → Redistribution | How do we decompose, recompose, and find new possibilities? |

## Agents

### Domain Agents (How to Work)

| Agent | Domain | Role |
|-------|--------|------|
| `navigator` | Meta | Assesses Cynefin domain, orchestrates which agents/skills to use |
| `probe-runner` | Complex | Designs and runs safe-to-fail experiments |
| `pattern-validator` | Liminal (Alpha) | Validates whether patterns are genuinely repeatable |
| `solution-builder` | Complicated | Builds solutions with expert judgment |
| `standardizer` | Clear | Automates, standardizes, and hardens processes |
| `disruptor` | Aporetic/Chaotic | Radical rethinking in isolated worktree |

### Perspective Agents (What to Consider)

| Agent | Perspective |
|-------|------------|
| `business-strategist` | Value proposition, business model, market, revenue |
| `customer-advocate` | User needs, journeys, pain points, Jobs-to-be-Done |
| `designer` | UX/UI, service design, accessibility, prototyping |
| `developer` | Architecture, tech choices, code quality, feasibility |
| `data-specialist` | Data model, analytics, metrics, AI/ML, privacy |
| `cloud-infra` | Cloud services, infrastructure, scaling, security, cost |

## Project Structure

```
your-project/
├── .claude/
│   ├── CLAUDE.md              # Main instructions & Cynefin overview
│   ├── settings.json          # Project settings
│   ├── agents/                # 12 agent definitions
│   │   ├── navigator.md       #   Domain orchestrator
│   │   ├── probe-runner.md    #   Complex domain
│   │   ├── pattern-validator.md  # Alpha inflection
│   │   ├── solution-builder.md   # Complicated domain
│   │   ├── standardizer.md    #   Clear domain
│   │   ├── disruptor.md       #   Aporetic/Chaotic
│   │   ├── business-strategist.md
│   │   ├── customer-advocate.md
│   │   ├── designer.md
│   │   ├── developer.md
│   │   ├── data-specialist.md
│   │   └── cloud-infra.md
│   ├── skills/                # 8 slash commands
│   │   ├── assess/SKILL.md
│   │   ├── probe/SKILL.md
│   │   ├── validate/SKILL.md
│   │   ├── decide/SKILL.md
│   │   ├── mob/SKILL.md
│   │   ├── retro/SKILL.md
│   │   ├── pivot/SKILL.md
│   │   └── status/SKILL.md
│   └── rules/                 # 3 rule sets
│       ├── cynefin-principles.md
│       ├── documentation.md
│       └── mob-working.md
├── docs/
│   ├── cynefin-map.md         # Where each area sits (single source of truth)
│   ├── project-journal.md     # Chronological activity log
│   ├── decisions/             # Architecture Decision Records
│   │   └── 0000-template.md
│   └── probes/                # Safe-to-fail experiment docs
│       └── template.md
└── README.md
```

## Core Principles

1. **Never assume the domain.** Always `/assess` first. When in doubt, assume Complex.
2. **No building in Complex.** Only safe-to-fail probes. If the need isn't validated, you're in Complex.
3. **All perspectives matter.** Use `/mob` for significant decisions. Six viewpoints catch blind spots.
4. **Document everything.** If it's not in `docs/`, it didn't happen.
5. **Start with the need.** Every action must trace to a validated need. Needs can be hypotheses.
6. **Dynamics are natural.** Areas move between domains — including backwards. That's reality, not failure.

## Customization

This is a **generic template**. To adapt it for your project:

- **Add MCP servers** — Configure `.mcp.json` for GitHub, Figma, Slack, databases etc.
- **Adjust agent models** — Change `model:` in agent frontmatter (opus for deep thinking, sonnet for speed, haiku for quick tasks)
- **Add domain-specific rules** — Create new `.md` files in `.claude/rules/` for your coding standards, tech stack, etc.
- **Add skills** — Create new directories in `.claude/skills/` for project-specific workflows
- **Tune permissions** — Edit `.claude/settings.json` to match your security needs

## Further Reading

- [Cynefin Dynamics](https://cynefin.io/wiki/Cynefin_Dynamics) — The framework this environment is built on
- [Cynefin Framework](https://cynefin.io/wiki/Cynefin) — Overview of the Cynefin sense-making framework
- [Claude Code Documentation](https://docs.anthropic.com/en/docs/claude-code) — How to use Claude Code

## License

This template is provided as-is for use in your projects. The Cynefin framework is created by Dave Snowden and Cognitive Edge / The Cynefin Co.
