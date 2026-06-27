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

**If a reference website is named as the design target** ("make it look like `<url>`", "match `<url>`'s design"): extract its REAL design tokens before writing any styles. Drive Playwright to the URL and capture its `:root` CSS custom properties, `getComputedStyle` on `body/h1/h2/h3/p/a/button/nav`, the most-used background / text / button colours, container width, radii and motion easings, plus a full-page screenshot — and build from that captured data. NEVER reconstruct the brand's look from memory; approximating it (serif-vs-sans, palette, spacing, button shape) reliably misses and gets rejected. (See build-site Phase 0.5 + hard rule #36.)

**Always run the interlinking pass — regardless of page count.** Once the pages exist, add contextual inline body links (not just `RelatedLinks` blocks) across the site with varied anchor text; parallelise one-agent-per-file. Even a ~20-page site benefits — `RelatedLinks` alone leaves the strongest internal-link signal on the table. Scale the effort to the size, not whether you run it. (See `get_methodology('interlinking-pass')` + build-site Phase 6.5.)

After deploying, verify with the MCP:
- `check_readiness(<url>)` → confirm the SEO/AEO/GEO signals actually landed (structured data, llms.txt, AI-crawler access, etc.). Close any remaining gaps.
- `generate_llms_txt(<url>)` → produce a starter `llms.txt`; review the summary and page labels, then commit it to `public/llms.txt`.
