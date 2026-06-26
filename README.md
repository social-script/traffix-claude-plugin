# traffix — Claude Code plugin

The SEO/AEO/GEO brain for your Claude Code, powered by [traffix.dev](https://traffix.dev).

It connects Claude Code to the traffix.dev MCP and adds:

- **/weekly** — a client-ready weekly SEO update across your portfolio
- **/optimize [client]** — execute the highest-impact opportunity end to end (fix in your repo → log it back)
- **/audit [client]** — a full SEO/AEO/GEO audit (visibility, pages, CWV, keyword gaps, backlog)
- **/build [what]** — build/optimise a page using the build-site methodology

## Install

```
/plugin marketplace add social-script/traffix-claude-plugin
/plugin install traffix@traffix
```

Then set your agency API key (get it at **traffix.dev → Connect Claude Code**):

```
export TRAFFIX_API_KEY=gos_xxx
```

Restart Claude Code. Run `/weekly` to start.
