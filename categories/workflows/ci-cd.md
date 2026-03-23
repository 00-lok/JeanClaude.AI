# CI/CD avec Claude Code

> Integrations GitHub Actions et automatisation de pipelines avec Claude Code.

---

## Claude Code Action (GitHub Action officielle)

| Info | Detail |
|------|--------|
| **GitHub** | [anthropics/claude-code-action](https://github.com/marketplace/actions/claude-code-action-official) |
| **Installation** | `anthropics/claude-code-action@v1` |
| **Statut** | Actif |

### Ce que ca fait

L'action GitHub officielle d'Anthropic qui execute Claude Code dans les pipelines CI/CD. Elle se declenche sur les evenements de PR, analyse les diffs, et publie ses conclusions directement sur les PRs.

### Fonctionnalites cles

- **Revue automatisee de PR** — Claude analyse les changements et commente la PR
- **Implementation d'issues** — Claude peut implementer des fonctionnalites a partir d'issues
- **Audits de securite** — Analyse automatique de vulnerabilites sur les PRs
- **Contexte CLAUDE.md** — Utilise la configuration de votre projet
- **Declenchement @claude** — Mentionnez `@claude` dans une PR pour declencher l'action

### Exemple de workflow

```yaml
name: Claude Code Review
on:
  pull_request:
    types: [opened, synchronize]
  issue_comment:
    types: [created]

jobs:
  review:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: anthropics/claude-code-action@v1
        with:
          anthropic_api_key: ${{ secrets.ANTHROPIC_API_KEY }}
```

---

## Documentation officielle

- [Claude Code GitHub Actions](https://code.claude.com/docs/en/github-actions) — Guide officiel pour executer Claude Code dans GitHub Actions
- [Claude Code Action Marketplace](https://github.com/marketplace/actions/claude-code-action-official) — Page du marketplace

---

*Derniere verification : 2026-03-22 · [Signaler un probleme](../../.github/ISSUE_TEMPLATE/tool-update.md)*
