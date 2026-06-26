---
description: Generate a starter llms.txt for a site
argument-hint: [domain or url]
---
Use the `traffix` MCP server.

1. `generate_llms_txt("$1")` → a ready-to-use `llms.txt` built from the site's homepage (identity) and sitemap (key pages).
2. Review the summary and page labels for accuracy — tighten the descriptions so they're specific and honest.
3. Save the result to `public/llms.txt` so it serves at `/llms.txt`.
4. `check_readiness("$1")` → confirm the llms.txt check now passes (and spot any other AEO/GEO gaps to fix next).

Briefly explain what `llms.txt` is and why it helps AI answer engines (ChatGPT, Perplexity, AI Overviews) understand the site.
