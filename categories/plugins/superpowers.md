# Superpowers

> Le plugin Claude Code #1 mondial — un framework agentique qui enforce le TDD, structure le developpement en 7 phases, et utilise des subagents frais par tache pour eliminer le context rot.

| Info | Detail |
|------|--------|
| **GitHub** | [obra/superpowers](https://github.com/obra/superpowers) |
| **Site web** | Non disponible |
| **Installation** | `/plugin install superpowers` |
| **Categorie** | Plugin / Framework |
| **Licence** | MIT |
| **Statut** | Actif |
| **Stars** | ~104k |
| **Derniere verification** | 2026-03-22 |

---

## Ce que ca fait

Superpowers transforme Claude Code d'un generateur de code en un **developpeur senior discipline**. Le principe fondamental : Claude ne peut pas prendre de raccourcis. Le plugin impose un workflow en 7 phases que l'agent ne peut pas contourner, avec un point cle radical — **il supprime le code ecrit avant les tests**.

Concretement : si Claude essaie d'ecrire l'implementation avant d'avoir ecrit les tests, Superpowers efface cette implementation. C'est l'enforcement TDD le plus strict qui existe. Le resultat : chaque ligne de code est couverte par un test, chaque test a ete ecrit AVANT l'implementation, et le cycle Red-Green-Refactor est respecte mecaniquement.

Le deuxieme pilier est l'utilisation de **subagents frais par tache**. Au lieu de tout faire dans un seul contexte (qui se degrade au fil du temps — le "context rot"), Superpowers spawne un nouveau subagent avec un contexte propre de 200K tokens pour chaque tache. Cela garantit que la qualite de la 50eme tache est aussi bonne que la 1ere.

Un developpeur a rapporte avoir livre 100 000 lignes de code de haute qualite en deux semaines avec Superpowers et des subagents paralleles.

---

## Fonctionnalites cles

- **TDD enforcement radical** — Supprime le code ecrit avant les tests. Pas de contournement possible
- **Workflow 7 phases** — Brainstorm → Spec → Plan → TDD → Subagent Dev → Review → Finalize
- **Subagents frais par tache** — Chaque tache s'execute dans un contexte propre, eliminant le context rot
- **Revue de code inter-taches** — Claude revoit son propre code entre chaque phase, bloquant les issues critiques
- **Debugging systematique en 4 phases** — Methodologie structuree pour le debugging, pas d'approche "essai-erreur"
- **Brainstorming socratique** — Phase de brainstorm avant la spec pour explorer les options

---

## Installation

```bash
/plugin install superpowers
```

### Prerequis

- Claude Code CLI installe et authentifie

---

## Utilisation avec Claude Code

```bash
# Superpowers s'active automatiquement apres installation
# Le workflow impose les phases dans l'ordre

# Phase 1 : Brainstorm — Explorer les options
# Claude pose des questions, explore les approches, identifie les risques

# Phase 2 : Spec — Definir les exigences
# Claude redige une specification avec criteres d'acceptation

# Phase 3 : Plan — Planifier l'implementation
# Claude cree un plan detaille avec etapes et dependances

# Phase 4 : TDD — Ecrire les tests AVANT le code
# Claude ecrit les tests. S'il ecrit du code avant → SUPPRIME
# Red: tests ecrits, echouent
# Green: implementation minimale pour passer les tests
# Refactor: ameliorer sans casser les tests

# Phase 5 : Subagent Dev — Implementation dans un contexte frais
# Un nouveau subagent implemente chaque tache avec 200K tokens propres

# Phase 6 : Review — Revue de code automatique
# Claude revoit son propre code, bloque si issues critiques

# Phase 7 : Finalize — Verification finale et documentation
```

### Quand utiliser Superpowers

| Situation | Adapte ? |
|-----------|----------|
| Projet qui doit etre fiable (production, API publique) | Oui — c'est le cas d'usage ideal |
| Prototype rapide / hackathon | Non — le workflow est trop strict |
| Projet avec tests existants | Oui — Superpowers s'integre aux tests existants |
| Correction de bug rapide | Non — trop de ceremonies pour un fix simple |

---

## Configuration

Superpowers se configure via ses skills internes. Apres installation, les workflows sont automatiquement actifs. Vous pouvez personnaliser :

- Les phases a inclure (desactiver le brainstorm pour les petites taches)
- Les criteres de revue (stricte vs permissive)
- Le modele pour les subagents (Sonnet pour la vitesse, Opus pour la qualite)

---

## Liens

- [Depot GitHub](https://github.com/obra/superpowers)
- [Tutoriel Superpowers TDD](https://byteiota.com/superpowers-tutorial-claude-code-tdd-framework-2026/)

---

*Derniere verification : 2026-03-22 · [Signaler un probleme](../../.github/ISSUE_TEMPLATE/tool-update.md)*
