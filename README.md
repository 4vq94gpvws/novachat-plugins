# NovaChat Plugins

Claude-formaat plugins voor NovaChat/OpenWork. Elke plugin bundelt een remote MCP-server (met OAuth) plus een skill met werkinstructies voor de agent.

| Plugin | Installatie-URL |
|---|---|
| Supabase | `https://github.com/4vq94gpvws/novachat-plugins/tree/main/plugins/supabase` |
| Vercel | `https://github.com/4vq94gpvws/novachat-plugins/tree/main/plugins/vercel` |
| GitHub | `https://github.com/4vq94gpvws/novachat-plugins/tree/main/plugins/github` |

## De marketplace

`.claude-plugin/marketplace.json` is de lijst die NovaChat Desktop in **Aanpassen** toont. Een plugin toevoegen aan het aanbod = een regel in dit bestand, zonder nieuwe app-release. Het formaat is dat van een Claude Code-marketplace (`claude plugin validate .` moet slagen):

- `source` is een eigen map (`"./plugins/vercel"`), een hele repo (`{"source": "url", "url": "https://github.com/netlify/context-and-tools.git"}`) of een map in een repo (`{"source": "git-subdir", "url": "...", "path": "..."}`).
- `description` in het Nederlands en voor niet-technische gebruikers: wat kun je ermee, niet hoe het werkt.
- `tags: ["uitgelicht"]` zet hem bovenaan.

Zet er alleen een plugin in die NovaChat echt kan installeren én waarvan het inloggen werkt (de online server moet OAuth met dynamische registratie ondersteunen; GitHub doet dat niet en zegt dat ook in de omschrijving).

Deze repo is bewust **openbaar**: de app haalt de lijst en de plugins zonder inloggen op.

Formaat per plugin:

```
plugins/<naam>/
  .claude-plugin/plugin.json   # naam, beschrijving, versie
  .mcp.json                    # remote MCP-server (url + oauth)
  skills/<naam>/SKILL.md       # werkinstructies voor de agent
```
