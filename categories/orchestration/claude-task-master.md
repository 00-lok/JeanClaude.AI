# Claude Task Master (Taskmaster AI)

> Systeme de gestion de taches pilote par IA qui decompose un PRD en taches structurees avec dependances, scoring de complexite et 36 outils MCP.

| Info | Detail |
|------|--------|
| **GitHub** | [eyaltoledano/claude-task-master](https://github.com/eyaltoledano/claude-task-master) |
| **Site web** | Non disponible |
| **Installation** | `npm install` (voir ci-dessous) |
| **Categorie** | Orchestration / Gestion de taches |
| **Licence** | MIT |
| **Statut** | Actif |
| **Stars** | ~25.3k |
| **Derniere verification** | 2026-03-22 |

---

## Ce que ca fait

Claude Task Master prend un PRD (Product Requirements Document) — un document decrivant ce que votre logiciel doit faire — et le decompose automatiquement en **taches atomiques** avec :

- **Dependances** — La tache B ne peut commencer avant que la tache A soit finie
- **Scoring de complexite** — Chaque tache reçoit un score de difficulte (1-10)
- **Sous-taches** — Les taches complexes sont re-decomposees en etapes plus petites
- **Fichier `tasks.json`** — Toutes les taches dans un format structure executable

Claude Task Master ne fait PAS l'implementation — il fait la **planification**. Ensuite, vous utilisez Claude Code (ou un autre agent) pour executer les taches une par une.

Initialement cree pour Cursor, il fonctionne maintenant avec Claude Code via ses 36 outils MCP.

---

## Fonctionnalites cles

- **Parsing automatique de PRD** — Transforme un document en taches atomiques en quelques secondes
- **36 outils MCP** — Integration native avec Claude Code via le protocole MCP
- **Graphe de dependances** — Visualisation de l'ordre d'execution des taches
- **Scoring de complexite** — Evaluation automatique de la difficulte (1-10)
- **3 agents specialises** — Orchestrateur (planification), Executeur (implementation), Verificateur (qualite)
- **Generation tasks.json** — Format JSON structure, versionnable avec Git

---

## Installation

```bash
# Cloner et installer
git clone https://github.com/eyaltoledano/claude-task-master.git
cd claude-task-master
npm install

# Configurer comme serveur MCP pour Claude Code
# Ajouter dans .claude/settings.json :
```

```json
{
  "mcpServers": {
    "taskmaster": {
      "command": "node",
      "args": ["path/to/claude-task-master/server.js"]
    }
  }
}
```

### Prerequis

- Node.js v18+
- Claude Code CLI installe

---

## Utilisation avec Claude Code

```bash
# 1. Creer un PRD (manuellement ou avec Claude)
# prd.md contient les exigences de votre projet

# 2. Parser le PRD en taches
/task-master parse prd.md
# → Genere tasks.json avec toutes les taches, dependances, scores

# 3. Voir les taches generees
/task-master list
# ID  Titre                          Complexite  Dependances  Statut
# 1   Setup projet et dependances    2           -            En attente
# 2   Schema base de donnees         4           1            En attente
# 3   API authentification           6           1,2          En attente
# 4   Frontend login                 5           3            En attente

# 4. Prendre la prochaine tache disponible
/task-master next
# → Selectionne la tache sans dependances bloquantes
# → Claude Code commence l'implementation

# 5. Marquer comme terminee et passer a la suivante
/task-master complete 1
/task-master next
```

### Exemple de tasks.json genere

```json
{
  "tasks": [
    {
      "id": 1,
      "title": "Setup projet et dependances",
      "description": "Initialiser le projet Next.js avec TypeScript...",
      "complexity": 2,
      "dependencies": [],
      "subtasks": [
        "Initialiser le projet avec create-next-app",
        "Configurer TypeScript strict",
        "Installer les dependances (prisma, next-auth, ...)"
      ],
      "status": "pending"
    }
  ]
}
```

---

## Configuration

Le fichier `tasks.json` est la configuration principale. Il est genere automatiquement par le parsing du PRD et peut etre edite manuellement si necessaire.

```bash
# Emplacement par defaut
./tasks.json

# Regenerer a partir du PRD
/task-master parse prd.md --output tasks.json

# Ajouter une tache manuellement
/task-master add "Nouvelle tache" --complexity 3 --depends-on 2
```

---

## Liens

- [Depot GitHub](https://github.com/eyaltoledano/claude-task-master)

---

*Derniere verification : 2026-03-22 · [Signaler un probleme](../../.github/ISSUE_TEMPLATE/tool-update.md)*
