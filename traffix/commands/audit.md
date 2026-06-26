---
description: Full SEO/AEO/GEO audit of a client site
argument-hint: [client name or domain]
---
Use the `traffix` MCP server to audit **$1**.

1. `get_site(site_id)` → identity, latest GSC metrics, connection status.
2. `get_research(site_id)` → keyword universe (intent · volume · difficulty), domain visibility, competitors.
3. `get_pages(site_id)` → per-page performance, index status, Core Web Vitals.
4. `get_trends(site_id)` → momentum.
Produce a structured audit: **Visibility & momentum** → **Top pages & issues** (index/CWV) → **Keyword gaps** (winnable = high volume + low KD) → **AEO/GEO readiness** (pull `get_methodology("geo-answer-engines")` and `get_methodology("structured-data")` to assess) → **Prioritised backlog** (top 10 by impact). Be specific and cite the numbers.
