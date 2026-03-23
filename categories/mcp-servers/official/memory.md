# Memory (MCP officiel)

> Serveur MCP officiel fournissant un systeme de memoire persistante base sur un graphe de connaissances.

| Info | Detail |
|------|--------|
| **GitHub** | [modelcontextprotocol/servers — memory](https://github.com/modelcontextprotocol/servers/tree/main/src/memory) |
| **Site web** | [modelcontextprotocol.io](https://modelcontextprotocol.io/) |
| **Installation** | `npx -y @modelcontextprotocol/server-memory` |
| **Categorie** | Serveur MCP — Connaissance/IA |
| **Licence** | MIT |
| **Statut** | Actif |
| **Derniere verification** | 2026-03-22 |

---

## Ce que ca fait

Le serveur Memory MCP permet a un client MCP de maintenir une **memoire persistante entre les sessions** en utilisant un graphe de connaissances local. Il stocke des entites (personnes, projets, concepts) et les relations entre elles dans un fichier JSON, permettant de conserver des informations d'une conversation a l'autre.

**Note pour Claude Code** : Claude Code possede son propre systeme de memoire natif (fichiers dans `~/.claude/`). Ce serveur MCP est utile pour :
1. **Claude Desktop** qui n'a pas de memoire native
2. **Partage de connaissances entre outils** — un graphe commun accessible par tous vos clients MCP
3. **Memoire structuree** — le format graphe (entites + relations) est plus riche que les fichiers texte

---

## Fonctionnalites cles

- **Graphe de connaissances** — Entites typees (personne, projet, concept) et relations entre elles
- **Persistance locale** — Stocke dans un fichier JSON, survit entre les sessions
- **CRUD complet** — Creer, lire, mettre a jour et supprimer des entites et relations
- **Recherche** — Trouver des entites par nom, type ou relations

---

## Installation

```json
{
  "mcpServers": {
    "memory": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-memory"],
      "env": {
        "MEMORY_FILE_PATH": "/chemin/vers/memory.json"
      }
    }
  }
}
```

### Prerequis

- Node.js v18+

---

## Liens

- [Depot GitHub](https://github.com/modelcontextprotocol/servers/tree/main/src/memory)

---

*Derniere verification : 2026-03-22 · [Signaler un probleme](../../../.github/ISSUE_TEMPLATE/tool-update.md)*
