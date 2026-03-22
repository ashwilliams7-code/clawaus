---
name: OpenClaw Skills Research — Business Deployment Top 10
description: Research findings on available OpenClaw skills from official registries and GitHub, ranked for business use across aviation, real estate, accounting, legal, healthcare, hospitality
type: project
---

Research completed 2026-03-18.

**Why:** Identify the top 10 NEW skills to install for a business-focused OpenClaw deployment (Aether Intelligence / ClawAus clients: aviation, real estate, accounting, legal, healthcare, hospitality).

**Sources investigated:**
- `github.com/openclaw/skills` — official ClawHub archive (66,389 tree entries, 5,400+ skills, indexed by username/slug)
- `github.com/VoltAgent/awesome-openclaw-skills` — 5,366 curated community skills (39k stars)
- `github.com/LeoYeAI/openclaw-master-skills` — 339 curated weekly-updated skills (1.9k stars)
- `clawhub.ai` — live registry (currently empty/no published listings at time of research)

**Skill repo structure:** `skills/<github-username>/<skill-slug>/SKILL.md`

**Install method:** `clawhub install <username>/<skill-slug>` OR copy dir to workspace `skills/`

**Already installed (25 skills):** accli, ai-humanizer, ai-researcher, automation-workflows, calendar, clean-code, cli-anything, data-analysis, data-anomaly-detector, healthy-eating, home-assistant, intelligent-budget-tracker, language-learning, learning, linkedin, meeting-prep, para-second-brain, parenting, personal-finance, proactive-agent, recipe, resume-cv-builder, social-media-scheduler, travel-planning, workout

**Top 10 NEW skills for business deployment:**

1. **gmail** (byungkyu) — Gmail API via Maton OAuth. Read/send/manage email, threads, labels, drafts. Requires MATON_API_KEY.
2. **native-hubspot** (codeninja23) — HubSpot CRM direct API (no proxy). Contacts, companies, deals, pipelines. Requires HUBSPOT_TOKEN.
3. **native-stripe** (codeninja23) — Stripe direct API. Charges, invoices, subscriptions, refunds. Requires STRIPE_SECRET_KEY.
4. **pdf-tools** (cmpdchtr) — Extract, edit, merge, split, rotate PDFs. Pure Python (pdfplumber + PyPDF2), no API key needed.
5. **biz-reporter** (ariktulcha) — Pulls GA4, Search Console, Stripe, HubSpot, Airtable, social metrics into KPI reports. Delivers via Slack/email/Notion/Markdown.
6. **google-calendar** (adrianmiller99) — Google Calendar REST API (native OAuth). List, create, update, delete events. Requires GOOGLE_CLIENT_ID, GOOGLE_CLIENT_SECRET, GOOGLE_REFRESH_TOKEN.
7. **quote-invoice-workbench** (52yuanchangxing) — Turns pricing notes into professional quotes, SOW line items, and invoice drafts. No API key.
8. **contract-reviewer** (1kalin / AfrexAI) — Reviews NDAs, MSAs, SaaS agreements, SOWs for risks, missing clauses, compliance gaps. Structured risk report output.
9. **aviation-weather** (dimitryvin) — METAR, TAF, PIREPs from aviationweather.gov (FAA). No API key needed. Key for aviation vertical.
10. **compliance-officer** (arberx / QCME-AI) — Reviews marketing content against 208 regulations: FTC, HIPAA, GDPR, SEC, CCPA, COPPA, CAN-SPAM. Cites laws with URLs.

**How to apply:** When asked to recommend or install skills for business/Aether Intelligence use cases, reference these as the vetted top 10. Note: byungkyu skills require a Maton API key (maton.ai OAuth proxy). codeninja23 skills are direct API (preferred — no third-party dependency).
