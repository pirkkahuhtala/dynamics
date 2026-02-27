---
name: status
description: Show the current project status — Cynefin map, active probes, recent decisions, and recommended next actions. Use at the start of any session for orientation.
allowed-tools: Read, Glob, Grep
---

# Project Status

Display the current project status and Cynefin map.

## Instructions

### 1. Read Current State

Read the following files:
- `docs/cynefin-map.md` — the full Cynefin domain mapping
- `docs/project-journal.md` — last 10 entries
- `docs/probes/` — list all probes, note their statuses
- `docs/decisions/` — list all ADRs, note their statuses

### 2. Display the Cynefin Map

Present the map visually, organized by domain:

```
╔══════════════════════════════════════════════════════════════╗
║                     CYNEFIN MAP                              ║
╠══════════════════════════════════════════════════════════════╣
║                                                              ║
║  COMPLEX (probe)          │  COMPLICATED (build)             ║
║  ─────────────────────    │  ──────────────────────          ║
║  • [Area 1]               │  • [Area 5]                      ║
║  • [Area 2]               │  • [Area 6]                      ║
║  • [Area 3]               │                                  ║
║                           │                                  ║
║ ─ ─ ─ ─ ─ APORIA ─ ─ ─ ─ ┼ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─    ║
║                           │                                  ║
║  CHAOTIC (act)            │  CLEAR (standardize)             ║
║  ─────────────────────    │  ──────────────────────          ║
║  • [Area 4]               │  • [Area 7]                      ║
║                           │                                  ║
╚══════════════════════════════════════════════════════════════╝
```

### 3. Show Active Dynamics

Identify which Cynefin dynamic lines are active:
- **Blue Line:** Areas progressing from Complex → Complicated → Clear
- **Purple Line:** Areas cycling Complex ↔ Aporetic (innovation/grazing)
- **Red Line:** Areas needing radical rethinking

### 4. Summarize Active Work

**Active Probes:**
| # | Probe | Status | Area | Due |
|---|-------|--------|------|-----|

**Recent Decisions:**
| # | ADR | Status | Domain | Date |
|---|-----|--------|--------|------|

### 5. Identify Inflection Points

Which areas are approaching an inflection point?
| Area | Current Domain | Inflection Point | Readiness |
|------|---------------|------------------|-----------|

### 6. Recommend Next Actions

Based on the current state, what should happen next?
- Areas needing assessment
- Probes ready for validation
- Decisions pending
- Areas that seem stalled

## Output

Present all of the above in a clear, scannable format. The status command is used for **quick orientation** — keep it concise but comprehensive. Highlight anything that needs immediate attention.

### Priority Flags

Use these markers for items needing attention:
- 🔴 **Urgent** — Blocking other work, needs immediate action
- 🟡 **Attention** — Approaching inflection point or deadline
- 🟢 **On track** — Progressing as expected
- ⚪ **Dormant** — No recent activity, may need reassessment
