# Ruflo

> Plateforme d'orchestration multi-agents pour Claude avec coordination de swarm, integration RAG et routage auto-apprenant.

| Info | Detail |
|------|--------|
| **GitHub** | [ruvnet/ruflo](https://github.com/ruvnet/ruflo) |
| **Site web** | Non disponible |
| **Installation** | `git clone` + configuration |
| **Categorie** | Orchestration |
| **Licence** | MIT |
| **Statut** | Actif |
| **Derniere verification** | 2026-03-22 |

---

## Ce que ca fait

Ruflo (anciennement Claude Flow) se positionne sur un creneau different des autres orchestrateurs : la **coordination de swarms d'agents a grande echelle**. La ou Claude Squad gere 3-5 agents en parallele, Ruflo est concu pour orchestrer des dizaines d'agents avec un routage intelligent des taches.

Le principe : un agent coordinateur analyse une tache complexe, la decompose, et distribue les sous-taches a un essaim d'agents specialises. Un systeme de routage auto-apprenant ameliore la distribution au fil du temps en apprenant quels types de taches chaque agent gere le mieux.

Ruflo integre aussi une couche RAG (Retrieval-Augmented Generation) pour que les agents puissent interroger une base de connaissances partagee — documentation interne, specs, code existant — sans tout charger dans le contexte.

---

## Fonctionnalites cles

- **Coordination de swarm** — Un coordinateur distribue les taches a un essaim d'agents specialises
- **Routage auto-apprenant** — Le systeme optimise la distribution des taches au fil du temps
- **Integration RAG** — Base de connaissances interrogeable par tous les agents
- **Support MCP** — Communication entre agents via le protocole MCP
- **Architecture distribuee** — Les agents peuvent tourner sur differentes machines

---

## Installation

```bash
# Cloner le depot
git clone https://github.com/ruvnet/ruflo.git
cd ruflo

# Installer les dependances
npm install

# Configurer (voir le README pour les details)
cp .env.example .env
# Editer .env avec votre cle API Anthropic
```

### Prerequis

- Node.js v18+
- Cle API Anthropic
- Git

---

## Utilisation avec Claude Code

```bash
# Lancer Ruflo comme orchestrateur
npx ruflo start

# Soumettre une tache complexe
npx ruflo task "Migrer l'application de REST a GraphQL"

# Ruflo va :
# 1. Analyser la tache et la decomposer
# 2. Creer des sous-taches (schemas, resolvers, migration BDD, tests)
# 3. Distribuer chaque sous-tache a un agent specialise
# 4. Coordonner les resultats
# 5. Verifier la coherence globale

# Suivre la progression
npx ruflo status
```

### Quand utiliser Ruflo vs Claude Squad

| Critere | Ruflo | Claude Squad |
|---------|-------|-------------|
| Nombre d'agents | Dizaines | 3-5 |
| Configuration | Complexe | Simple |
| Courbe d'apprentissage | Elevee | Faible |
| Cas d'usage | Projets enterprise, taches massives | Taches paralleles quotidiennes |
| Routage | Intelligent, auto-apprenant | Manuel |

---

## Configuration

Configuration via fichier `.env` et `ruflo.config.json` :

```json
{
  "coordinator": {
    "model": "claude-sonnet-4-6",
    "maxAgents": 10
  },
  "agents": {
    "defaultModel": "claude-haiku-4-5",
    "timeout": 300000
  },
  "rag": {
    "enabled": true,
    "indexPath": "./knowledge-base"
  }
}
```

---

## Liens

- [Depot GitHub](https://github.com/ruvnet/ruflo)
- [Wiki CLAUDE.md Templates](https://github.com/ruvnet/ruflo/wiki/CLAUDE-MD-Templates)

---

*Derniere verification : 2026-03-22 · [Signaler un probleme](../../.github/ISSUE_TEMPLATE/tool-update.md)*
