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

Call `get_methodology()` once to get the methodology **category map** (`referencesByCategory`), then produce the audit **grouped by category** rather than as a flat list.

- Open with the **Readiness score** (from `check_readiness`).
- Then one section per methodology category that has findings, in catalog order: **Foundations · SEO (on-page) · GEO & AI discoverability · Performance & QA · Visual, design & components · Content & internal linking · Conversion & measurement · Off-page & local**. Under each, list the specific gaps (from `check_readiness`, and for connected clients from `get_research`/`get_pages`/`get_trends`) with the actual numbers, and name the fixing reference.
- **Treat a category with zero coverage as a finding, not a pass** — an empty *GEO & AI discoverability* or *Conversion & measurement* section is one of the biggest misses, so call it out explicitly.
- Close with a **Prioritised backlog (top 10 by impact)**, each item tagged with the category it sits in.

For any fix you detail, pull `get_methodology(ref)` for the verbatim build-site reference. Be specific and cite the numbers.
