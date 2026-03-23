# Workflows agentiques

> Pipelines de developpement multi-agents ou plusieurs instances Claude se coordonnent pour accomplir des taches complexes.

---

## Fonctionnalite native : Agent Teams (experimental)

Claude Code possede une fonctionnalite experimentale permettant a plusieurs instances de se coordonner. Une session joue le role de team lead, coordonnant le travail, assignant les taches et synthetisant les resultats.

**Activation** :
```bash
export CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS=1
```

Documentation : [code.claude.com/docs/en/agent-teams](https://code.claude.com/docs/en/agent-teams)

---

## Frameworks de workflows agentiques

| Framework | Description | Lien |
|-----------|-------------|------|
| **BMAD Method** | Framework agile complet avec 12+ agents specialises | [Voir fiche](../frameworks/bmad-method.md) |
| **GSD** | Decoupe en taches atomiques executees dans des contextes frais | [Voir fiche](../frameworks/gsd.md) |
| **claude-code-workflows** | Workflows prets a la production avec agents specialises | [shinpr/claude-code-workflows](https://github.com/shinpr/claude-code-workflows) |
| **Claude-Code-Workflow** | Framework JSON-driven avec orchestration CLI multi-modeles | [catlog22/Claude-Code-Workflow](https://github.com/catlog22/Claude-Code-Workflow) |

---

## Pattern typique d'un workflow agentique

```
1. PLANIFICATION
   └─ Agent planificateur decompose le travail en taches

2. RECHERCHE
   └─ Agent chercheur analyse le codebase et la documentation

3. IMPLEMENTATION
   └─ Agent developpeur implemente chaque tache dans un worktree isole

4. VERIFICATION
   └─ Agent verificateur lance les tests et valide la qualite

5. INTEGRATION
   └─ Agent integrateur merge les changements et resout les conflits
```

---

## Outils d'orchestration pour workflows agentiques

Voir la categorie [Orchestration](../orchestration/) pour les outils de coordination multi-agents :
- [Claude Squad](../orchestration/claude-squad.md) — Gestion terminal
- [Ruflo](../orchestration/ruflo.md) — Enterprise
- [CCPM](../orchestration/ccpm.md) — GitHub Issues
- [Claude Task Master](../orchestration/claude-task-master.md) — Planification PRD

---

*Derniere verification : 2026-03-22 · [Signaler un probleme](../../.github/ISSUE_TEMPLATE/tool-update.md)*
