---
applyTo: "**"
---

# Cynefin Principles

These principles govern ALL work in this project. They are non-negotiable.

## Domain Awareness

- **Never assume the domain.** Always assess first using `/assess`. When in doubt, assume Complex.
- **The domain determines the method, not the other way around.** Don't pick Scrum/Kanban/etc. first — let the Cynefin domain guide the approach.
- **Different parts of the project can be in different domains simultaneously.** Authentication might be Clear while the core value proposition is still Complex.

## Complex Domain Rules

- **No final solutions in Complex.** Only safe-to-fail probes. If someone proposes building "the solution" and we're in Complex, push back.
- **Multiple parallel probes.** Never bet on a single experiment. Run 2-3 probes simultaneously to learn faster.
- **Failure is data.** A failed probe is not a problem — it narrows the solution space. Document what was learned.
- **Emergent practice.** Patterns emerge from probes. Don't impose patterns.

## Complicated Domain Rules

- **Expert analysis required.** Use perspective agents to get multi-disciplinary input before building.
- **Governing constraints.** Establish architecture decisions, API contracts, coding standards as you build.
- **Good practice, not best practice.** There may be multiple valid approaches. Choose with awareness, not dogma.

## Clear Domain Rules

- **Commitment is high-cost.** Moving to Clear means standardizing and automating. Reverting is expensive.
- **Delta check is mandatory.** Before committing to Clear, run `/validate` to confirm genuine stability.
- **Automate ruthlessly.** If it's truly Clear, it should be automated — CI/CD, IaC, monitoring, runbooks.

## Aporetic / Chaotic Rules

- **Radical rethinking, not panic.** A shallow dive into chaos is intentional and structured.
- **Decompose and recompose.** Break apart assumptions. Recombine in new ways.
- **Isolation is key.** Disruptive exploration happens in branches — never directly on main.
- **Exaptation welcome.** Repurposing existing components for entirely new uses is encouraged.

## Transition Rules

- **Alpha (Complex → Complicated):** Only cross when probes produce genuinely consistent, repeatable results. Verify with `/validate`.
- **Beta (Complicated → Clear or back to Complex):** Check for variations and exceptions. If found, cycle back to Complex.
- **Delta (Complicated → Clear or → Aporetic):** Final confirmation before commitment. If stability cannot be confirmed, trigger Red Line via `/pivot`.
- **Gamma (Aporetic → Redistribution):** Suspension point. Multiple outcomes possible. Use `/mob` to get all perspectives before choosing a direction.

## The Need Principle

- **Every action must trace to a validated need.** Before building, ask: "What need does this serve? How do we know it's real?"
- **Needs can be hypotheses.** In Complex, the need itself might be a hypothesis tested via probes.
- **Needs evolve.** What we thought the customer needed might change. Re-validate periodically.
