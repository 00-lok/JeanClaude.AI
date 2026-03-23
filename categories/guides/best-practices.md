# Bonnes pratiques

> Configuration, workflows et conventions pour utiliser Claude Code de maniere optimale.

---

## Depots de bonnes pratiques

| Depot | Description |
|-------|-------------|
| [shanraisshan/claude-code-best-practice](https://github.com/shanraisshan/claude-code-best-practice) | Implementation de reference avec skills, subagents, hooks et commandes |
| [awattar/claude-code-best-practices](https://github.com/awattar/claude-code-best-practices) | Patterns, exemples et commandes slash personnalisees |
| [rosmur/claudecode-best-practices](https://rosmur.github.io/claudecode-best-practices/) | Guide web synthetisant les meilleures pratiques |
| [steipete/agent-rules](https://github.com/steipete/agent-rules) | Regles cross-agents (Claude Code, Cursor, etc.) |

---

## Configuration recommandee

### Structure de projet

```
projet/
├── CLAUDE.md              # Instructions pour Claude Code
├── CLAUDE.local.md         # Instructions locales (non commitees)
├── .claude/
│   ├── settings.json       # Parametres projet
│   ├── settings.local.json # Parametres locaux (non commites)
│   ├── skills/             # Skills personnalises
│   │   └── 01/SKILL.md
│   └── commands/           # Commandes slash personnalisees
│       └── review.md
```

### Fichiers a ne PAS commiter

```gitignore
# .gitignore
CLAUDE.local.md
.claude/settings.local.json
```

---

## Workflow recommande

### Pour une nouvelle fonctionnalite

1. **Planifier** — Decrire la fonctionnalite, demander a Claude de planifier (mode plan)
2. **Valider le plan** — Verifier et ajuster avant l'implementation
3. **Implementer** — Laisser Claude implementer etape par etape
4. **Tester** — Demander a Claude de lancer les tests
5. **Revoir** — Utiliser `git diff` pour revoir les changements
6. **Commiter** — Commiter une fois satisfait

### Pour un bug fix

1. **Reproduire** — Fournir l'erreur complete a Claude
2. **Diagnostiquer** — Laisser Claude analyser la cause racine
3. **Corriger** — Implementation du fix
4. **Verifier** — Lancer les tests pour confirmer le fix
5. **Regression** — Ajouter un test pour prevenir la regression

---

## Outils de conversion de regles

| Outil | Description |
|-------|-------------|
| **rulesync** | CLI de gestion unifiee supportant Copilot, Cursor, Cline, Claude Code, Roo Code |
| **rule-porter** | CLI zero-dependance convertissant `.mdc` (Cursor) en CLAUDE.md |

---

## Documentation officielle

- [Best Practices](https://code.claude.com/docs/en/best-practices)
- [Common Workflows](https://code.claude.com/docs/en/common-workflows)
- [Setup Guide](https://code.claude.com/docs/en/setup)

---

*Derniere verification : 2026-03-22 · [Signaler un probleme](../../.github/ISSUE_TEMPLATE/tool-update.md)*
