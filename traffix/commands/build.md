---
description: Build or optimise a page using the build-site methodology
argument-hint: [what to build]
---
You are building/optimising: **$1**.

Pull the methodology from the `traffix` MCP before writing code:
1. `get_methodology()` → the catalog, **grouped into categories** (`referencesByCategory`). Use it as your checklist.
2. **Work the relevant categories in order — don't skip one that applies to this page:** Foundations → SEO (on-page) → GEO & AI discoverability → Content & internal linking → Performance & QA → Conversion & measurement (plus Visual, design & components for a new build). Pull `get_methodology(ref)` for each playbook you apply (e.g. `hard-rules`, `seo-page-brief`, `structured-data`, `geo-answer-engines`, `interlinking-pass`, `qa-sweeps`, `conversion-and-leads`, `design-reference`).
3. If this is for a tracked client, `get_research` / `serp_analysis` for the keyword cluster + winning SERP intent.

Then build the page to the methodology: answer-first hero, intent-matched sections, real proof, correct structured data (verified against on-page content), conversion path, Core Web Vitals within budget, and AEO/GEO discoverability. Verify against the playbook's "done" checklist.

**If a reference website is named as the design target** ("make it look like `<url>`", "match `<url>`'s design"): never reconstruct the brand from memory — pull `get_methodology('design-reference')` and follow it to capture the site's real design tokens before writing any styles.

**Always run the interlinking pass — regardless of page count** (even a ~20-page site benefits; scale the effort to size, not whether you run it): pull `get_methodology('interlinking-pass')` and follow it.

After deploying, verify with the MCP:
- `check_readiness(<url>)` → confirm the SEO/AEO/GEO signals actually landed (structured data, llms.txt, AI-crawler access, etc.). Close any remaining gaps — a methodology category left with no coverage is itself a gap.
- `generate_llms_txt(<url>)` → produce a starter `llms.txt`; review the summary and page labels, then commit it to `public/llms.txt`.
