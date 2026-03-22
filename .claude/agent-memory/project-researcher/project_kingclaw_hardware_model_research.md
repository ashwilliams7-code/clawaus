---
name: King Claw — Hardware Model Research
description: Full analysis of King Claw's hardware delivery model options: provide Mac Mini, client owns hardware, hybrid, or cloud. Covers financials, ops, risk, legal, tax, competitive, and scalability. Researched 2026-03-22.
type: project
---

# King Claw Hardware Model Research

**Researched:** 2026-03-22
**Decision question:** Should King Claw provide hardware, use client hardware, go hybrid, or go cloud?

## Key Data Points

### Mac Mini M4 Pricing (AUD)
- **Retail (Apple AU):** $999 AUD (M4, 16GB, 256GB)
- **Education pricing (Apple On Campus via unions like AEU):** ~$815 AUD — no student ID required to access some programs
- **Reseller margin on Apple hardware:** 8–10% gross margin maximum (Apple notoriously tight)
- **Refurbished / grey market:** $750–$850 range possible

### Competitor: Ralph (getralph.ai)
- Three-tier model: Cloud VPS $2,000 setup / Mac Mini remote $3,500 / Mac Mini in-person $4,000
- Offers BOTH cloud and on-premise options (already running hybrid model)
- Cloud option: Ralph hosts VPS, ~$5–10/month ongoing to Ralph
- Hardware: client-owned Mac Mini, Ralph does setup
- Sydney only for in-person; rest of AU remote

### AWS Cloud Hosting (Sydney, ap-southeast-2)
- Lightsail small (~2 vCPU, 1GB RAM): ~$12 USD/month ≈ $19 AUD/month
- Lightsail medium (~2 vCPU, 4GB RAM): ~$20 USD/month ≈ $31 AUD/month
- EC2 t3.medium on-demand: ~$30–40 USD/month ≈ $48–64 AUD/month
- Note: Sydney region has 50% reduced data transfer allowance vs US regions
- Mac Mini M4 runs OpenClaw far better than any $20/month VPS (unified memory, 16GB, NPU)

### Australian Tax — Instant Asset Write-Off (FY2025–26)
- $20,000 per asset threshold, extended to 30 June 2026
- Eligible: businesses with aggregated turnover under $10M
- Eligible assets: IT equipment including computers
- Asset must be installed AND operational by 30 June 2026
- **Implication:** A client buying (or receiving) a Mac Mini worth $999 can write off the full amount if structured correctly — massive sales hook

### Hardware Leasing (HaaS Model)
- HaaS = monthly fee covers hardware + maintenance + upgrades
- MSP retains ownership, client never buys
- King Claw could charge ~$80–120/month for Mac Mini lease component (covers $999 hardware over 12–18 months + margin)
- Pros: recurring revenue, King Claw retains asset, client has lower upfront

### MSP Industry Norms (Australia)
- Most AU MSPs use a mix: for servers/critical infrastructure they own and lease to client; for endpoints BYOD is common
- Per-device pricing common: $50–150/device/month managed
- Trend in 2026: value-based and fixed-fee monthly models preferred by clients
- 61% of AU SMBs already outsource IT management — receptive to managed hardware
- SMBs strongly prefer predictable monthly costs over large capital outlays

### Liability (Hardware on Client Premises)
- MSP contracts should explicitly disclaim responsibility for hardware failure caused by vendor/manufacturer
- Clear clause needed: who replaces failed hardware (King Claw or client?)
- Apple Care+ for Business: 3-year coverage, $79 AUD/year per device — King Claw can bundle
- If King Claw provides hardware under HaaS, they bear warranty responsibility — must have AppleCare
- Dundas Lawyers (AU) specialises in MSA drafting — reference for contract templates

## Recommendation
**Option C — Hybrid model with HaaS as the flagship:**
- Essentials tier: BYOC (Bring Your Own Computer) — client has compatible Mac, King Claw installs remotely
- Professional tier: HaaS — King Claw retains ownership, charges monthly lease component, includes AppleCare
- Enterprise tier: Dedicated leased hardware, on-site setup, full managed care
- Cloud option available for clients who want zero on-premise footprint

**Why:** Ralph already proves hybrid works. HaaS is better than "free Mac Mini" — it creates recurring hardware revenue, King Claw retains the asset, and clients get lower upfront cost. The $20K instant write-off is a strong sales hook for client-owned model too.

**Why:** Sourced 2026-03-22 from: Apple AU edu store, OzBargain, getralph.ai, AWS CloudPrice, ATO, Dundas Lawyers, DeskDay, TechBrain AU, Wolfe Systems AU, The Mac Index AU.
