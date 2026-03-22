---
name: Claude Code Ecosystem — March 2026 Snapshot
description: Top trending repos, features, MCP servers, hooks, and community findings as of March 19-21 2026. Useful for recommending Claude Code improvements to Ash.
type: reference
---

## New Claude Code Features (March 2026)

- **/voice** — push-to-talk, spacebar to record, supports 20 languages. Ash already has this via Hammerspoon.
- **/loop** — session-level cron: `/loop 5m check deploy` or `/loop 30s run tests`
- **/effort** — set analysis depth (low/medium/high); `ultrathink` keyword triggers max effort
- **/color** — assign colors to sessions for visual distinction
- **/context** — now gives actionable optimization suggestions, identifies token hogs
- **Opus 4.6 default** — 1M token context window on Max/Team/Enterprise
- **autoMemoryDirectory** — setting to configure custom memory dir
- **worktree.sparsePaths** — for monorepos, only checkout needed dirs
- **modelOverrides** — map model picker entries to custom model IDs (Bedrock etc)
- **MCP Elicitation** — servers can request structured input mid-task
- **Performance:** 16MB base memory reduction, 510KB bundle cut, 74% fewer prompt re-renders
- **Off-peak usage promo (March 2026):** Doubled limits 6PM–8AM ET. Australian users benefit significantly.

## Top GitHub Repos (Trending March 2026)

| Repo | Stars | What It Is |
|------|-------|-----------|
| affaan-m/everything-claude-code | 91k | Agent harness: 28 agents, 116 skills, 59 slash commands, security, memory |
| code-yeongyu/oh-my-openagent | 42k | Best agent harness (formerly oh-my-opencode) |
| thedotmack/claude-mem | 39k | Plugin: captures sessions → AI compress → semantic inject into future sessions |
| wshobson/agents | 32k | 112 agents, 72 plugins, 146 skills, 16 orchestrators, 79 dev tools |
| musistudio/claude-code-router | 30k | Route Claude Code to custom models (Bedrock, etc) |
| hesreallyhim/awesome-claude-code | 29k | Curated list of hooks, commands, plugins, orchestrators |
| davila7/claude-code-templates | 23k | CLI tool for configuring and monitoring Claude Code |
| PaulDuvall/claude-code | 91 | 62 slash commands (/xtest, /xquality, /xsecurity, /xgit etc), 26 sub-agents |
| jimovonz/engram | new | Hook-based semantic memory: invisible <memory> tags, SQLite + MiniLM embeddings |

## Top MCP Servers (March 2026)

- **GitHub MCP** — PR reviews, issue management, repo search (Ash already has gh skill)
- **Filesystem MCP** — local file ops
- **PostgreSQL MCP** — natural language DB queries
- **Slack MCP** — channel read/write/search
- **Apify MCP** — 3000+ scrapers (Google Maps, LinkedIn, Amazon, Instagram, YouTube)
- **Firecrawl MCP** — URL → Markdown for research
- **Bright Data MCP** — anti-bot scraping
- **Puppeteer MCP** — browser automation, screenshots
- **karellen-jdb-mcp** — debug JVM processes from Claude Code via JDWP (new March 21)
- **sxmc (Rust)** — bridge skills + MCP + APIs in one binary

## Notable Tools & Hooks

- **engram** — hook-based semantic memory across projects, local embeddings, no cloud. Install: `git clone + ./install.sh`
- **claude-mem** — plugin with lifecycle hooks + Chroma vector DB + web UI on port 37777. Install: `/plugin marketplace add thedotmack/claude-mem`
- **parry** — prompt injection scanner hook (early dev)
- **claude-esp** — Go TUI streaming Claude's hidden thinking/tool calls to separate windows
- **claude-tmux** — manage multiple Claude Code instances in tmux with git worktree support
- **Claude Squad** — terminal app managing multiple Claude Code + Codex instances simultaneously
- **ccflare/better-ccflare** — web UI token metrics and cost tracking
- **claudectx** — switch entire Claude Code configurations with one command
- **Britfix** — hook converting American → British English (preserves code identifiers)

## CLAUDE.md Best Practices (2026 Consensus)

- Keep under 200 lines / 150 instructions (LLM attention degrades beyond this)
- Use `@path/to/file` imports to reference without duplicating
- Path-scoped rules: `.claude/rules/*.md` with YAML `paths:` frontmatter
- CLAUDE.md = advisory. Hooks = deterministic. Use hooks for must-happen-every-time rules.
- `CLAUDE.local.md` = personal config, auto-gitignored
- Org-wide policy: `/Library/Application Support/ClaudeCode/CLAUDE.md` (macOS)
- Subdirectory CLAUDE.md files load on-demand (token efficient)

## Security Notes

- CVE-2026-25253 patched in v2026.3.12 (Ash already applied)
- Claude Code Security (Anthropic) — codebase vulnerability scanning, enterprise preview
- Ceros/Beyond Identity — AI Trust Layer, audit trail for agent actions
- MCP servers running with full developer permissions — scope carefully
