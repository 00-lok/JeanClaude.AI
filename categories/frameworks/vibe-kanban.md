# Vibe Kanban

> Outil de gestion de taches et d'orchestration base sur le kanban qui permet de planifier, executer avec des agents IA, revoir les diffs et previsualiser votre app — le tout dans une seule interface.

| Info | Detail |
|------|--------|
| **GitHub** | [BloopAI/vibe-kanban](https://github.com/BloopAI/vibe-kanban) |
| **Site web** | [vibekanban.com](https://vibekanban.com/) |
| **Installation** | `npx vibe-kanban` |
| **Categorie** | Framework |
| **Licence** | MIT |
| **Statut** | Actif |
| **Derniere verification** | 2026-03-22 |

---

## Ce que ca fait

Vibe Kanban fait le pont entre la gestion de projet et le coding IA. Il fournit un tableau kanban visuel ou vous planifiez le travail sous forme d'issues, puis creez des **espaces de travail dedies** ou chaque agent IA obtient sa propre branche, son terminal et son serveur de dev. Vous pouvez revoir les diffs generes avec des commentaires en ligne, previsualiser votre app dans un navigateur integre, et merger via la creation native de PR.

Le differenciant cle est l'**interface tout-en-un** : au lieu de basculer entre un tableau de taches, un terminal, un outil de revue de code et un navigateur, Vibe Kanban consolide tout dans un flux unique. Il supporte 10+ agents de coding, donc vous n'etes pas verrouille sur Claude Code seul.

---

## Fonctionnalites cles

- **Tableau kanban** — Planification et priorisation visuelle des issues
- **Espaces de travail dedies** — Chaque agent obtient sa propre branche, terminal et serveur de dev
- **Revue de code integree** — Revoir les diffs generes avec commentaires en ligne
- **Apercu navigateur integre** — Navigateur avec devtools, mode inspection et emulation d'appareils
- **Support 10+ agents** — Claude Code, Codex, Gemini CLI, GitHub Copilot, Amp, Cursor, OpenCode, Droid, CCR, Qwen Code
- **Creation native de PR** — Creer des pull requests directement depuis l'interface avec integration GitHub

---

## Installation

```bash
npx vibe-kanban
```

### Prerequis

- Node.js v18+
- Au moins un agent de coding supporte installe (Claude Code, Codex, etc.)
- Git initialise dans votre projet

---

## Utilisation avec Claude Code

```bash
# Lancer Vibe Kanban dans votre projet
npx vibe-kanban

# L'interface s'ouvre dans votre navigateur
# 1. Creer des issues sur le tableau kanban
# 2. Creer un espace de travail → selectionner Claude Code comme agent
# 3. Claude Code travaille sur sa propre branche avec un terminal
# 4. Revoir le diff une fois termine
# 5. Previsualiser le resultat dans le navigateur integre
# 6. Creer une PR pour merger
```

### Workflow

1. **Planifier** — Creer des issues kanban pour definir les elements de travail
2. **Executer** — Creer des espaces de travail ou Claude Code obtient une branche, un terminal et un serveur de dev dedies
3. **Revoir** — Examiner les diffs generes avec commentaires en ligne
4. **Previsualiser** — Tester dans le navigateur integre avec devtools et emulation d'appareils
5. **Merger** — Creer des PR et merger directement depuis l'interface

---

## Configuration

Vibe Kanban detecte automatiquement la configuration de votre projet. La configuration se fait principalement via l'interface web.

Pour les parametres specifiques a l'agent, configurez vos agents comme d'habitude (ex : `CLAUDE.md` pour Claude Code).

---

## Liens

- [Depot GitHub](https://github.com/BloopAI/vibe-kanban)
- [Site web](https://vibekanban.com/)

---

*Derniere verification : 2026-03-22 · [Signaler un probleme](../../.github/ISSUE_TEMPLATE/tool-update.md)*
