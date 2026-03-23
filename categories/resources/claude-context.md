# claude-context

> Recherche semantique dans le codebase via embeddings hybrides BM25 + vecteurs. ~40% reduction de tokens vs lecture naive de fichiers.

| Info | Detail |
|------|--------|
| **GitHub** | [zilliztech/claude-context](https://github.com/zilliztech/claude-context) |
| **Installation** | Serveur MCP (voir ci-dessous) |
| **Categorie** | MCP / Contexte |
| **Stars** | ~5.6k |
| **Statut** | Actif |
| **Derniere verification** | 2026-03-22 |

---

## Ce que ca fait

claude-context transforme votre codebase en une base de donnees semantique interrogeable par Claude. Au lieu de charger des fichiers entiers par grep/glob (bruyant et couteux en tokens), Claude peut faire une **recherche semantique** : "trouve le code qui gere l'authentification" retourne exactement les fonctions pertinentes, pas des fichiers entiers.

Utilise des embeddings hybrides BM25 (mots-cles) + vecteurs denses (sens semantique) pour une precision maximale, avec ~40% de tokens en moins qu'une lecture de fichiers naive.

Version locale disponible : [FarhanAliRaza/claude-context-local](https://github.com/FarhanAliRaza/claude-context-local) — zero API externe, tout reste sur votre machine.

---

## Fonctionnalites cles

- **Recherche semantique** — Par sens, pas juste par mots-cles
- **Embeddings hybrides** — BM25 + vecteurs denses pour precision maximale
- **~40% reduction tokens** — Plus de contexte pour le raisonnement
- **Indexation automatique** — Le codebase est indexe une fois, mis a jour incrementalement

---

## Installation

```json
{
  "mcpServers": {
    "claude-context": {
      "command": "npx",
      "args": ["-y", "claude-context-mcp"]
    }
  }
}
```

---

## Liens

- [Depot GitHub](https://github.com/zilliztech/claude-context)
- [Version locale](https://github.com/FarhanAliRaza/claude-context-local)

---

*Derniere verification : 2026-03-22 · [Signaler un probleme](../../.github/ISSUE_TEMPLATE/tool-update.md)*
