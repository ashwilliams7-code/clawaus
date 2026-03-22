---
name: wshobson_agents_installed
description: 10 agents cherry-picked from wshobson/agents (31.8k stars) and installed into ~/.claude/agents/ on 2026-03-21
type: project
---

10 specialized agents from https://github.com/wshobson/agents installed on 2026-03-21.

**Why:** Ash requested cherry-picking the most useful agents for his workflow covering architecture, security, marketing, debugging, and AI engineering.

**How to apply:** When Ash asks about available agents or sub-agent capabilities, the full team is now 14 agents (4 original + 10 new).

## Installed Agents

| File | Purpose |
|------|---------|
| `backend-architect.md` | API design, microservices, event-driven architecture, resilience patterns |
| `security-auditor.md` | OWASP audits, DevSecOps, auth review, compliance (GDPR/SOC2) |
| `incident-responder.md` | Production incidents, SRE, post-mortems, runbooks |
| `code-reviewer.md` | Deep code review — security, correctness, reliability, performance |
| `ai-engineer.md` | LLM apps, RAG systems, agent orchestration, prompt engineering |
| `business-analyst.md` | KPI frameworks, revenue modeling, cohort analysis, market sizing |
| `content-marketer.md` | Blog, social, email, SEO content — tailored for Aether/ClawAus |
| `docs-architect.md` | Comprehensive technical docs, ADRs, architecture guides |
| `debugger.md` | Root cause analysis, systematic debugging across any stack |
| `sales-automator.md` | Cold email sequences, proposals, sales scripts for AU SMBs |

## Format Notes
- All use YAML frontmatter: name, description, model, color, memory: project
- Models: sonnet for most; opus only where complexity demands it (not used here — cost-conscious)
- Colors chosen to visually distinguish role type in Claude Code UI
- Originals preserved: atlas, coding-partner, project-researcher, test-executor
