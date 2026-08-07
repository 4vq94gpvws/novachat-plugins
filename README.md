# NovaChat Plugins

Claude-formaat plugins voor NovaChat/OpenWork. Elke plugin bundelt een remote MCP-server (met OAuth) plus een skill met werkinstructies voor de agent.

| Plugin | Installatie-URL |
|---|---|
| Supabase | `https://github.com/4vq94gpvws/novachat-plugins/tree/main/plugins/supabase` |
| Vercel | `https://github.com/4vq94gpvws/novachat-plugins/tree/main/plugins/vercel` |

Installeren kan in NovaChat via **Aanpassen** (sidebar) → URL plakken of de catalogus, of door de URL aan de `claude-plugins`-route van de OpenWork-server te geven.

Formaat per plugin:

```
plugins/<naam>/
  .claude-plugin/plugin.json   # naam, beschrijving, versie
  .mcp.json                    # remote MCP-server (url + oauth)
  skills/<naam>/SKILL.md       # werkinstructies voor de agent
```
