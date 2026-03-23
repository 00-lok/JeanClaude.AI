# Metaswarm

> Framework d'orchestration multi-agents auto-ameliorant avec revue adversariale et quality gates bloquantes — l'agent ne peut pas commiter tant que la revue n'est pas passee.

| Info | Detail |
|------|--------|
| **GitHub** | [dsifry/metaswarm](https://github.com/dsifry/metaswarm) |
| **Site web** | Non disponible |
| **Installation** | `git clone` + `INSTALL.md` |
| **Categorie** | Orchestration |
| **Licence** | MIT |
| **Statut** | Actif |
| **Derniere verification** | 2026-03-22 |

---

## Ce que ca fait

Metaswarm implemente le pattern le plus strict de controle qualite multi-agents : une **boucle d'execution orchestree en 4 phases** ou chaque transition est bloquee par un quality gate.

La cle est la **phase de revue adversariale** : un agent de revue completement frais (qui n'a pas vu l'implementation) examine chaque critere de la Definition of Done avec des preuves `fichier:ligne` en format binaire PASS/FAIL. Il n'existe **aucun chemin de FAIL vers COMMIT** — si la revue echoue, le code retourne en implementation.

L'orchestrateur ne fait jamais confiance aux auto-rapports des subagents. Il execute lui-meme `tsc`, `eslint`, `vitest` et la verification de couverture de maniere independante. Les seuils de couverture sont charges depuis `.coverage-thresholds.json` et constituent un gate bloquant.

---

## Fonctionnalites cles

- **4 phases bloquantes** — IMPLEMENT → VALIDATE → ADVERSARIAL REVIEW → COMMIT. Pas de raccourci possible
- **Revue adversariale** — Agent frais qui verifie chaque critere DoD avec preuves fichier:ligne, format PASS/FAIL
- **Verification independante** — L'orchestrateur lance tsc/eslint/vitest lui-meme, ne fait pas confiance aux rapports agents
- **Seuils de couverture bloquants** — Charges depuis `.coverage-thresholds.json`, la build echoue si non atteints
- **18 agents, 13 skills, 15 commandes** — Specifies par domaine
- **Auto-amelioration** — Le systeme apprend de ses echecs pour ameliorer les cycles suivants

---

## Installation

```bash
git clone https://github.com/dsifry/metaswarm.git
cd metaswarm
# Suivre INSTALL.md pour la configuration
```

### Prerequis

- Claude Code CLI
- Node.js v18+ (pour tsc, eslint, vitest)
- Git

---

## Utilisation avec Claude Code

```bash
# Lancer une tache avec Metaswarm
/metaswarm "Implementer le systeme de notifications push"

# Metaswarm orchestre automatiquement :

# Phase 1 : IMPLEMENT
# → Subagent developpe la fonctionnalite

# Phase 2 : VALIDATE
# → L'orchestrateur lance independamment :
#   tsc --noEmit        (zero erreurs requises)
#   eslint .            (zero warnings)
#   vitest run          (tous les tests passent)
#   coverage check      (seuils .coverage-thresholds.json respectes)

# Phase 3 : ADVERSARIAL REVIEW
# → Agent frais (n'a PAS vu l'implementation) verifie :
#   ✓ Chaque critere DoD avec preuve fichier:ligne
#   ✓ Format binaire : PASS ou FAIL, pas de "presque"
#   ✓ Un seul FAIL → retour en Phase 1

# Phase 4 : COMMIT
# → Seulement si TOUT est PASS
# → Commit atomique avec message Conventional Commits
```

### La boucle de retour

```
IMPLEMENT → VALIDATE → REVIEW → FAIL?
     ↑                           │
     └───────── retour ──────────┘

IMPLEMENT → VALIDATE → REVIEW → PASS → COMMIT ✓
```

---

## Configuration

```json
// .coverage-thresholds.json
{
  "statements": 80,
  "branches": 75,
  "functions": 80,
  "lines": 80
}
```

Les seuils sont personnalisables par projet. Tout code en dessous des seuils bloque le commit.

---

## Liens

- [Depot GitHub](https://github.com/dsifry/metaswarm)

---

*Derniere verification : 2026-03-22 · [Signaler un probleme](../../.github/ISSUE_TEMPLATE/tool-update.md)*
