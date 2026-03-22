---
name: sky_skills_installation
description: Skills installed into Sky's OpenClaw instance at /Users/sky/Documents/sky/skills/ and how skill registration works
type: project
---

# Sky OpenClaw Skills

## Registration Model
OpenClaw uses `nativeSkills: "auto"` (set in `/Users/sky/.openclaw/openclaw.json`). Skills are **auto-discovered** from the workspace `skills/` directory by reading `SKILL.md` files — no manual registration in `openclaw.json` needed. Only skills that require API keys (like `openai-image-gen`) have entries under `skills.entries`.

## Skills Installed 2026-03-21
All installed to `/Users/sky/Documents/sky/skills/<skill-name>/`:

| Skill | Source | Notes |
|-------|--------|-------|
| `pdf-tools` | `cmpdchtr/pdf-tools` | pdfplumber + PyPDF2 deps installed |
| `quote-invoice-workbench` | `52yuanchangxing/quote-invoice-workbench` | python3 only, no extra deps |
| `aviation-weather` | `dimitryvin/aviation-weather` | stdlib only, hits aviationweather.gov API — live-tested with YBBN |
| `contract-reviewer` | `1kalin/contract-reviewer` (AfrexAI) | Prompt-only skill, no scripts |
| `compliance-officer` | `arberx/compliance-officer` (QCME-AI) | 208 rules in JSON files under references/ |

## Python Dependencies Installed
`pdfplumber`, `PyPDF2` installed via `pip3 install --break-system-packages` (Python 3.14.3 at `/opt/homebrew/bin/python3`).

**Why:** macOS PEP 668 blocks pip without `--break-system-packages`. Use this flag for future pip installs on this machine.

## Aviation Weather Notes
- Default airports are SoCal (KSMO, KLAX, KVNY) — for AU airports use ICAO codes like YBBN (Brisbane), YSSY (Sydney)
- No API key required — free FAA aviationweather.gov API
- Highly relevant to the Aviation vertical in ClawAus

## How to apply
When installing more OpenClaw skills: drop the directory into `/Users/sky/Documents/sky/skills/`, install any deps, no config changes needed. Skills with API keys need an entry in `openclaw.json` under `skills.entries`.
