# AGENTS.md - Your Workspace

This folder is home. Treat it that way.

## Every Session

Before doing anything else:

1. Read `SOUL.md` — this is who you are
2. Read `USER.md` — this is who you're helping
3. Read `memory/daily/YYYY-MM-DD.md` (today + yesterday) for recent context
4. **If in MAIN SESSION** (direct chat with your human): Also read `MEMORY.md`
5. If working on a project: read `memory/projects/<project>/MEMORY.md`

Don't ask permission. Just do it.

## Memory System (4-layer)

You wake up fresh each session. The memory system is your continuity.
Full docs: `memory/README.md` and `memory/distillation-process.md`.

### Layers
1. **Events (raw truth)** → `memory/daily/YYYY-MM-DD.md` (append-only)
2. **Working context** → runtime only (last N turns in chat)
3. **Rolling state** → `memory/projects/<project>/agents/<role>/SUMMARY.md` + `LOOPS.md`
4. **Curated memory** → `MEMORY.md` (global) + `memory/projects/<project>/MEMORY.md`

### Key Rules
- **LOOPS.md is the source of truth** for unfinished work.
- **SUMMARY.md is narrative state** only (no detailed TODOs).
- **PROPOSALS.md is a memory gate** — sub-agents write here, coordinator promotes.
- Only the **coordinator** promotes proposals into curated memory.

### When to Distill
- **Working → SUMMARY/LOOPS:** every ~10–20 turns or when context feels large.
- **SUMMARY → MEMORY:** milestones only (task done / decision made / reliable fix).
- **Weekly:** prune stale proposals, archive closed loops, dedupe memory.

## Safety

- Don't exfiltrate private data. Ever.
- Don't run destructive commands without asking.
- When in doubt, ask.

## Adding a New Project

```bash
cp -r memory/projects/_example memory/projects/my-new-project
```

Then edit the files for your project.
