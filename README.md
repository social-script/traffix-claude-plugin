# traffix — Claude Code plugin

**The SEO/AEO/GEO brain for your Claude Code**, powered by [traffix.dev](https://traffix.dev).

traffix connects Claude Code to the traffix.dev MCP so it can audit any site, pull prioritised, data-backed opportunities for your clients, and execute the fix in your repo — following the same methodology behind 15+ ranked sites.

- **AEO/GEO-first:** built for the era where ChatGPT, Perplexity and Google AI Overviews decide who gets cited — not just blue links.
- **Repo-native:** the work happens in your codebase, the way you already work in Claude Code.
- **Methodology-driven:** every fix follows a versioned playbook, so output is consistent across any harness.

## How it works (read this first)

This repo is the **thin command interface only** — five slash commands and the MCP connection config. The actual product lives server-side:

- the **methodology** (the full build-site playbooks, the 38 hard rules, the Phase 7 QA sweeps),
- the **SERP / keyword research** and competitor analysis,
- the **readiness scoring** and prioritised opportunity backlog,

…all run on the **traffix.dev MCP and are gated by your `TRAFFIX_API_KEY`**. The plugin is free and open; the brain is the key-gated API. Installing without a key gives you the commands, but they can't do anything until a valid key authenticates to `https://traffix.dev/api/mcp`.

## Install

```text
/plugin marketplace add https://github.com/social-script/traffix-claude-plugin
/plugin install traffix@traffix
```

Then set your API key (get one at **traffix.dev → Connect Claude Code**) and restart Claude Code:

```bash
export TRAFFIX_API_KEY=gos_xxx   # your own key — each user supplies their own
```

Run `/audit yourdomain.com` to see it work, or `/weekly` if you manage clients on traffix.dev.

## Commands

| Command | Argument | What it does |
|---|---|---|
| `/audit` | `[domain]` | Full SEO/AEO/GEO audit of any site — instant readiness score (structured data, llms.txt, AI-crawler access, sitemap, canonical, OG, title/meta) + gaps. Goes deeper for connected clients. No connection needed to start. |
| `/build` | `[what to build]` | Build or optimise a page to the build-site methodology (answer-first hero, intent-matched sections, valid structured data, conversion path, Core Web Vitals, AEO/GEO), then verify it. |
| `/optimize` | `[client]` | Execute the single highest-impact opportunity for a client end to end — fix it in the repo, then log it back. |
| `/weekly` | — | A client-ready weekly SEO/AEO/GEO update across your traffix.dev portfolio. |
| `/llms-txt` | `[domain]` | Generate a ready-to-paste `llms.txt` for any site. |

## Under the hood (MCP tools)

The commands orchestrate these server-side tools (all key-gated):

- `get_methodology(ref?)` — the catalog of playbooks + references (grouped by category), or a specific playbook/reference verbatim.
- `check_readiness(url)` — live 0–100 SEO/AEO/GEO readiness score + per-check gaps, each naming the methodology reference that fixes it.
- `serp_analysis(keyword)` / `get_research(...)` — live SERP intent + the keyword/research data behind each recommendation.
- `get_opportunity(...)` — the prioritised, impact-scored fix backlog for a tracked client, each with its execution playbook.
- `generate_llms_txt(url)` — a starter `llms.txt` from the live site.

The methodology is organised into: Foundations · SEO (on-page) · GEO & AI discoverability · Performance & QA · Visual, design & components · Content & internal linking · Conversion & measurement · Off-page & local · Build orchestration · Assets.

## Requirements

- Claude Code (CLI, desktop, or IDE extension).
- An active **traffix.dev API key** — the commands are inert without it.
- Node.js for the build/verification steps the `/build` methodology runs locally.

## Links & support

- Product & API keys: **[traffix.dev](https://traffix.dev)**
- Issues with the plugin commands: open an issue on this repo.
- Methodology / account questions: **info@socialscript.in**

## Note on licensing

The plugin in this repo (commands + config) is open. The **methodology, research data and scoring served by the traffix.dev MCP are proprietary to Social Script** and require an active traffix.dev subscription/key. Cloning this repo gives you the interface, not the brain.
