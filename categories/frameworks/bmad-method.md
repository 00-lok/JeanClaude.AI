# BMAD Method

> Breakthrough Method for Agile AI-Driven Development — un framework agile complet qui transforme Claude Code en une equipe de developpement complete avec 12+ agents IA specialises.

| Info | Detail |
|------|--------|
| **GitHub** | [bmad-code-org/BMAD-METHOD](https://github.com/bmad-code-org/BMAD-METHOD) |
| **Site web** | [docs.bmad-method.org](https://docs.bmad-method.org/) |
| **Installation** | `npx bmad-method install` |
| **Categorie** | Framework |
| **Licence** | MIT |
| **Statut** | Actif (v6.2.0, mars 2026) |
| **Derniere verification** | 2026-03-22 |

---

## Ce que ca fait

BMAD transforme les assistants de programmation IA en une equipe de developpement agile structuree. Au lieu de donner a Claude des prompts vagues en esperant le meilleur, BMAD fournit des **personas d'agents en langage naturel** qui guident Claude a travers des processus de developpement structures — de l'ideation jusqu'a l'architecture, l'implementation et le deploiement.

Le framework utilise le **Spec-Driven Development (SDD)** : chaque projet commence par un PRD, un document d'architecture et une spec technique avant qu'une seule ligne de code ne soit ecrite. Cela elimine le probleme du "vibe coding" ou l'IA genere du code sans exigences claires.

BMAD realise des **economies de tokens de 70-85%** par rapport aux approches traditionnelles grace aux patterns helper et a la gestion de contexte basee sur YAML. Il s'adapte des corrections de bugs (Niveau 0) aux systemes enterprise (Niveau 4) avec detection automatique de la complexite.

---

## Fonctionnalites cles

- **12+ agents specialises** — BMad Master (orchestrateur), Business Analyst, Product Manager, System Architect, Scrum Master, Developer, UX Designer, QA Engineer, Creative Intelligence, Product Owner, et plus
- **34+ workflows de base** — Processus structures a travers 4 phases de developpement : Analyse → Planification → Conception → Implementation
- **15 commandes de workflow** — Commandes slash qui declenchent les workflows d'agents appropries
- **Planification adaptive** — Ajuste automatiquement la profondeur selon la complexite du projet (Niveaux 0-4)
- **Mode Party** — Plusieurs personas d'agents collaborent dans une seule session
- **70-85% d'economies de tokens** — Patterns helper et gestion de contexte YAML reduisent les couts

---

## Installation

```bash
npx bmad-method install
```

### Prerequis

- Node.js v20+
- CLI Claude Code installe et authentifie

### Integrations alternatives

| Depot | Description |
|-------|-------------|
| [aj-geddes/claude-code-bmad-skills](https://github.com/aj-geddes/claude-code-bmad-skills) | Integration native Claude Code optimisee en tokens avec 9 skills, 15 commandes |
| [24601/BMAD-AT-CLAUDE](https://github.com/24601/BMAD-AT-CLAUDE) | Portage de BMAD specifiquement pour Claude Code |

---

## Utilisation avec Claude Code

Apres installation, les skills se chargent automatiquement au demarrage de Claude Code. Utilisez les commandes slash pour declencher les workflows :

```bash
# Demarrer un nouveau projet avec le flux BMAD complet
/bmad start

# Invoquer un agent specifique
/bmad architect    # System Architect pour les decisions techniques
/bmad pm           # Product Manager pour les exigences
/bmad dev          # Developer pour l'implementation

# Executer un workflow
/bmad sprint-plan  # Planification de sprint avec l'agent Scrum Master
/bmad code-review  # Workflow de revue de code
```

### Phases de developpement

1. **Analyse** — Business Analyst et Creative Intelligence etudient le probleme
2. **Planification** — Product Manager definit les exigences (PRD, Jobs-to-be-Done)
3. **Conception** — System Architect conçoit la solution technique
4. **Implementation** — Developer implemente avec verification du QA Engineer

---

## Configuration

BMAD s'installe dans le repertoire `.claude/` de votre projet :
- Skills dans `.claude/skills/`
- Commandes dans `.claude/commands/`
- Personas d'agents en fichiers de configuration YAML

Personnalisez le comportement des agents en editant les fichiers YAML de personas.

---

## Liens

- [Depot GitHub](https://github.com/bmad-code-org/BMAD-METHOD)
- [Documentation](https://docs.bmad-method.org/)
- [Reference des Skills](https://aj-geddes.github.io/claude-code-bmad-skills/)
- [Comprendre les agents BMAD (DEV Community)](https://dev.to/jacktt/understanding-the-agents-in-the-bmad-235o)

---

*Derniere verification : 2026-03-22 · [Signaler un probleme](../../.github/ISSUE_TEMPLATE/tool-update.md)*
