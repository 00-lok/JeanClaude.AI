# TDD / BDD avec Claude Code

> Workflows de developpement pilote par les tests (Test-Driven Development) et par le comportement (Behavior-Driven Development) avec Claude Code.

---

## Outils TDD pour Claude Code

| Outil | Description | Lien |
|-------|-------------|------|
| **ATDD** | Acceptance Test Driven Development inspire de Uncle Bob. Impose la discipline Red-Green-Refactor | [swingerman/atdd](https://github.com/swingerman/atdd) |
| **TDD Skill** | Skill personnalise qui force Claude Code a suivre la discipline TDD avec des boucles Red-Green-Refactor explicites | [aihero.dev](https://www.aihero.dev/skill-test-driven-development-claude-code) |
| **TDD Guide** | Guide complet du workflow TDD avec Claude Code (partie du ultimate guide) | [claude-code-ultimate-guide](https://github.com/FlorianBruniaux/claude-code-ultimate-guide) |

---

## Le cycle TDD avec Claude Code

### 1. Red — Ecrire un test qui echoue

```
Ecris un test pour [fonctionnalite]. Le test doit echouer car la fonctionnalite
n'est pas encore implementee. N'ecris PAS l'implementation.
```

### 2. Green — Ecrire le minimum de code pour passer le test

```
Implemente le minimum de code necessaire pour faire passer le test.
Pas de code superflu.
```

### 3. Refactor — Ameliorer le code en gardant les tests verts

```
Refactorise le code en gardant tous les tests verts.
Ameliore la lisibilite et la structure sans changer le comportement.
```

---

## Bonne pratique

Le principal anti-pattern avec Claude Code et le TDD est que Claude a tendance a **ecrire l'implementation en meme temps que le test**. Pour l'eviter :

- Utilisez le skill ATDD ou TDD Skill qui impose la discipline
- Soyez explicite dans vos prompts : "N'ecris PAS l'implementation"
- Demandez a Claude de lancer les tests apres chaque etape pour verifier l'etat rouge/vert

---

*Derniere verification : 2026-03-22 · [Signaler un probleme](../../.github/ISSUE_TEMPLATE/tool-update.md)*
