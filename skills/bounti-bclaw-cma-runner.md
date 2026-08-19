---
name: B.Claw — Comparative Market Analysis Runner skill
slug: cma-runner
category: pricing
api: null
operations: []
method: searched
source: https://bounti.ai/skills/cma-runner
generated: '2026-08-14'
---

# B.Claw — Comparative Market Analysis Runner

> Produce a defensible CMA for a target property using 3–6 recent comparable sales and active listings.

Published by Bounti at <https://bounti.ai/skills/cma-runner> as a schema.org `SoftwareApplication`
skill definition. Everything below is the provider's own published description of the skill.

## What the provider says it does

- Pulls 3–6 active comps and 3–6 sold comps in the target geography (half-mile / 90-day window default)
- Applies NAR PSA adjustment methodology for square footage, condition, lot, age, upgrades, view
- Categorizes comps by tier when the use case warrants (e.g. total-gut vs partial-update for fix-and-flip)
- Outputs a Google Sheet adjustment grid + a one-page seller summary
- Defensible price recommendation backed by the math, with comp selection rationale auditable

## Data sources and tools the provider names

Connected CRMs (Follow Up Boss, kvCORE, GoHighLevel, Brivity), then public real estate sources
(Zillow, Redfin, Realtor.com, county assessor records). The published page names the internal tool
calls `web_search`, `web_fetch`, `memory_store` and `memory_recall`.

## How an agent invokes it

**It cannot, from outside B.Claw.** Bounti publishes no operation, endpoint, or input schema for this
skill. It runs inside the authenticated B.Claw application; the product API at
`https://claw.bounti.ai/api` answers `401 {"error":"unauthorized","message":"Authentication required"}`
to every unauthenticated request and has no published contract. The only Bounti operations callable by
an agent today are the two unauthenticated content operations in `openapi/` — see
`skills/bounti-content-access.md`.

## Reference framework cited by the provider

NAR Pricing Strategy Advisor curriculum; Appraisal Institute Residential Sales Comparison Approach.
