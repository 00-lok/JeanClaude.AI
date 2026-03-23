# Semgrep MCP

> Analyse statique deterministe avec 5 000+ regles, integree comme serveur MCP. Scanne chaque fichier genere par l'agent pour les vulnerabilites, les secrets et les problemes de qualite.

| Info | Detail |
|------|--------|
| **GitHub** | [semgrep/mcp](https://github.com/semgrep/mcp) |
| **Site web** | [semgrep.dev](https://semgrep.dev/) |
| **Installation** | Voir ci-dessous |
| **Categorie** | Serveur MCP — Securite |
| **Licence** | LGPL |
| **Statut** | Actif |
| **Derniere verification** | 2026-03-22 |

---

## Ce que ca fait

Semgrep MCP integre l'analyse statique Semgrep directement dans le workflow Claude Code. Contrairement aux revues basees sur LLM (qui peuvent rater des patterns), Semgrep utilise une analyse **deterministe** — un pattern qu'il a une regle pour sera TOUJOURS detecte, sans exception.

Le serveur combine trois capacites : Semgrep Code (SAST), Semgrep Supply Chain (vulnerabilites des dependances), et Semgrep Secrets (detection de cles et tokens exposes).

---

## Fonctionnalites cles

- **5 000+ regles** — Couvrant OWASP Top 10, CWE, et patterns specifiques par langage
- **Deterministe** — Pas de faux negatifs sur les patterns couverts (contrairement aux LLMs)
- **SAST + Supply Chain + Secrets** — Trois types d'analyse en un serveur
- **Multi-langage** — Python, JavaScript, TypeScript, Go, Java, Ruby, et plus

---

## Installation

```json
{
  "mcpServers": {
    "semgrep": {
      "command": "npx",
      "args": ["-y", "@semgrep/mcp-server"],
      "env": {
        "SEMGREP_APP_TOKEN": "votre_token"
      }
    }
  }
}
```

---

## Liens

- [Depot GitHub](https://github.com/semgrep/mcp)
- [Semgrep](https://semgrep.dev/)

---

*Derniere verification : 2026-03-22 · [Signaler un probleme](../../../.github/ISSUE_TEMPLATE/tool-update.md)*
