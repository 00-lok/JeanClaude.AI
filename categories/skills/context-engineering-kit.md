# Context Engineering Kit

> Skills Claude Code pour ameliorer la qualite des resultats via spec-driven development, DDD et subagents. Teste en production avec un taux de 100% de code fonctionnel.

| Info | Detail |
|------|--------|
| **GitHub** | [NeoLabHQ/context-engineering-kit](https://github.com/NeoLabHQ/context-engineering-kit) |
| **Site web** | Non disponible |
| **Installation** | `/plugin install NeoLabHQ/context-engineering-kit` |
| **Categorie** | Skills / Qualite |
| **Licence** | MIT |
| **Statut** | Actif |
| **Derniere verification** | 2026-03-22 |

---

## Ce que ca fait

Le Context Engineering Kit part d'un constat : la qualite de la sortie de Claude depend directement de la qualite du **contexte** qu'il recoit. Donner un prompt vague produit du code vague. Donner un contexte ingenierie — specs structurees, modeles de domaine, patterns d'architecture — produit du code de production.

Ce kit fournit des skills qui structurent le contexte avant que Claude code : definition des specs, modeles DDD (Domain-Driven Design), et decomposition en taches pour subagents. Le resultat revendique est un taux de **100% de code fonctionnel** sur des projets de production reels — pas de code qui compile mais qui ne marche pas.

---

## Fonctionnalites cles

- **Spec-driven development** — Skills pour structurer les specs avant toute implementation
- **Domain-Driven Design** — Modelisation du domaine metier avant le code
- **Subagent-driven development** — Decomposition en taches optimisees pour les subagents
- **100% working code rate** — Teste sur des projets de production reels
- **Context engineering** — Pas du prompt engineering (changer les mots), mais du context engineering (changer les informations)

---

## Installation

```bash
/plugin install NeoLabHQ/context-engineering-kit
```

---

## Utilisation avec Claude Code

```bash
# Le kit ajoute des workflows qui structurent le contexte AVANT de coder

# 1. Definir le domaine metier
"Utilise le Context Engineering Kit pour modeliser le domaine e-commerce"
# → Claude cree les entites, aggregats, value objects, et bounded contexts

# 2. Structurer les specs
"Cree une spec pour le systeme de panier d'achat"
# → Claude produit une spec structuree avec invariants et cas limites

# 3. Decomposer en taches pour subagents
"Decompose l'implementation en taches pour subagents"
# → Chaque tache a un contexte optimise pour un subagent frais
```

---

## Liens

- [Depot GitHub](https://github.com/NeoLabHQ/context-engineering-kit)

---

*Derniere verification : 2026-03-22 · [Signaler un probleme](../../.github/ISSUE_TEMPLATE/tool-update.md)*
