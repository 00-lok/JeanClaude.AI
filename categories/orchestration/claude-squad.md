# Claude Squad

> Application terminal qui gere plusieurs agents IA (Claude Code, Codex, Gemini) travaillant en parallele dans des espaces de travail Git isoles.

| Info | Detail |
|------|--------|
| **GitHub** | [smtg-ai/claude-squad](https://github.com/smtg-ai/claude-squad) |
| **Site web** | Non disponible |
| **Installation** | `brew install smtg-ai/tap/claude-squad` |
| **Categorie** | Orchestration |
| **Licence** | MIT |
| **Statut** | Actif |
| **Derniere verification** | 2026-03-22 |

---

## Ce que ca fait

Claude Squad resout le probleme de la **parallelisation** : vous avez plusieurs taches independantes (corriger un bug, ajouter une feature, refactoriser un module) et vous voulez que plusieurs agents IA y travaillent en meme temps sans se marcher dessus.

Claude Squad cree une session tmux par agent, chacune avec son propre **Git worktree** (une copie isolee du depot). L'agent travaille sur sa branche, dans son repertoire, sans affecter les autres. Vous surveillez toutes les sessions depuis un tableau de bord terminal unique.

Concretement : vous lancez 3 sessions Claude Code en parallele, chacune sur une tache differente, et vous voyez leur progression en temps reel dans votre terminal.

---

## Fonctionnalites cles

- **Sessions paralleles** — Lancer N agents en meme temps, chacun sur une tache
- **Isolation Git worktree** — Chaque agent travaille dans sa propre copie du depot, sa propre branche
- **Tableau de bord terminal** — Vue d'ensemble de tous les agents, leur statut, leur progression
- **Multi-backend** — Supporte Claude Code, Codex, Gemini CLI et d'autres agents locaux
- **Base tmux** — Interface legere, fonctionne dans n'importe quel terminal

---

## Installation

```bash
# Via Homebrew (macOS/Linux)
brew install smtg-ai/tap/claude-squad

# Via Go
go install github.com/smtg-ai/claude-squad@latest
```

### Prerequis

- Homebrew ou Go 1.21+
- tmux installe (`brew install tmux` ou `apt install tmux`)
- Au moins un agent IA installe (Claude Code recommande)
- Git initialise dans votre projet

---

## Utilisation avec Claude Code

```bash
# Lancer Claude Squad
claude-squad

# L'interface terminal s'ouvre avec le tableau de bord
# Raccourcis :
#   n    → Nouvelle session (choisir l'agent et la tache)
#   d    → Detacher une session
#   q    → Quitter
#   ↑/↓  → Naviguer entre les sessions
#   Enter → Entrer dans une session

# Exemple concret : 3 taches en parallele
# Session 1 : "Corrige le bug #142 dans le module auth"
# Session 2 : "Ajoute la pagination a l'endpoint /users"
# Session 3 : "Ecris les tests unitaires pour le service de paiement"

# Chaque session a :
# - Sa propre branche Git (ex: squad/session-1, squad/session-2)
# - Son propre worktree (copie isolee du repo)
# - Son propre agent Claude Code
```

### Workflow typique

```
1. Lancer claude-squad
2. Creer 3 sessions avec 3 taches independantes
3. Chaque agent travaille dans son worktree isole
4. Surveiller la progression dans le tableau de bord
5. Quand un agent termine → revoir son diff → merger sa branche
6. Repeter avec de nouvelles taches
```

---

## Configuration

Claude Squad cree automatiquement les worktrees dans un repertoire temporaire. Configuration via variables d'environnement :

```bash
# Repertoire pour les worktrees (defaut: /tmp/claude-squad/)
export CLAUDE_SQUAD_WORKTREE_DIR="/path/to/worktrees"

# Agent par defaut
export CLAUDE_SQUAD_DEFAULT_AGENT="claude-code"
```

---

## Liens

- [Depot GitHub](https://github.com/smtg-ai/claude-squad)

---

*Derniere verification : 2026-03-22 · [Signaler un probleme](../../.github/ISSUE_TEMPLATE/tool-update.md)*
