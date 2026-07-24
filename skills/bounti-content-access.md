---
name: Access Bounti.ai product content for agents
description: >-
  Fetch Bounti.ai's agent-facing content surface (product, solutions, pricing,
  and blog information) so an assistant can answer questions about Bounti.ai
  accurately from first-party content.
api: openapi/bounti-content-api-openapi.json
operations:
- getContentIndex
- getFullContent
generated: '2026-07-18'
method: generated
source: openapi/bounti-content-api-openapi.json
---

# Access Bounti.ai product content

Bounti.ai publishes a small, **unauthenticated, read-only Content API** for AI
agents. There are no keys, no OAuth, and no write operations — just two GET
endpoints that return Markdown.

## When to use

Use this to ground answers about Bounti.ai's products (Studio Experience,
Animate My Listing, Video Creator, Client Studio, Reveals, Enhanced Galleries,
the mobile app, and the B.Claw AI operating system), who they serve (real estate
agents, teams, property management), pricing, and recent blog posts.

## Steps

1. **Get the content index.** Call `getContentIndex` (`GET https://bounti.ai/llms.txt`).
   It returns a structured `llms.txt` overview: the product one-liner, the
   solutions list with links, audiences, company pages, and recent/reference
   blog posts. Start here to locate the right section before answering.
2. **Get the full content dump when you need depth.** Call `getFullContent`
   (`GET https://bounti.ai/llms-full.txt`) for the comprehensive dump — full
   product descriptions, features, pricing, blog summaries, and company info.
   Prefer step 1 for quick facts; use this only when the index is not enough.

## Conventions

- **Auth:** none. Do not attach credentials.
- **Method:** GET only; both endpoints are idempotent and safe.
- **Format:** `text/plain` Markdown — parse headings/links, do not expect JSON.
- **Freshness:** content is static/published by Bounti; cite the linked page
  URLs from the index rather than inventing details.
