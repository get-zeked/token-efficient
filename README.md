# token-efficient

> Adapted from [drona23/claude-token-efficient](https://github.com/drona23/claude-token-efficient) for Perplexity Computer.

One SKILL.md file. Drop it in. Cuts the filler Perplexity Computer adds to every response — narrated tool calls, sycophantic openers, post-action summaries, redundant confirmations — without losing any useful signal.

## The Problem

By default, Perplexity Computer:

- Opens with "Great question!" / "Sure!" / "Happy to help!"
- Narrates every tool call: "Let me search for that...", "Now I'll read the file..."
- Summarizes what it just did after doing it: "I've successfully created the file at /path/..."
- Restates your question before answering it
- Adds "Let me know if you need anything else!" to everything
- Creates todo lists for 2-step tasks
- Delegates to subagents when one direct tool call would suffice
- Over-qualifies simple answers with unnecessary caveats

All of this costs tokens. None of it adds value.

## The Fix

Upload `SKILL.md` to your Perplexity Computer skills. It activates on every session automatically.

## What It Fixes

| # | Problem | Fix |
|---|---------|-----|
| 1 | Sycophantic openers/closers | No filler phrases — just answer |
| 2 | Narrated tool usage | Execute tools silently |
| 3 | Post-action summaries | If the user can see the result, don't describe it |
| 4 | Restating the question | Answer directly |
| 5 | Redundant file confirmations | File is visible in UI — don't narrate the path |
| 6 | Unnecessary todo lists | Just do the task if it's under 3 steps |
| 7 | Over-delegation to subagents | Direct tool call when one call is enough |
| 8 | Decorative Unicode | Plain hyphens and straight quotes only |
| 9 | Excessive caveats | Save qualifications for genuine edge cases |
| 10 | Pre-action planning narration | Do, don't announce |

## Profiles

| Profile | Best For |
|---------|---------|
| **Universal** | Any Perplexity Computer session |
| **Coding** | Dev work, code review, debugging in the sandbox |
| **Research** | Web search, analysis, report building |
| **Automation** | Cron jobs, pipelines, batch operations |

## Install

### Perplexity Computer
1. Download `SKILL.md` from this repo
2. Go to **Skills** → **Create skill** → **Upload a skill**
3. Drop it in
4. Active on every session automatically

### Claude Code
Use the original: [drona23/claude-token-efficient](https://github.com/drona23/claude-token-efficient)

### Any SKILL.md-compatible agent (Codex, Cursor, Copilot)
Copy to your agent's skills directory. Follows the [agentskills.io](https://agentskills.io) open standard.

## Override Rule

User instructions always win. If you ask for verbose output, step-by-step breakdowns, or detailed explanations, those instructions override every rule in this file.

## Stats

- **110 lines** — intentionally minimal so it doesn't cost more input tokens than it saves
- **5.2 KB** — small enough to load on every message without overhead
- Validated against the agentskills.io spec

## Credits

Based on [drona23/claude-token-efficient](https://github.com/drona23/claude-token-efficient) by Drona Gangarapu. Adapted for the Perplexity Computer environment.

## License

MIT
