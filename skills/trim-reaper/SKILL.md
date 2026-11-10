---
name: trim-reaper
description: Run a Trim Reaper dependency-reduction pass (assess, 1-8, or policy) on the current project while preserving behavior, security, and compatibility.
argument-hint: "[assess | 1-8 | policy]"
disable-model-invocation: true
---

# Trim Reaper

The user invoked this skill with: `$ARGUMENTS`

Pick the action from the argument (case-insensitive; a pass name like `unused` or `verify` also works):

| Argument | File | What it does |
|---|---|---|
| `assess` / `0` | `passes/0-assess.md` | Read-only assessment and prioritized plan. **Do not** load `shared.md`; make no changes. |
| `1` / `unused` | `passes/1-unused.md` | Remove unused dependencies |
| `2` / `stdlib` | `passes/2-stdlib.md` | Replace with the standard library |
| `3` / `simple` | `passes/3-simple.md` | Replace small, simple functionality |
| `4` / `overlap` | `passes/4-overlap.md` | Consolidate overlapping libraries |
| `5` / `transitive` | `passes/5-transitive.md` | Reduce transitive overhead |
| `6` / `prod-scope` | `passes/6-prod-scope.md` | Keep dev dependencies out of production |
| `7` / `larger` | `passes/7-larger.md` | Evaluate larger replacements |
| `8` / `verify` | `passes/8-verify.md` | Verify and report |
| `policy` | `policy.md` | Add the third-party library policy to the project's `AGENTS.md` (or `CLAUDE.md`). If dependency guidance already exists there, reconcile into one consistent policy. Show the diff; don't commit unless asked. |

If the argument is empty or unrecognized, list the options above and stop.

## Running a numbered pass (1-8)

1. Read `shared.md` in this skill's folder. Treat it as the governing instruction for the whole pass.
2. Read `policy.md` too. `shared.md` refers to "the third-party library policy above"; this file is that policy. If the project's `AGENTS.md`/`CLAUDE.md` already has its own dependency policy, follow the project's version and use `policy.md` only to fill gaps.
3. Read the selected pass file and carry it out under the shared instruction.
4. Run only the selected pass. Don't continue into other passes unless the user asks.
5. After any pass other than 8, remind the user to finish with pass 8 (verify): `/trim-reaper:trim-reaper 8` when installed as a plugin, `/trim-reaper 8` when copied into `~/.claude/skills/`.

The prompt files are copied verbatim from the Trim Reaper readme (https://github.com/jmanico/trim-reaper, MIT). Keep them in sync with `readme.md` when it changes upstream.
