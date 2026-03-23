# Comparatif des frameworks

> Guide de comparaison detaille pour choisir le bon framework Claude AI selon votre contexte.

---

## Vue d'ensemble

| Critere | BMAD | GSD | Vibe Kanban | Templates | gstack | Spec Kit | RALPH |
|---------|------|-----|-------------|-----------|--------|----------|-------|
| **Complexite setup** | Elevee | Moyenne | Faible | Faible | Faible | Faible | Faible |
| **Courbe d'apprentissage** | 2-3 jours | 1 jour | 30 min | 10 min | 10 min | 1 heure | 30 min |
| **Taille projet ideale** | Enterprise | Moyen-Large | Tout | Tout | Tout | Moyen | Moyen-Large |
| **Travail en equipe** | Oui (agents = equipe) | Non | Oui (multi-agents) | Non | Non | Oui | Non |
| **Gestion du contexte** | YAML optimise | Contextes frais | Non | Non | Non | Specs versionnees | Boucle auto |
| **Approche** | Agile structuree | Spec-driven | Kanban visuel | Config pre-faites | Roles opinionated | Spec formelle | Autonome |

---

## Decision rapide

```
Vous debutez avec Claude Code ?
  └─→ Claude Code Templates (setup en 10 min)

Projet solo, taches quotidiennes ?
  └─→ gstack (commandes pratiques immediates)

Projet avec specs claires et equipe ?
  └─→ Spec Kit (specs comme reference unique)

Projet enterprise avec phases structurees ?
  └─→ BMAD Method (equipe agile complete)

Projet long avec degradation de qualite ?
  └─→ GSD (contextes frais par tache)

Besoin de gestion visuelle multi-agents ?
  └─→ Vibe Kanban (kanban + workspaces)

Taches autonomes longue duree ?
  └─→ RALPH (boucle autonome avec garde-fous)
```

---

## Combinaisons recommandees

Les frameworks ne sont pas mutuellement exclusifs. Voici les combinaisons qui fonctionnent bien :

### BMAD + Vibe Kanban
**Cas d'usage** : Projet enterprise avec gestion visuelle

BMAD fournit la methodologie (agents, phases, specs) et Vibe Kanban fournit l'interface visuelle (kanban, review, preview). BMAD planifie, Vibe Kanban execute et visualise.

```
BMAD (Planification)          Vibe Kanban (Execution)
├── Business Analyst   ──→    Issue kanban #1
├── Product Manager    ──→    Issue kanban #2
├── System Architect   ──→    Issue kanban #3
└── Developer          ──→    Workspace avec agent
```

### GSD + CCPM
**Cas d'usage** : Projet long avec traceabilite GitHub

GSD gere le context engineering (contextes frais par tache) et CCPM gere la traceabilite (issues → worktrees → PRs). Chaque tache GSD devient une issue CCPM.

```
GSD (Context engineering)     CCPM (Traceabilite)
├── Discuss        ──→        Issue GitHub
├── Plan           ──→        Specs dans l'issue
├── Execute        ──→        Worktree isole
├── Verify         ──→        Tests + validation
└── Ship           ──→        PR liee a l'issue
```

### Spec Kit + BMAD
**Cas d'usage** : Projet avec specs formelles et execution agile

Spec Kit definit la reference unique (principes, exigences, plan) et BMAD fournit les agents pour executer contre ces specs. Les specs Spec Kit deviennent le contexte des agents BMAD.

```
Spec Kit (Reference)          BMAD (Execution)
├── Principles     ──→        Contexte pour tous les agents
├── Requirements   ──→        Input du Product Manager
├── Plan           ──→        Input du System Architect
└── Tasks          ──→        Input du Developer
```

### gstack + Claude Squad
**Cas d'usage** : Travail quotidien avec parallelisation

gstack fournit les commandes pratiques (`/careful`, `/freeze`, `/review`) et Claude Squad fournit la parallelisation (3-5 agents en meme temps). Chaque session Squad beneficie des protections gstack.

---

## Ce que chaque framework ne fait PAS

| Framework | Limites |
|-----------|---------|
| **BMAD** | Ne gere pas le context rot (sessions longues). Completer avec GSD |
| **GSD** | Pas d'interface visuelle. Completer avec Vibe Kanban |
| **Vibe Kanban** | Pas de methodologie — c'est un outil, pas un process. Completer avec BMAD ou GSD |
| **Templates** | Pas de workflow — juste des configs. Completer avec n'importe quel framework |
| **gstack** | Pas d'orchestration multi-agents. Completer avec Claude Squad |
| **Spec Kit** | Pas d'agents — vous devez executer manuellement avec Claude Code |
| **RALPH** | Pas de planification — il execute, il ne planifie pas. Completer avec Spec Kit ou BMAD |

---

*Derniere verification : 2026-03-22 · [Signaler un probleme](../../.github/ISSUE_TEMPLATE/tool-update.md)*
