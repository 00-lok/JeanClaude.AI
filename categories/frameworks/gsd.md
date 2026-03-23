# GSD (Get Shit Done)

> Un systeme leger de meta-prompting, context engineering et developpement spec-driven qui resout le "context rot" en executant les taches dans des fenetres de contexte fraiches.

| Info | Detail |
|------|--------|
| **GitHub** | [gsd-build/get-shit-done](https://github.com/gsd-build/get-shit-done) |
| **Site web** | Non disponible |
| **Installation** | `npx get-shit-done-cc@latest` |
| **Categorie** | Framework |
| **Licence** | MIT |
| **Statut** | Actif |
| **Derniere verification** | 2026-03-22 |

---

## Ce que ca fait

GSD resout un probleme critique du developpement assiste par IA : le **context rot**. Au fur et a mesure qu'une conversation grandit et que la fenetre de contexte se remplit, la qualite de la sortie IA se degrade. GSD corrige cela en decoupant les projets en petites taches bien definies, chacune executee dans une **fenetre de contexte fraiche de 200K tokens** par des sous-agents specialises.

Le cycle de workflow est simple : **Discuter → Planifier → Executer → Verifier → Livrer**. GSD utilise des definitions de taches structurees en XML avec des etapes de verification integrees, et orchestre plusieurs agents specialises (chercheurs, planificateurs, executeurs, verificateurs) pour completer chaque tache.

Le contexte est ingenierie a travers des fichiers de documentation curates (`PROJECT.md`, `REQUIREMENTS.md`, `ROADMAP.md`, `STATE.md`) qui alimentent chaque session fraiche avec exactement le contexte necessaire — ni plus, ni moins.

---

## Fonctionnalites cles

- **Contexte frais par tache** — Chaque tache s'execute dans une fenetre de contexte propre de 200K tokens, eliminant la degradation de qualite
- **Orchestration multi-agents** — Agents specialises pour la recherche, la planification, l'execution et la verification
- **Taches structurees XML** — Definitions de taches bien definies avec entrees, sorties et criteres de verification
- **Execution en vagues paralleles** — Les taches independantes s'executent simultanement
- **Commits Git atomiques** — Un commit par tache completee pour un historique propre
- **Context engineering** — Docs curates (PROJECT.md, REQUIREMENTS.md, ROADMAP.md, STATE.md) alimentent chaque session

---

## Installation

```bash
# GSD v1 — Commandes slash Claude Code
npx get-shit-done-cc@latest

# GSD v2 — CLI autonome via Pi SDK
npm install -g gsd-pi@latest
```

### Prerequis

- Node.js v18+
- CLI Claude Code (pour v1) ou autonome (pour v2)

### GSD v1 vs v2

| Aspect | v1 | v2 |
|--------|----|----|
| Runtime | Commandes slash Claude Code | CLI autonome via Pi SDK |
| Contexte | Depend de la gestion du contexte LLM | Session fraiche par tache |
| Automatisation | Boucle auto du LLM | Machine a etats lisant des fichiers disque |
| Recuperation | Aucune | Fichiers de verrouillage + forensics de session |
| Strategie Git | Le LLM ecrit les commandes git | Isolation worktree avec squash merge |

---

## Utilisation avec Claude Code

```bash
# Demarrer le workflow GSD
/gsd

# Planifier les taches a partir des exigences
/gsd plan

# Executer les taches automatiquement
/gsd execute

# GSD v2 : Mode autonome
/gsd auto

# GSD v2 : Interface web
gsd --web
```

### Cycle de workflow

1. **Discuter** — Definir ce que vous voulez construire, clarifier les exigences
2. **Planifier** — GSD decoupe le travail en taches atomiques et bien definies
3. **Executer** — Chaque tache s'execute dans un contexte frais avec des agents specialises
4. **Verifier** — Verifications integrees que chaque tache respecte ses criteres
5. **Livrer** — Commits atomiques, historique git propre, pret a deployer

---

## Configuration

GSD utilise des fichiers de documentation au niveau du projet pour le context engineering :

```
projet/
├── PROJECT.md        # Vue d'ensemble et objectifs du projet
├── REQUIREMENTS.md   # Exigences fonctionnelles et non-fonctionnelles
├── ROADMAP.md        # Jalons et priorites
└── STATE.md          # Etat actuel du projet (mis a jour automatiquement)
```

---

## Ecosysteme

| Depot | Description |
|-------|-------------|
| [gsd-build/gsd-2](https://github.com/gsd-build/gsd-2) | GSD v2 — CLI autonome avec recuperation de crash et interface web |
| [itsjwill/GSD-2.0-Get-Shit-Done-Cost-saver-](https://github.com/itsjwill/GSD-2.0-Get-Shit-Done-Cost-saver-) | Fork communautaire avec intelligence multi-modeles et optimisation des couts |
| [rokicool/gsd-opencode](https://github.com/rokicool/gsd-opencode) | GSD adapte pour OpenCode |

---

## Liens

- [Depot GitHub](https://github.com/gsd-build/get-shit-done)
- [Depot GSD v2](https://github.com/gsd-build/gsd-2)
- [Guide du debutant (DEV Community)](https://dev.to/alikazmidev/the-complete-beginners-guide-to-gsd-get-shit-done-framework-for-claude-code-24h0)

---

*Derniere verification : 2026-03-22 · [Signaler un probleme](../../.github/ISSUE_TEMPLATE/tool-update.md)*
