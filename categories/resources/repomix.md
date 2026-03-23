# Repomix

> Compresse un codebase entier en format IA avec tree-sitter. Reduction de ~70% des tokens tout en preservant le sens semantique.

| Info | Detail |
|------|--------|
| **GitHub** | [yamadashy/repomix](https://github.com/yamadashy/repomix) |
| **Site web** | Non disponible |
| **Installation** | `npx repomix` |
| **Categorie** | Outil / Contexte |
| **Statut** | Actif |
| **Derniere verification** | 2026-03-22 |

---

## Ce que ca fait

Repomix prend un codebase (local ou GitHub distant) et le compresse en un format optimise pour les LLMs. Au lieu de charger chaque fichier brut (gaspillant des tokens sur l'indentation, les commentaires triviaux et le boilerplate), Repomix utilise **tree-sitter** pour extraire les signatures essentielles et la structure du code, reduisant la consommation de tokens de ~70%.

Fonctionne en CLI et comme serveur MCP.

---

## Fonctionnalites cles

- **Compression tree-sitter** — Extrait les signatures et la structure, elimine le bruit
- **~70% reduction tokens** — Plus de contexte disponible pour le raisonnement
- **Repos distants** — Compresse des repos GitHub sans les cloner
- **Validation securite** — Empeche la fuite de fichiers sensibles
- **CLI + MCP** — Utilisable en ligne de commande ou integre a Claude Code

---

## Installation

```bash
# CLI
npx repomix

# MCP server
npx repomix --mcp
```

---

## Liens

- [Depot GitHub](https://github.com/yamadashy/repomix)

---

*Derniere verification : 2026-03-22 · [Signaler un probleme](../../.github/ISSUE_TEMPLATE/tool-update.md)*
