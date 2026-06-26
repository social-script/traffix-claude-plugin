---
description: Build or optimise a page using the build-site methodology
argument-hint: [what to build]
---
You are building/optimising: **$1**.

Pull the methodology from the `traffix` MCP before writing code:
1. `get_methodology()` → see the catalog of playbooks + references.
2. `get_methodology(ref)` for the relevant references — e.g. `seo-page-brief`, `structured-data`, `geo-answer-engines`, `conversion-and-leads`, `lighthouse-perf-gate`, `interlinking-pass`, `agent-readiness`.
3. If this is for a tracked client, `get_research` / `serp_analysis` for the keyword cluster + winning SERP intent.

Then build the page to the methodology: answer-first hero, intent-matched sections, real proof, correct structured data (verified against on-page content), conversion path, Core Web Vitals within budget, and AEO/GEO discoverability. Verify against the playbook's "done" checklist.

After deploying, verify with the MCP:
- `check_readiness(<url>)` → confirm the SEO/AEO/GEO signals actually landed (structured data, llms.txt, AI-crawler access, etc.). Close any remaining gaps.
- `generate_llms_txt(<url>)` → produce a starter `llms.txt`; review the summary and page labels, then commit it to `public/llms.txt`.
