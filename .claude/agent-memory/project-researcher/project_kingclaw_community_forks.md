---
name: King Claw — 5 Community Fork Repos
description: Vetted community OpenClaw skill/agent repos for King Claw marketplace to fork. Star counts, skill counts, quality assessment, and fork commands. Researched 2026-03-22.
type: project
---

Research completed 2026-03-22.

**Why:** King Claw needs a deeper, more diverse skill catalog than openclaw/skills alone. Forking curated community repos adds 7,000+ additional skills across specialist domains (medical, finance, agent templates) without building from scratch.

**How to apply:** When recommending King Claw marketplace expansion, reference these 5 forks. The sync script at `/Users/sky/scripts/kingclaw-fork-community-repos.sh` handles daily upstream sync for all 5.

---

## The 5 Repos

### 1. VoltAgent/awesome-openclaw-skills
- **URL:** https://github.com/VoltAgent/awesome-openclaw-skills
- **Stars:** 40,600 | **Forks:** 3,900
- **Skills:** 5,211 curated (from 13,729 in official registry as of Feb 2026)
- **Categories:** 25+ (Coding Agents, Web Dev, DevOps, Browser Automation, Search, PDF/Docs, Communication, etc.)
- **Quality vetting:** Explicit exclusion lists — removes spam (4,065), duplicates (1,040), low-quality/non-English (851), malicious after security audit (373), and crypto/finance noise (886). Only includes skills already in official openclaw/skills repo.
- **What it adds:** Best-of filter on official registry. King Claw gets the curated 38% of skills that passed quality review, not the raw firehose.
- **Fork command:** `gh repo fork VoltAgent/awesome-openclaw-skills --org kingclaw-marketplace --repo voltAgent-awesome-skills --clone=false`

### 2. FreedomIntelligence/OpenClaw-Medical-Skills
- **URL:** https://github.com/FreedomIntelligence/OpenClaw-Medical-Skills
- **Stars:** 1,500 | **Forks:** 197
- **Skills:** 869 actual SKILL.md skills (clinical, genomics, drug intelligence, bioinformatics, regulatory/FDA)
- **Key skills:** SOAP notes, discharge summaries, PubMed search, ClinicalTrials.gov querying, drug-drug interaction prediction, ACMG variant classification, HIPAA/IEC 62304/ISO 14971 compliance guidance
- **Quality vetting:** Aggregates 12+ open-source biomedical repos. MIT licensed. FreedomIntelligence is a research collective focused on open-source biomedical AI.
- **Install method:** Copy skill dirs to `~/.openclaw/skills/` OR `clawhub install <slug>` — fully compatible with OpenClaw skill format.
- **What it adds:** Healthcare vertical entirely absent from official openclaw/skills at meaningful depth. Critical for ClawAus healthcare/medical clients.
- **Fork command:** `gh repo fork FreedomIntelligence/OpenClaw-Medical-Skills --org kingclaw-marketplace --repo freedom-medical-skills --clone=false`

### 3. LeoYeAI/openclaw-master-skills
- **URL:** https://github.com/LeoYeAI/openclaw-master-skills
- **Stars:** 2,000 | **Forks:** 370
- **Skills:** 339+ (weekly updated by MyClaw.ai)
- **Categories:** AI & LLM Tools (34), Development & DevOps (87), Productivity (35), Marketing & Growth (32), Search & Web (21), plus more
- **Quality vetting:** Hand-picked weekly curation by MyClaw.ai team. Not automated — editorial judgment. 12 open PRs suggests active contributor community.
- **What it adds:** Rolling "best of week" feed from across the ecosystem including GitHub and community sources beyond just ClawHub. Catches quality skills that haven't hit official registry yet.
- **Fork command:** `gh repo fork LeoYeAI/openclaw-master-skills --org kingclaw-marketplace --repo leoye-master-skills --clone=false`

### 4. sundial-org/awesome-openclaw-skills
- **URL:** https://github.com/sundial-org/awesome-openclaw-skills
- **Stars:** 491 | **Forks:** 63
- **Skills:** 913 across 20 categories (daily-updated badge)
- **Categories:** Finance & Trading, Health & Wellness, Security, Documents & Presentations, Smart Home, Cloud & Infrastructure, Audio & Speech — overlapping with but distinct from VoltAgent's categories
- **Quality vetting:** No documented formal process. "Most popular and useful" emphasis. Smaller/newer than VoltAgent but daily update cadence and independent curation means different editorial judgment.
- **What it adds:** Complementary slice to VoltAgent — particularly Finance & Trading and Security categories that VoltAgent explicitly excludes. Useful for fintech/trading use cases.
- **Fork command:** `gh repo fork sundial-org/awesome-openclaw-skills --org kingclaw-marketplace --repo sundial-awesome-skills --clone=false`

### 5. mergisi/awesome-openclaw-agents
- **URL:** https://github.com/mergisi/awesome-openclaw-agents
- **Stars:** 1,600 | **Forks:** 233
- **Templates:** 177 production-ready SOUL.md agent configs across 24 categories
- **Key verticals:** Finance (10 agents: Expense Tracker, Invoice Manager, Revenue Analyst, Tax Preparer, Trading Bot, Fraud Detector, etc.), Healthcare, Legal, Real Estate, Compliance, DevOps (11), Marketing (18), Customer Success
- **Quality vetting:** MIT licensed. Copy-paste SOUL.md format, register with `openclaw agents add`. All configs machine-readable via agents.json. 7 open PRs indicates active community.
- **IMPORTANT DISTINCTION:** These are SOUL.md agent personality/config templates, NOT SKILL.md skills. They configure complete agent identities, not individual tools. Perfect for King Claw's "pre-configured agent personas" marketplace tier.
- **What it adds:** Agent identity layer — King Claw can sell pre-built agent personas (e.g., "Finance Analyst Agent") rather than just raw skills. Different product category.
- **Fork command:** `gh repo fork mergisi/awesome-openclaw-agents --org kingclaw-marketplace --repo mergisi-agent-templates --clone=false`

---

## Sync Script
`/Users/sky/scripts/kingclaw-fork-community-repos.sh`
- Forks all 5 on GitHub (idempotent — skips existing forks)
- Clones locally to `/Users/sky/Documents/openclaw-au/community-forks/`
- Syncs each upstream daily, merges, pushes to King Claw's fork
- Sends Telegram notification with diff summary
- Run: `bash /Users/sky/scripts/kingclaw-fork-community-repos.sh`
- Dry run: `bash /Users/sky/scripts/kingclaw-fork-community-repos.sh --dry-run`
- Cron: Add `0 3 * * * bash /Users/sky/scripts/kingclaw-fork-community-repos.sh` for 3am daily sync

## Total skill coverage from all 5 forks
- VoltAgent: 5,211 curated skills
- FreedomIntelligence: 869 medical skills
- LeoYeAI: 339+ curated skills
- sundial-org: 913 skills (incl. finance/security)
- mergisi: 177 agent templates
- **Total: ~7,500+ additional resources** beyond official openclaw/skills
