# CLAUDE.md — AI Database Maintenance Co. (working name)

**Location:** `CLAUDE.md` at the project root. Committed. Shared with the team.

**Loaded in addition to** `~/.claude/CLAUDE.md` (global) and any nested `CLAUDE.md` files — all merged at session start. This file does **not** replace the global one.

### Context Files and Their Roles

| File | Purpose | Auto-loads? |
|---|---|---|
| `~/.claude/CLAUDE.md` (Global) | Mike's portable user rules | Yes |
| `CLAUDE.md` at project root (this file) | Project behavior for this business | Yes |
| `SECURITY.md` | Mandatory security rules | Not yet created — no code exists yet |
| `PRD.md` | WHAT + WHY (requirements, "done") | **No — read at task start** |
| `spec/plan.md` | HOW (architecture, build order) | Not yet created — no build has started |
| `README.md` | How humans install / run | Not yet created |

**Living document:** When Claude does something wrong in a PR, add a rule here in the same PR.

---

## About This Project

- **Name**: AI Database Maintenance Co. (working name)
- **Type**: Service/consulting business (not a software product) — see `PRD.md` for the open question on this
- **Primary Tech**: Not yet decided — no code exists yet. Default stack per Mike's global preferences is JavaScript/Node, ES modules, when tooling is eventually built.
- **Key Purpose**: Ongoing maintenance (health checks, backups, performance tuning, incident response) for vector databases and other databases underlying AI applications, for Texas-based clients.

---

## Security

No `SECURITY.md` exists yet — there's no code to secure. Once a marketing site or client-tooling app is built, create one from the standard template before writing any code that handles secrets, user input, or client credentials.

**Non-negotiable baseline (from global rules):** Never hardcode secrets — use `.env` only. `.env` must be in `.gitignore` before the first commit. Never log tokens or PII. Client database credentials/connection strings for any future tooling are treated as secrets.

---

## Before Any Feature Work — Read These First

These files do **not** auto-load. Read them at the start of every new task, before writing code.

- **`PRD.md`** — WHAT and WHY. Confirm the goal, the Open Questions section, and the "done" checklist before touching code.
- **`spec/plan.md`** — HOW. Not yet created; no build has started.

If either file is missing or stale, flag it — run `/kickoff` to generate them.

---

## Team Workflow

- **Plan mode first** for any non-trivial task.
- This project has no `.claude/skills/` or `.claude/agents/` yet — add them once repeatable workflows emerge.
- **Feedback loops** are required once code exists: tests, screenshots, lint, type-check.

---

## Permissions

No `.claude/settings.json` override exists for this project — the user's default permission mode applies. Claude must still stop and confirm before any irreversible or shared-state action (deletions, force-push, deploys, sending messages, modifying CI/CD or secrets), per global rules.

---

## Project Rules for Claude

- **Code style**: Not yet applicable — no code exists. When code is written, follow Mike's global style (ES modules, async/await, 2-space indent, descriptive names).
- **Naming**: TBD
- **Testing**: TBD
- **Branches**: TBD
- **Critical files (ask before modifying)**: `PRD.md` (scope changes should be flagged, not silently made)

---

## What Does NOT Belong in This File

Route content to the right layer. Keep this file short.

- Feature specs, requirements, success metrics → **`PRD.md`**
- Architecture, DB schema, API routes, build order → **`spec/plan.md`** (not yet created)
- Full security rules → **`SECURITY.md`** (not yet created)
- Install / run / contribute for humans → **`README.md`** (not yet created)
- Personal preferences → **`~/.claude/CLAUDE.md`**

If this file exceeds ~1 page, audit and move content out.

---

## Key Contacts

- **Tech Lead**: Mike — mhearty1@gmail.com
- **Product Owner**: Mike — mhearty1@gmail.com
- **Slack**: N/A

---

**Rule of Thumb:** If unsure, ask before acting. Better to clarify than break something.
