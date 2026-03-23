# RALPH

> Boucle de developpement IA autonome pour Claude Code avec detection intelligente de sortie, rate limiting et recuperation de crash.

| Info | Detail |
|------|--------|
| **GitHub** | [frankbria/ralph-claude-code](https://github.com/frankbria/ralph-claude-code) |
| **Site web** | Non disponible |
| **Installation** | `git clone` + `./install.sh` |
| **Categorie** | Framework |
| **Licence** | MIT |
| **Statut** | Actif (v0.11.5) |
| **Derniere verification** | 2026-03-22 |

---

## Ce que ca fait

RALPH resout un probleme concret : comment laisser Claude Code travailler **de maniere autonome pendant de longues periodes** sans supervision constante, tout en evitant les boucles infinies et la surconsommation d'API.

Le principe est une boucle iterative : RALPH lance Claude Code, attend la completion d'une etape, verifie si le travail global est termine, et relance si necessaire. La cle est sa **porte de sortie a double condition** — RALPH ne s'arrete que lorsque deux criteres sont simultanement remplis :
1. Des **indicateurs de completion** detectes dans la sortie de Claude (tests qui passent, build reussi, etc.)
2. Un **signal EXIT explicite** emis par Claude lui-meme

Cette double condition evite l'arret premature (Claude dit "j'ai fini" alors qu'il reste du travail) et la boucle infinie (Claude tourne en rond sans jamais emettre le signal).

RALPH est egalement disponible comme plugin officiel dans le depot Anthropic (`anthropics/claude-code/plugins/ralph-wiggum`).

---

## Fonctionnalites cles

- **Double condition de sortie** — Indicateurs de completion + signal EXIT_SIGNAL, les deux requis pour arreter
- **Rate limiting configurable** — 100 appels/heure par defaut avec disjoncteur automatique pour eviter les factures surprises
- **Installation globale** — Installer une fois, utiliser dans n'importe quel projet avec `ralph-setup`
- **Recuperation de crash** — Si le processus plante, RALPH peut reprendre la ou il s'est arrete
- **566 tests, 100% de reussite** — Fiabilite verifiee par une couverture de tests complete

---

## Installation

```bash
# Installation globale (une seule fois)
git clone https://github.com/frankbria/ralph-claude-code.git
cd ralph-claude-code && ./install.sh

# Initialisation dans un projet specifique
cd mon-projet
ralph-setup
```

### Prerequis

- Claude Code CLI installe et authentifie
- Bash
- Git

---

## Utilisation avec Claude Code

```bash
# Lancer RALPH sur une tache
ralph "Implemente le systeme d'authentification JWT avec refresh tokens"

# RALPH va :
# 1. Lancer Claude Code avec le prompt
# 2. Attendre que Claude termine une iteration
# 3. Verifier les indicateurs de completion
# 4. Relancer si le travail n'est pas fini
# 5. S'arreter quand double condition remplie (completion + EXIT_SIGNAL)

# Configurer le rate limiting
ralph --max-calls 50 --interval 3600 "Refactorise le module de paiement"

# Mode verbose pour voir ce que RALPH fait
ralph --verbose "Corrige tous les tests qui echouent"
```

### Quand utiliser RALPH

| Situation | RALPH est adapte ? |
|-----------|-------------------|
| Tache longue et autonome (plusieurs heures) | Oui |
| Tache rapide et interactive (quelques minutes) | Non — utilisez Claude Code directement |
| Vous devez superviser chaque etape | Non — RALPH est fait pour l'autonomie |
| Vous voulez limiter les couts API | Oui — rate limiting integre |

---

## Configuration

RALPH se configure via un fichier `.ralph.config` dans votre projet :

```bash
# .ralph.config
MAX_CALLS_PER_HOUR=100    # Limite d'appels par heure
CIRCUIT_BREAKER=true       # Disjoncteur automatique
VERBOSE=false              # Mode verbose
EXIT_SIGNAL="EXIT_SIGNAL"  # Signal de sortie personnalise
```

---

## Liens

- [Depot GitHub](https://github.com/frankbria/ralph-claude-code)
- [Plugin officiel Anthropic](https://github.com/anthropics/claude-code/tree/main/plugins/ralph-wiggum)

---

*Derniere verification : 2026-03-22 · [Signaler un probleme](../../.github/ISSUE_TEMPLATE/tool-update.md)*
