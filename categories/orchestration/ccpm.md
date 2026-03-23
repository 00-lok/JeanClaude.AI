# CCPM (Claude Code Project Manager)

> Systeme de gestion de projet pour agents IA qui utilise GitHub Issues comme source de taches et Git worktrees pour l'execution parallele.

| Info | Detail |
|------|--------|
| **GitHub** | [automazeio/ccpm](https://github.com/automazeio/ccpm) |
| **Site web** | Non disponible |
| **Installation** | Skill Claude Code (voir ci-dessous) |
| **Categorie** | Orchestration / Gestion de projet |
| **Licence** | MIT |
| **Statut** | Actif |
| **Stars** | ~7.6k |
| **Derniere verification** | 2026-03-22 |

---

## Ce que ca fait

CCPM connecte la **gestion de projet (GitHub Issues)** a l'**execution par agents IA (Git worktrees)**. Le principe : chaque issue GitHub devient une tache assignable a un agent qui travaille dans un Git worktree dedie — une copie isolee du depot avec sa propre branche.

Pourquoi c'est utile : la traceabilite. Chaque tache a une issue (spec), un worktree (execution), une branche (code) et une PR (livraison). Tout est lie, tout est traçable, tout est dans GitHub. Pas de systeme externe, pas d'outil supplementaire.

CCPM fonctionne avec Claude Code, Amp, OpenCode, Codex, Cursor et d'autres agents.

---

## Fonctionnalites cles

- **GitHub Issues = Taches** — Chaque issue devient une tache executable par un agent
- **Git worktrees = Isolation** — Chaque agent travaille dans sa propre copie du depot
- **Traceabilite complete** — Issue → Branche → Worktree → PR, tout est lie
- **Execution parallele** — Plusieurs agents sur plusieurs issues en meme temps
- **Spec dans l'issue** — La specification de la tache est directement dans l'issue GitHub
- **Multi-agents** — Compatible Claude Code, Amp, OpenCode, Codex, Cursor

---

## Installation

```bash
# Cloner le depot CCPM
git clone https://github.com/automazeio/ccpm.git

# Copier les skills dans votre projet
cp -r ccpm/.claude/skills/ .claude/skills/

# Ou installer comme skill global
cp -r ccpm/.claude/skills/ ~/.claude/skills/
```

### Prerequis

- Claude Code CLI installe
- Git
- Acces au depot GitHub (pour les issues)
- GitHub CLI (`gh`) recommande

---

## Utilisation avec Claude Code

```bash
# 1. Creer des issues GitHub pour vos taches
gh issue create --title "Ajouter l'authentification JWT" --body "Spec : ..."
gh issue create --title "Creer l'endpoint /users" --body "Spec : ..."

# 2. Lister les taches disponibles
/ccpm list

# 3. Lancer un agent sur une tache (cree un worktree automatiquement)
/ccpm start #1
# → Cree un worktree : .worktrees/issue-1-auth-jwt/
# → Cree une branche : feature/issue-1-auth-jwt
# → Claude Code travaille dans le worktree isole

# 4. Suivre l'avancement
/ccpm status
# Issue #1 : En cours (branche feature/issue-1-auth-jwt)
# Issue #2 : En attente

# 5. Quand c'est termine, creer la PR
/ccpm pr #1
# → Cree une PR depuis feature/issue-1-auth-jwt vers main
# → Lie la PR a l'issue #1
```

### Workflow avec plusieurs agents

```
Issue #1 ──→ Worktree 1 ──→ Agent Claude Code ──→ PR #1
Issue #2 ──→ Worktree 2 ──→ Agent Claude Code ──→ PR #2
Issue #3 ──→ Worktree 3 ──→ Agent OpenCode   ──→ PR #3
                    ↓
            Tout est isole, pas de conflits
```

---

## Configuration

CCPM se configure dans les fichiers SKILL.md installes. Les parametres principaux :

- **Repertoire worktrees** — Ou creer les copies isolees (defaut : `.worktrees/`)
- **Convention de branche** — Format des noms de branche (defaut : `feature/issue-{id}-{slug}`)
- **Labels GitHub** — Quels labels d'issues utiliser pour filtrer les taches

---

## Liens

- [Depot GitHub](https://github.com/automazeio/ccpm)

---

*Derniere verification : 2026-03-22 · [Signaler un probleme](../../.github/ISSUE_TEMPLATE/tool-update.md)*
