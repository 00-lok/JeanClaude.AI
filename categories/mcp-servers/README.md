# Serveurs MCP

Le Model Context Protocol (MCP) est un standard ouvert annonce par Anthropic en novembre 2024 qui permet aux modeles IA de se connecter de maniere securisee a des outils et sources de donnees externes via une interface JSON-RPC 2.0 standardisee.

**En mars 2026** : 97 millions de telechargements SDK mensuels, 17 500+ serveurs indexes, SDKs disponibles en TypeScript, Python, Go, Rust, C#, Java, Ruby, C/C++.

---

## Sous-categories

| Sous-categorie | Description | Nombre |
|----------------|-------------|--------|
| [Officiels](official/) | Serveurs de reference maintenus par Anthropic / MCP Steering Group | 7 |
| [Bases de donnees](databases/) | PostgreSQL, MongoDB, DuckDB, Neo4j, Supabase, etc. | 14+ |
| [Automatisation navigateur](browser-automation/) | Playwright, Puppeteer, Browserbase | 4+ |
| [Web scraping](web-scraping/) | Firecrawl, Apify, Bright Data, Tavily, Exa | 8+ |
| [Cloud et DevOps](cloud-devops/) | AWS, Azure, Cloudflare, Vercel, Kubernetes, Docker | 12+ |
| [Integrations API](api-integrations/) | GitHub, Notion, Slack, Linear, Stripe, Jira | 10+ |
| [Monitoring et securite](monitoring-security/) | Sentry, Datadog, Grafana, SonarQube, Semgrep | 10+ |
| [Agregateurs](aggregators/) | Pipedream, Composio, MetaMCP — serveurs qui en connectent plusieurs | 5+ |

---

## Ou trouver plus de serveurs MCP

| Repertoire | Taille | URL |
|------------|--------|-----|
| **MCP.so** | 17 500+ serveurs | [mcp.so](https://mcp.so/) |
| **PulseMCP** | 12 370+ serveurs | [pulsemcp.com](https://www.pulsemcp.com/servers) |
| **Smithery.ai** | Milliers | [smithery.ai](https://smithery.ai/) |
| **Glama** | Curate | [glama.ai/mcp/servers](https://glama.ai/mcp/servers) |
| **MCPMarket** | Top 100 | [mcpmarket.com](https://mcpmarket.com/leaderboards) |

Voir aussi : [Registres et repertoires](../resources/registries-directories.md)

---

## Listes awesome GitHub

| Depot | Stars | Description |
|-------|-------|-------------|
| [punkpeye/awesome-mcp-servers](https://github.com/punkpeye/awesome-mcp-servers) | ~83.8k | Plus grande collection curatee, 7 260+ serveurs |
| [wong2/awesome-mcp-servers](https://github.com/wong2/awesome-mcp-servers) | ~3.8k | Liste curatee avec organisation par categorie |
| [tolkonepiu/best-of-mcp-servers](https://github.com/tolkonepiu/best-of-mcp-servers) | — | Liste classee, mise a jour hebdomadaire |

---

## Installation typique

Les serveurs MCP se configurent dans les parametres Claude Code :

```json
{
  "mcpServers": {
    "nom-du-serveur": {
      "command": "npx",
      "args": ["-y", "@package/mcp-server"],
      "env": {
        "API_KEY": "votre-cle"
      }
    }
  }
}
```

Fichiers de configuration :
- `~/.claude/settings.json` (niveau utilisateur)
- `.claude/settings.json` (niveau projet)
- `.claude/settings.local.json` (local, non commite)
