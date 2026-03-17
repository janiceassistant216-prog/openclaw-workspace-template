# memory/ — Context & Memory System

This folder is the structured memory system (human-readable, sub-agent ready).

## Layers (4)

1) **Events (raw truth)** → `daily/`
2) **Working context (ephemeral)** → runtime only (chat history)
3) **Rolling state** → `projects/*/agents/*/SUMMARY.md` + `LOOPS.md`
4) **Long-term curated memory** → global `../MEMORY.md` + per-project `projects/*/MEMORY.md`

## Roles & write permissions

- **Coordinator (main agent):** may promote items into long-term memory.
- **Sub-agents:** must only write suggestions into project-level `PROPOSALS.md` (memory gate).

## Distillation triggers

- **Working → SUMMARY/LOOPS:** when context gets big (token budget) or every ~10–20 turns.
- **SUMMARY/LOOPS → MEMORY (promotion):** *milestones only* (task done / decision made / reliable fix).
- **Weekly hygiene:** dedupe, expire stale, reconfirm critical facts.

## Files

- `daily/YYYY-MM-DD.md` — append-only log; not injected by default.
- `projects/<project>/MEMORY.md` — curated project memory.
- `projects/<project>/RUNBOOK.md` — operational procedures.
- `projects/<project>/PROPOSALS.md` — candidates to promote.
- `projects/<project>/agents/<role>/{SUMMARY,LOOPS}.md` — role state.
- `projects/<project>/agents/coordinator/PROPOSALS.md` — memory gate (coordinator only).
