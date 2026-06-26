---
description: Full SEO/AEO/GEO audit of a site (connected or not)
argument-hint: [client name or domain]
---
Use the `traffix` MCP server to audit **$1**.

Start with a readiness check that works on **any URL** — no connection required:

1. `check_readiness("$1")` → a 0–100 SEO/AEO/GEO score plus per-check gaps (structured data, llms.txt, AI-crawler access, sitemap, canonical, Open Graph, title/description). Each gap names the build-site reference that fixes it.

If **$1** is a connected client, go deeper with Search Console + research:

2. `get_site(site_id)` → identity, latest GSC metrics, connection status.
3. `get_research(site_id)` → keyword universe (intent · volume · difficulty), domain visibility, competitors.
4. `get_pages(site_id)` → per-page performance, index status, Core Web Vitals.
5. `get_trends(site_id)` → momentum.

Produce a structured audit: **Readiness score & gaps** (from `check_readiness`) → **Visibility & momentum** → **Top pages & issues** (index/CWV) → **Keyword gaps** (winnable = high volume + low KD) → **Prioritised backlog** (top 10 by impact). For any fix, pull `get_methodology(ref)` for the verbatim build-site reference. Be specific and cite the numbers.
