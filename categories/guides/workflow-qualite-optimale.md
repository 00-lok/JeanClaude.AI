# Workflow de qualite optimale

> Le workflow qui produit la meilleure qualite de code avec Claude Code, base sur les retours d'experience et les donnees de la communaute.

---

## Le pipeline en 7 etapes

```
1. SPEC        → Definir le probleme avant de coder
2. PLAN        → Planifier l'architecture (Plan Mode)
3. TDD         → Tests AVANT l'implementation
4. CONTEXTE    → Subagents frais par tache
5. IMPLEMENT   → Coder contre la spec et les tests
6. REVIEW      → Revue multi-agents parallele
7. SHIP        → Quality gates CI/CD bloquantes
```

---

## Etape 1 : Spec — Definir le probleme

**Pourquoi** : Claude resout brillamment le mauvais probleme si vous ne definissez pas le bon.

| Outil | Quand l'utiliser |
|-------|-----------------|
| [BMAD Method](../frameworks/bmad-method.md) | Projet enterprise, equipe, phases structurees |
| [GSD](../frameworks/gsd.md) | Projet solo/petit, gestion du context rot |
| [Spec Kit](../frameworks/spec-kit.md) | Projet GitHub-native, specs comme reference unique |

**Resultat prouve** : Un projet Twitter clone en spec-driven a obtenu zero regressions, zero breaking changes, 100% build success rate.

---

## Etape 2 : Plan — Planifier l'architecture

**Pourquoi** : Plan Mode reduit les erreurs d'architecture de 45% sur les taches multi-fichiers.

```bash
# Entrer en Plan Mode
Shift+Tab

# Claude lit le code, analyse, et propose un plan
# SANS modifier aucun fichier

# Regle : si le changement touche 3+ fichiers, planifier d'abord
```

**Regle d'or** : Si vous ne pouvez pas decrire le changement en une seule phrase, planifiez d'abord.

---

## Etape 3 : TDD — Tests AVANT l'implementation

**Pourquoi** : Claude tend a ecrire l'implementation en meme temps que les tests, produisant des tests qui verifient l'implementation plutot que le comportement.

| Outil | Approche |
|-------|----------|
| [Superpowers](../plugins/superpowers.md) | Radical — supprime le code ecrit avant les tests |
| [TDD Guard](../workflows/tdd-guard.md) | Hooks — bloque l'implementation si pas de tests |
| [ATDD](../workflows/tdd-bdd.md) | Deux flux de tests (acceptance + unit) |

**Metrique prouvee** : Un dev avec TDD quality gates pendant 3 mois rapporte que "le plus gros changement n'etait pas le nombre de bugs, mais le temps de cycle."

---

## Etape 4 : Contexte — Subagents frais

**Pourquoi** : Le "context rot" — la degradation de qualite quand le contexte se remplit — est le probleme #1 des sessions longues.

**Solutions** :

- `/compact` a ~50% de saturation du contexte
- `/clear` entre les taches non liees
- Subagents frais par tache (pattern GSD/Superpowers)
- [claude-mem](../plugins/claude-mem.md) pour la memoire entre sessions
- [claude-context](../resources/claude-context.md) pour la recherche semantique (-40% tokens)

---

## Etape 5 : Implementation

**Avec les etapes precedentes, l'implementation est guidee** :
- La spec dit QUOI construire
- Le plan dit COMMENT le construire
- Les tests definissent QUAND c'est termine
- Le contexte frais garantit la QUALITE

---

## Etape 6 : Revue multi-agents

**Pourquoi** : Un seul agent qui revoit son propre code a des angles morts. Plusieurs agents specialises couvrent plus de surface.

| Outil | Nombre d'agents | Specialite |
|-------|----------------|------------|
| [Metaswarm](../orchestration/metaswarm.md) | 18 agents | Revue adversariale avec gate PASS/FAIL |
| [Compound Engineering](../plugins/compound-engineering.md) | 12 agents | 12 perspectives de revue paralleles |
| Pattern 9-agents | 9 agents | Securite, perf, tests, deps, simplicite, style, etc. |
| Claude Code Review (officiel) | Multi | Equipe + Enterprise, ~$15-25 par revue |

### Le pattern 9-agents

```
1. Test Runner         — Execute les tests
2. Linter              — Analyse statique + lint
3. Code Reviewer       — 5 ameliorations concretes par impact
4. Security Reviewer   — Injections, auth, credentials
5. Quality Reviewer    — Complexite, code mort, duplication
6. Test Quality        — Couverture ROI, tests comportementaux vs implementation
7. Performance         — N+1, ops bloquantes, fuites memoire
8. Dependencies        — Breaking changes, securite deps
9. Simplification      — Le code pourrait-il etre plus simple ?
```

---

## Etape 7 : Quality gates CI/CD

**Pourquoi** : Les hooks locaux protegent en dev. Les CI/CD protegent en deploiement.

### Quality gates bloquantes recommandees

```yaml
# GitHub Actions
- Type safety : tsc --noEmit (zero erreurs)
- Tests : vitest run (100% pass)
- Couverture : >80% pour le nouveau code
- Lint : eslint --max-warnings=0
- Securite : claude-code-security-review
- Deps : socket-mcp scan
```

### Outils CI/CD

| Outil | Role |
|-------|------|
| [claude-code-action](../workflows/ci-cd.md) | Revue Claude sur chaque PR |
| [claude-code-security-review](https://github.com/anthropics/claude-code-security-review) | Scan securite sur chaque PR |
| [Semgrep MCP](../mcp-servers/monitoring-security/semgrep-mcp.md) | Analyse statique deterministe |

---

## Configuration CLAUDE.md optimale

**Regles decouvertes par la communaute** :

- **< 80 lignes** — Au-dela, Claude ignore des regles
- **Langage positif** — "Utilise X" > "N'utilise PAS Y" (divise les violations par 2)
- **Primacy/recency** — Les regles en debut et fin sont mieux suivies
- **Hooks > CLAUDE.md** — Pour les regles critiques, utilisez des hooks (deterministes)
- **Compounding** — Chaque erreur de Claude → nouvelle regle dans CLAUDE.md

---

## Stack recommandee par taille de projet

### Projet solo / petit
```
Spec Kit + gstack + TDD Guard + claude-mem
```

### Projet moyen / equipe
```
GSD + Superpowers + Claude Squad + claude-context + Plankton
```

### Projet enterprise
```
BMAD + Metaswarm + Trail of Bits Skills + Semgrep MCP + claude-code-action
```

---

*Derniere verification : 2026-03-22 · [Signaler un probleme](../../.github/ISSUE_TEMPLATE/tool-update.md)*
