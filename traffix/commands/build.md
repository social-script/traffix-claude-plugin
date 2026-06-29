---
description: Build a new site or a page using the traffix methodology
argument-hint: [what to build]
---
You are building: **$1**.

First decide which path this is:

## A. A brand-new website (no existing site)
When the user wants a whole new site built from scratch, let traffix plan it from real search demand before you write any code.

1. Gather the business intake (ask the user for anything missing): name, what they offer, core services/products, who they serve, **service area / location**, the **keywords they want to rank for** (optional), desired feel, and whether they already own a domain.
2. Call `plan_new_site({ name, offering, services, audience, location, target_keywords, industry_feel, owned_domain })` on the `traffix` MCP. It researches real keyword demand + competitors in the target geo and returns an **SEO-backed build brief**: a sitemap where every page maps to a real-volume target keyword, plus brand direction. It also creates the site in the Growth OS at the `planning` stage (note the returned `site_id`).
3. Build the site **locally in this repo**, page by page, following the brief's sitemap. For EACH page pull the methodology and apply it:
   - `get_methodology('design-reference')` if a reference site is named (capture its real tokens — never reconstruct a brand from memory),
   - `get_methodology('seo-page-brief')` for the page brief against the page's `target_keyword` + intent,
   - `get_methodology('structured-data')` and `get_methodology('geo-answer-engines')` for schema + AEO/GEO,
   - `get_methodology('hard-rules')` and `get_methodology('qa-sweeps')` for the non-negotiables and Phase-7 checks.
4. **Always run the interlinking pass** once the pages exist: `get_methodology('interlinking-pass')`.
5. When the site is live, set its domain and connect Search Console so it moves from `planning` → tracked and traffix starts surfacing opportunities. Re-fetch the plan any time with `get_build_brief(site_id)`.

## B. A single page, or optimising an existing/tracked site
1. `get_methodology()` → the catalog grouped into categories; use it as your checklist. If this is a planned site, `get_build_brief(site_id)` for its sitemap + per-page target keywords.
2. Work the relevant categories in order — don't skip one that applies: Foundations → SEO (on-page) → GEO & AI discoverability → Content & internal linking → Performance & QA → Conversion & measurement (plus Visual, design & components for a new build). Pull `get_methodology(ref)` for each playbook you apply.
3. For a tracked client, `get_research` / `serp_analysis` for the keyword cluster + winning SERP intent.

## Always (both paths)
Build to the methodology: answer-first hero, intent-matched sections, real proof, correct structured data (verified against on-page content), conversion path, Core Web Vitals within budget, AEO/GEO discoverability. Verify against each playbook's "done" checklist.

After deploying, verify with the MCP:
- `check_readiness(<url>)` → confirm the SEO/AEO/GEO signals landed; close any gaps (a methodology category with no coverage is itself a gap).
- `generate_llms_txt(<url>)` → produce a starter `llms.txt`; review it, then commit to `public/llms.txt`.

The build runs entirely in your own Claude Code, on your tokens — traffix provides the plan, the demand data, and the methodology; you ship the code.
