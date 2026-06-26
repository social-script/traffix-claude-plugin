---
description: Weekly SEO update across your traffix.dev client portfolio
---
Use the `traffix` MCP server.

1. Call `list_sites` to get the portfolio.
2. For each connected site (or, if the user named a client, just that one), call `get_weekly_report`.
3. Present a concise, client-ready update per site:
   - **Momentum**: clicks/impressions this period vs last (call out the direction).
   - **Shipped**: the changes logged since last week.
   - **Top 3 opportunities**: title, impact, and the one-line "why" — highest impact first.
Keep it skimmable. End with a single recommended next action for the week.
