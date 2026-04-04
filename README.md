# User Root Agent System

Personal global Claude Code configuration.
Applies to all projects via `~/.claude/`.

## Structure

```
CLAUDE.md                          # Core laws (~30 lines, always loaded)
rules/
  clean-architecture.md            # Architecture quality gates (always loaded)
  go.md                            # Go rules (*.go)
  typescript.md                    # TypeScript rules (*.ts, *.tsx)
  python.md                        # Python rules (*.py)
  shell.md                         # Shell rules (*.sh)
  markdown.md                      # Markdown rules (*.md)
  deployment.md                    # Deploy safety (always loaded)
  chinese-writing.md               # Chinese output quality (always loaded)
skills/
  leveraging-tasks/                # Thin router: classify → gate → delegate
  reflecting-to-root/              # Session reflection → user/project routing
```

## Skills

### leveraging-tasks

Thin router that intercepts all significant tasks.
Classifies into four pipes (implement, design, debug, deploy) with cross-cutting refactor awareness.

- **Quality awareness** is continuous, not just an entry gate
- **Refactor** is not a separate pipe — it's a reflex embedded in all pipes
- **Feedback loops**: implement discovers new context → back to design; debug finds architectural root cause → refactor first

### reflecting-to-root

Post-session reflection that captures learnings at the correct scope.

- Cross-project patterns → `~/.claude/CLAUDE.md` or `~/.claude/rules/`
- Project-specific patterns → `.claude/CLAUDE.md` or `.claude/rules/`
- Delegates to `rcc:reflecting` for project-level integration when available

## Design Principles

- **CLAUDE.md = constitution**: universal laws, every word counts
- **rules/ = scoped laws**: loaded by file glob, saves context window
- **skills = leverage**: few powerful process skills that multiply project-level skills
- **settings.local.json**: sensitive data (accounts, IPs) — not tracked

## Model Routing

| Role | Model |
|------|-------|
| Router / orchestration | opus (session default) |
| implement / deploy / refactor | sonnet |
| design / debug | opus |
| search / summary / formatting | haiku |

## Not Tracked

- `settings.json` / `settings.local.json` (credentials, paths)
- `plugins/` (managed separately)
- `todos/`, `projects/`, `statsig/` (auto-generated)
- Existing user skills (`agent-browser/`, `find-skills`)
