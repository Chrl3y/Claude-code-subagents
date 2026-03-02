Invoke the project-continuity agent to capture the current session state and prepare a cross-platform handoff.

Perform the following steps:

1. **Scan this session** — identify all decisions made, code written, problems solved, and approaches chosen since the conversation started.

2. **Read existing context files** — check for CLAUDE.md, HANDOFF.md, and any `.claude/` config in the current project. Understand what was already known before this session.

3. **Update CLAUDE.md** — using the project-continuity agent's CLAUDE.md structure, update or create these sections:
   - `## Project State` — current one-paragraph status
   - `## Architecture Decisions` — append any new decisions with rationale
   - `## Artifact Registry` — update statuses of anything touched this session
   - `## Active Context` — refresh with the exact current moment
   - `## Session Log` — append a new entry for this session

4. **Write HANDOFF.md** — generate a self-contained handoff document at the project root so any Claude surface (chat, CLI, VS Code) can resume immediately without re-reading history.

5. **Output a resume prompt** — print a single copyable block the user can paste into any new Claude session to restore full context instantly.

Format the final resume prompt as:
```
> Context: [project name]. [2-sentence state summary]. Last session: [date].
> Artifacts: [comma-separated list with statuses].
> Next: [single most important action].
> Load CLAUDE.md for full context.
```

Be thorough on decisions and rationale — the goal is zero context loss when switching platforms.
