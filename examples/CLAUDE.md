# Bridle Harness · CLAUDE.md example

> Drop a `CLAUDE.md` (or equivalent `.cursorrules` / `copilot-instructions.md`) at your repo root. This is the **System Context** component of the Harness Five-Pack — see `three-leaps.md` §9.1.

## Project context

This project follows the **Bridle / Three Leaps** AI coding governance methodology. Before generating any code, you (the AI agent) must:

1. Read the relevant `module.yaml` for the module being modified.
2. Check the `intent.yaml` for the desired-state declaration.
3. Verify the action's reversibility tier (R0–R5):
   - R0–R1: you may execute directly
   - R2: you may execute, must write to `docs/agent-decisions/`
   - R3: you propose a PR, do not auto-merge — human review required
   - R4: stop and ask the human; do not proceed
   - R5: refuse — this is a permanent red line (financial / physical / irreversible user impact)

## Boundaries

- Do **not** edit modules outside the one named in the user's prompt unless explicitly asked.
- Do **not** modify `module.yaml` `lifecycle.state` fields without a corresponding intent change and a state-transition rationale.
- Do **not** humans-in-the-loop bypass — never use `--no-verify` or skip CI.
- Do **not** delete files in `archive/` or `docs/agent-decisions/` (append-only audit trail).

## Quality gates

Every PR you open must satisfy:

- `lint` + `type` + `unit-test` + `contract-test` + `sec-scan` all green
- New code coverage ≥ 80%
- No new boundary violations (run `archtest`)
- `intent.yaml` field updates have matching verifier updates

## Decision audit

Every state-changing action you take is logged to `docs/agent-decisions/<module-name>.md` with:

- timestamp
- triggering signal
- action taken
- reversibility tier
- rollback procedure

This is mandatory under the **AI Decision Auditor** role (three-leaps.md §13.3).

## Anti-patterns to avoid

| Anti-pattern | Why it's bad |
|---|---|
| Filling in `signals.*` values manually | Must be mechanically collected (three-leaps.md §5.4) |
| Promoting `experimental` → `asset` without `candidate` step | Skips the candidate verification gate |
| Editing `module.yaml` outside the module's own directory | Cross-domain manifest writes are R3 |
| Adding fields to `intent.yaml` without binding a verifier | Anti-pattern A2: "intent ≠ execution" |

## When in doubt

Read these in order:

1. `three-leaps.md` §10 (autonomy gradient) — to know what tier this action is
2. `three-leaps.md` §12 (anti-patterns) — to check you're not stepping on a known trap
3. The module's own `module.yaml` `audit.reversibility_max` — caps what you may auto-act on

If still uncertain, **stop and ask the human**. Asking is always cheaper than rolling back.
