# gstack

> Le setup Claude Code exact de Garry Tan (CEO de Y Combinator) — 15 outils opinionated transformant Claude en equipe virtuelle avec des roles CEO, Designer, Eng Manager, Release Manager, Doc Engineer et QA.

| Info | Detail |
|------|--------|
| **GitHub** | [garrytan/gstack](https://github.com/garrytan/gstack) |
| **Site web** | Non disponible |
| **Installation** | `git clone` + `./setup` |
| **Categorie** | Framework |
| **Licence** | MIT |
| **Statut** | Actif (mars 2026) |
| **Stars** | ~20k |
| **Derniere verification** | 2026-03-22 |

---

## Ce que ca fait

gstack est le setup Claude Code personnel de Garry Tan, CEO de Y Combinator, rendu open-source en mars 2026. Il a atteint 10 000 etoiles GitHub en 48 heures, prouvant la demande pour des setups opinionated et prets a l'emploi.

L'idee est simple : au lieu de configurer Claude Code de zero, vous installez un ensemble de 15 commandes slash basees sur des **roles concrets** — comme si vous aviez un CEO, un designer, un manager d'ingenierie, un QA et un release manager dans votre equipe. Chaque commande declenche un comportement specialise de Claude.

Le differenciant par rapport a BMAD (qui est un framework methodologique complet) est que gstack est **pragmatique et immediat** : pas de courbe d'apprentissage, pas de phases, juste des commandes slash qui font exactement ce que leur nom dit.

---

## Fonctionnalites cles

- **`/careful`** — Active un mode de protection : Claude avertit avant toute commande destructive (`rm -rf`, `DROP TABLE`, `git push --force`, `kubectl delete`). Indispensable en production
- **`/freeze <repertoire>`** — Verrouille les edits a un seul repertoire pendant le debugging, empechant Claude de toucher au reste du codebase
- **Revue CEO** — Claude fait une revue de haut niveau du projet : direction produit, priorites, risques
- **Revue design** — Claude evalue l'UX/UI, la coherence visuelle, l'accessibilite
- **Code reviewer paranoiaque** — Revue de code ultra-stricte : race conditions, fuites memoire, injections SQL, edge cases
- **QA avec navigateur reel** — Claude lance des tests automatises dans un vrai navigateur, pas juste des assertions en memoire

---

## Installation

```bash
# Cloner dans le repertoire skills de Claude Code
git clone https://github.com/garrytan/gstack.git ~/.claude/skills/gstack

# Lancer le script de setup
cd ~/.claude/skills/gstack && ./setup
```

### Prerequis

- Claude Code CLI installe et authentifie
- Git

---

## Utilisation avec Claude Code

Apres installation, les commandes sont immediatement disponibles :

```bash
# Protection contre les commandes dangereuses
/careful
# Claude demande maintenant confirmation avant rm, DROP, force-push, etc.

# Verrouiller les edits a un repertoire pendant le debug
/freeze src/api/
# Claude ne modifie plus que src/api/, le reste est en lecture seule

# Revue de code paranoiaque sur vos changements
/review
# Claude cherche : race conditions, injections, fuites memoire, edge cases

# Revue CEO : vision macro du projet
/ceo-review
# Claude evalue : direction produit, dette technique, priorites

# QA automatise avec navigateur reel
/qa
# Claude ouvre un navigateur, teste les parcours utilisateur, rapporte les bugs
```

### Quand utiliser gstack vs BMAD

| Situation | Choix |
|-----------|-------|
| Vous voulez un setup rapide sans courbe d'apprentissage | **gstack** |
| Vous voulez un framework agile complet avec phases structurees | **BMAD** |
| Vous avez besoin de roles specialises immediatement | **gstack** |
| Vous construisez un projet enterprise avec specs formelles | **BMAD** |
| Vous pouvez combiner les deux | **gstack** pour les commandes quotidiennes + **BMAD** pour la methodologie |

---

## Configuration

gstack s'installe dans `~/.claude/skills/gstack/`. Chaque commande est un fichier SKILL.md independant que vous pouvez modifier :

```
~/.claude/skills/gstack/
├── setup                    # Script d'installation
├── careful/SKILL.md         # Protection commandes dangereuses
├── freeze/SKILL.md          # Verrouillage de repertoire
├── review/SKILL.md          # Code review paranoiaque
├── ceo-review/SKILL.md      # Revue CEO
├── qa/SKILL.md              # QA navigateur
└── ...                      # 10+ autres commandes
```

Pour personnaliser un comportement, editez le fichier SKILL.md correspondant.

---

## Liens

- [Depot GitHub](https://github.com/garrytan/gstack)
- [Article TechCrunch](https://techcrunch.com/2026/03/17/why-garry-tans-claude-code-setup-has-gotten-so-much-love-and-hate/)

---

*Derniere verification : 2026-03-22 · [Signaler un probleme](../../.github/ISSUE_TEMPLATE/tool-update.md)*
