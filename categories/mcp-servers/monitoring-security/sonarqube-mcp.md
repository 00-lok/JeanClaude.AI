# SonarQube MCP

> Qualite de code et analyse de securite via SonarQube, integree comme serveur MCP. Container Docker gratuit.

| Info | Detail |
|------|--------|
| **GitHub** | [SonarSource/sonarqube-mcp-server](https://github.com/SonarSource/sonarqube-mcp-server) |
| **Site web** | [sonarsource.com](https://www.sonarsource.com/) |
| **Installation** | `docker pull sonarqube-mcp-server` |
| **Categorie** | Serveur MCP — Qualite / Securite |
| **Licence** | LGPL |
| **Statut** | Actif |
| **Derniere verification** | 2026-03-22 |

---

## Ce que ca fait

Integre SonarQube directement dans le workflow Claude Code via MCP. Claude peut analyser des snippets de code a la demande pour detecter bugs, code smells, vulnerabilites de securite et dette technique. Deploiement en minutes via Docker.

---

## Fonctionnalites cles

- **Analyse a la demande** — Claude soumet du code et recoit les resultats instantanement
- **Qualite + Securite** — Bugs, code smells, vulnerabilites, dette technique
- **Docker** — Deploiement en minutes, pas de configuration complexe
- **Multi-langage** — 30+ langages supportes

---

## Installation

```json
{
  "mcpServers": {
    "sonarqube": {
      "command": "docker",
      "args": ["run", "--rm", "-i", "sonarqube-mcp-server"]
    }
  }
}
```

---

## Liens

- [Depot GitHub](https://github.com/SonarSource/sonarqube-mcp-server)

---

*Derniere verification : 2026-03-22 · [Signaler un probleme](../../../.github/ISSUE_TEMPLATE/tool-update.md)*
