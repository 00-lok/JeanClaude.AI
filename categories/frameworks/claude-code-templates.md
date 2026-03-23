# Claude Code Templates

> Une collection de 100+ configurations pretes a l'emploi — agents, commandes, integrations MCP, parametres, hooks et skills pour Claude Code.

| Info | Detail |
|------|--------|
| **GitHub** | [davila7/claude-code-templates](https://github.com/davila7/claude-code-templates) |
| **Site web** | [aitmpl.com](https://www.aitmpl.com/) |
| **Installation** | `npx claude-code-templates@latest` |
| **Categorie** | Framework |
| **Licence** | MIT |
| **Statut** | Actif |
| **Derniere verification** | 2026-03-22 |

---

## Ce que ca fait

Claude Code Templates est la plus grande collection de configurations pre-construites pour Claude Code. Au lieu de construire votre setup de zero, vous parcourez et installez des templates pour des cas d'usage specifiques — des agents de developpement frontend aux skills d'audit de securite, des connexions MCP PostgreSQL aux hooks pre-commit.

Le projet fournit un navigateur CLI interactif qui permet de chercher, filtrer et installer des templates par categorie. Il inclut egalement un tableau de bord analytique pour surveiller les sessions Claude Code en temps reel.

Pensez-y comme un **app store pour les configurations Claude Code** : chaque template est un setup teste et pret a l'emploi que vous installez avec une seule commande.

---

## Fonctionnalites cles

- **48+ agents** — Configurations IA specialisees pour l'audit de securite, l'optimisation de performance, le developpement frontend/backend, et plus
- **36 skills de roles professionnels** — Skills specifiques pour l'ingenierie, le marketing, le produit, la conformite
- **Integrations MCP** — Connexions pre-configurees vers GitHub, PostgreSQL, Stripe, AWS, OpenAI
- **Commandes personnalisees** — Commandes slash comme `/generate-tests`, `/optimize-bundle`
- **Hooks** — Declencheurs d'automatisation comme la validation pre-commit, l'auto-formatage
- **Tableau de bord analytique** — Surveillance de session en temps reel, suivi des conversations, bilans de sante
- **139 skills scientifiques** — Skills specialises pour la biologie, la chimie et la medecine

---

## Installation

```bash
# Navigateur interactif — parcourir et selectionner quoi installer
npx claude-code-templates@latest

# Installer un agent specifique
npx claude-code-templates@latest --agent development-team/frontend-developer --yes

# Installer une commande specifique
npx claude-code-templates@latest --command generate-tests --yes

# Installer une integration MCP specifique
npx claude-code-templates@latest --mcp github --yes

# Installer un skill specifique
npx claude-code-templates@latest --skill pdf-processing --yes
```

### Prerequis

- Node.js v18+
- CLI Claude Code installe

---

## Utilisation avec Claude Code

Apres l'installation des templates, ils s'integrent directement avec Claude Code :

```bash
# Les agents deviennent disponibles en tant que skills
# Les commandes deviennent disponibles en tant que commandes slash
# Les integrations MCP se configurent automatiquement dans les parametres
# Les hooks s'enregistrent automatiquement dans le systeme de hooks

# Exemple : utiliser une commande installee
/generate-tests
/optimize-bundle
```

### Categories de templates

| Categorie | Contenu |
|-----------|---------|
| Agents | Frontend, backend, fullstack, securite, performance, DevOps |
| Commandes | Generation de tests, optimisation de code, documentation |
| MCPs | GitHub, PostgreSQL, Stripe, AWS, OpenAI, Slack |
| Parametres | Timeouts, memoire, styles de sortie |
| Hooks | Validation pre-commit, auto-formatage, linting |
| Skills | Traitement PDF, automatisation Excel, domaines scientifiques |

---

## Configuration

Les templates s'installent dans le repertoire `.claude/` de votre projet. Vous pouvez personnaliser tout template installe en editant les fichiers generes.

Parcourez les templates disponibles sur [aitmpl.com](https://www.aitmpl.com/).

---

## Projets lies

| Depot | Description |
|-------|-------------|
| [scotthavird/claude-code-template](https://github.com/scotthavird/claude-code-template) | Template de demarrage avec devcontainer, journalisation de hooks, analytique |
| [abhishekray07/claude-md-templates](https://github.com/abhishekray07/claude-md-templates) | Bonnes pratiques et templates CLAUDE.md |
| [FlorianBruniaux/claude-code-ultimate-guide](https://github.com/FlorianBruniaux/claude-code-ultimate-guide) | Guide complet avec templates de production |

---

## Liens

- [Depot GitHub](https://github.com/davila7/claude-code-templates)
- [Navigateur de templates (aitmpl.com)](https://www.aitmpl.com/)

---

*Derniere verification : 2026-03-22 · [Signaler un probleme](../../.github/ISSUE_TEMPLATE/tool-update.md)*
