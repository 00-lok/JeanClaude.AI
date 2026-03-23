# Fetch (MCP officiel)

> Serveur MCP officiel pour la recuperation et conversion de contenu web en format adapte aux LLMs.

| Info | Detail |
|------|--------|
| **GitHub** | [modelcontextprotocol/servers — fetch](https://github.com/modelcontextprotocol/servers/tree/main/src/fetch) |
| **Site web** | [modelcontextprotocol.io](https://modelcontextprotocol.io/) |
| **Installation** | `npx -y @modelcontextprotocol/server-fetch` |
| **Categorie** | Serveur MCP — Web |
| **Licence** | MIT |
| **Statut** | Actif |
| **Derniere verification** | 2026-03-22 |

---

## Ce que ca fait

Le serveur Fetch MCP permet a tout client MCP de recuperer du contenu depuis des URLs et de le convertir en Markdown propre — en eliminant navigation, pubs et elements non essentiels pour ne garder que le contenu utile au LLM.

**Note pour Claude Code** : Claude Code possede un outil `WebFetch` natif. Ce serveur est principalement utile pour :
1. **Claude Desktop** qui n'a pas d'outil de fetch natif
2. **Workflows MCP standardises** ou vous voulez un seul protocole pour tous vos outils

---

## Fonctionnalites cles

- **Recuperation web** — Telecharger le contenu de n'importe quelle URL
- **Conversion Markdown** — Convertir automatiquement le HTML en Markdown propre
- **Extraction intelligente** — Elimine le bruit (navigation, pubs, footers)
- **Multi-format** — HTML, JSON, texte brut, PDF

---

## Installation

```json
{
  "mcpServers": {
    "fetch": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-fetch"]
    }
  }
}
```

---

## Liens

- [Depot GitHub](https://github.com/modelcontextprotocol/servers/tree/main/src/fetch)

---

*Derniere verification : 2026-03-22 · [Signaler un probleme](../../../.github/ISSUE_TEMPLATE/tool-update.md)*
