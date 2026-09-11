# GUI

**HTML in, URL out.** One POST call returns a live, shareable page — real-time sync, interactive components, no build step, no account.

<img width="1200" height="675" alt="image" src="https://github.com/user-attachments/assets/d2919cf7-e0c0-411e-a07d-86510e66de79" />
  

  
Built for agents. An assistant that would otherwise dump a wall of HTML into a chat window can hand you a link instead.

**[gui.now](https://gui.now)** · [API reference](https://gui.now/docs) · [llms.txt](https://gui.now/docs/llms.txt)

---

## Try it

```bash
curl -X POST https://gui.now/api/canvas \
  -H 'Content-Type: application/json' \
  -d '{"html": "<h1>Hello, world</h1>", "title": "My Canvas"}'
```

```json
{
  "id": "abc123xyz",
  "url": "https://gui.now/abc123xyz",
  "edit_token": "tok_...",
  "expires_at": "2026-09-12T12:00:00Z"
}
```

That URL is live. JavaScript runs, forms work, and every `<input>` syncs across everyone viewing it. No account or API key needed.

## Teach your agent

Install the skill — works with Claude Code, Cursor, Codex, Windsurf, OpenClaw, and anything else that speaks the Skills protocol:

```bash
npx skills add gui-now/skills --skill gui-now -g
```

Or drop a rules file into your project root:

```bash
curl -O https://raw.githubusercontent.com/gui-now/templates/main/CLAUDE.md
```

`.cursorrules`, `.windsurfrules` and `AGENTS.md` live in the same repo.

## Repositories

| Repo | What it is |
|---|---|
| **app** *(private)* | The service — Next.js app, the HTTP API, the canvas renderer |
| [**skills**](https://github.com/gui-now/skills) | Agent skill: `SKILL.md` plus API, component and format references |
| [**templates**](https://github.com/gui-now/templates) | Drop-in rules files for Cursor, Windsurf, Claude Code and `AGENTS.md` |
| [**sdk**](https://github.com/gui-now/sdk) | TypeScript SDK |
| [**cli**](https://github.com/gui-now/cli) | Command line — pipe HTML in, get a URL out |
| [**mcp**](https://github.com/gui-now/mcp) | MCP server — six tools for creating and revising canvases |
| [**python**](https://github.com/gui-now/python) | Python SDK, with LangChain, LlamaIndex and CrewAI tools |

## What a canvas can do

- **Five input formats** — HTML, Markdown (server-rendered with syntax highlighting), Mermaid diagrams, multi-frame tabs, and component markup
- **Live sync** — inputs, selects and textareas stay in step across every viewer
- **Components** — charts, tables, cards, kanban boards, timelines and code blocks, auto-injected as `<gui-*>` tags
- **Editable** — `PUT` to the same canvas and every open viewer updates instantly

## Free and Pro

| | Free | Pro |
|---|---|---|
| Auth | none — just POST | API key |
| Size | 2 MB | 10 MB |
| Expiry | 24 hours | up to 30 days |
| Edits | 3 per canvas | unlimited |
| Rate | 5 creates/hr | 100 creates/hr |
| Password protection | — | ✓ |

[gui.now/pro](https://gui.now/pro)

## License

The open-source repositories are MIT licensed — see each repository's `LICENSE`.
