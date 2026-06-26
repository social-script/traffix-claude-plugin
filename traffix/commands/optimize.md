---
description: Execute the highest-impact opportunity for a client, end to end
argument-hint: [client name or domain]
---
Use the `traffix` MCP server to execute the top opportunity for **$1** (or ask which client if not given).

1. `list_sites` → resolve the client to its `site_id`.
2. `get_opportunities(site_id)` → take the highest-impact OPEN item.
3. `get_opportunity(opportunity_id)` → read the evidence, the target page/keyword, and the **playbook**.
4. If you need the full methodology, call `get_methodology(playbook_ref)` for the verbatim build-site reference.
5. Execute the fix in the current repo, following the playbook step by step. Use `keyword_research` / `serp_analysis` for live intent where useful.
6. Build/verify locally. Commit on a branch and (if the user approves) push.
7. Call `log_change(site_id, summary, commit)` and `update_opportunity(opportunity_id, "done")`.
Report what you changed and the expected impact.
