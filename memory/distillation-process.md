# Distillation Process

## Goal
Keep prompts small, memory clean, and never lose important context.

## Key Rules
- **LOOPS.md** is the source of truth for unfinished work.
- **SUMMARY.md** is narrative state (no detailed TODO lists).
- **PROPOSALS.md** is a gate between operational state and curated memory.

## Promotion Checklist (milestones only)

When a task is completed (bug fixed, deploy done, workflow decided):

1. Add a short note to `memory/daily/YYYY-MM-DD.md` under **Decisions made today**.
2. Add candidate memory items to the project coordinator proposals:
   - `memory/projects/<project>/agents/coordinator/PROPOSALS.md`
   - Sub-agents write here, never directly to curated memory.
3. Coordinator reviews proposals:
   - Set `status: accepted|rejected|stale`
   - Promote accepted items into:
     - Stable project items → `memory/projects/<project>/MEMORY.md`
     - Global prefs/infra/rules → `MEMORY.md`
4. Update `LOOPS.md` items (close or advance next steps).
5. (Optional) Move closed loops to `LOOPS_ARCHIVE.md`.

## Frequency
- Rolling `SUMMARY.md`: every ~10–20 turns or when context feels large.
- Promotions: milestones only (not daily).
- Weekly: prune stale proposals + archive closed loops + dedupe memory.

## What NEVER Goes Into Long-Term Memory
- Secrets, tokens, passwords
- One-off chat banter
- Unverified assumptions
- Transient debugging logs
- Anything that changes weekly

## Proposal Format

```yaml
- id: PROP-001
  status: pending          # pending | accepted | rejected | stale
  created_at: 2026-03-15
  proposed_by: backend-dev  # which agent proposed this
  kind: fact               # fact | procedure | preference | lesson
  scope: global            # global | project:<name>
  key: short.dot.key
  content: The actual thing to remember
  rationale: Why this is worth storing long-term
  confidence: 0.9          # 0.0–1.0
```
