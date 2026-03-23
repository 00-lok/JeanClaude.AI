# Git (MCP officiel)

> Serveur MCP officiel fournissant des outils pour lire, chercher et manipuler des depots Git.

| Info | Detail |
|------|--------|
| **GitHub** | [modelcontextprotocol/servers — git](https://github.com/modelcontextprotocol/servers/tree/main/src/git) |
| **Site web** | [modelcontextprotocol.io](https://modelcontextprotocol.io/) |
| **Installation** | `npx -y @modelcontextprotocol/server-git` |
| **Categorie** | Serveur MCP — Outils de dev |
| **Licence** | MIT |
| **Statut** | Actif |
| **Derniere verification** | 2026-03-22 |

---

## Ce que ca fait

Le serveur Git MCP donne a tout client MCP la capacite de travailler avec des depots Git : cloner, lire l'historique de commits, voir les diffs, gerer les branches et effectuer des recherches dans le code source.

**Note pour Claude Code** : Claude Code possede deja des capacites Git natives (Bash + outils integres). Ce serveur MCP est principalement utile dans deux cas :
1. **Claude Desktop** ou d'autres clients MCP qui n'ont pas d'acces natif a Git
2. **Workflows MCP standardises** ou vous voulez que tous vos outils passent par le meme protocole

---

## Fonctionnalites cles

- **Historique de commits** — Parcourir les logs, voir les details, filtrer par auteur/date
- **Diffs** — Comparer des branches, commits ou l'arbre de travail
- **Gestion de branches** — Lister, creer, changer de branche
- **Recherche** — Chercher du texte dans le depot avec `git grep`
- **Statut** — Voir l'etat de l'arbre de travail et de l'index

---

## Installation

```json
{
  "mcpServers": {
    "git": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-git"]
    }
  }
}
```

### Prerequis

- Node.js v18+
- Git installe

---

## Liens

- [Depot GitHub](https://github.com/modelcontextprotocol/servers/tree/main/src/git)
- [Specification MCP](https://modelcontextprotocol.io/specification/2025-11-25)

---

*Derniere verification : 2026-03-22 · [Signaler un probleme](../../../.github/ISSUE_TEMPLATE/tool-update.md)*
