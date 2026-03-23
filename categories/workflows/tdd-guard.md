# TDD Guard

> Hooks qui bloquent le code non-TDD et injectent les skills TDD automatiquement. Passe l'activation des skills de ~20% a ~84%.

| Info | Detail |
|------|--------|
| **GitHub** | [nizos/tdd-guard](https://github.com/nizos/tdd-guard) |
| **Installation** | Voir le depot GitHub |
| **Categorie** | Workflow / TDD |
| **Statut** | Actif |
| **Derniere verification** | 2026-03-22 |

---

## Ce que ca fait

TDD Guard resout le probleme principal du TDD avec Claude : meme avec un skill TDD installe, Claude ne l'active que ~20% du temps. TDD Guard utilise des hooks PreToolUse pour **injecter la logique TDD** dans chaque operation, montant l'activation a ~84%.

Les hooks valident que les tests existent avant d'autoriser l'ecriture de code d'implementation. Toggle rapide pour activer/desactiver le mode TDD selon le contexte.

---

## Fonctionnalites cles

- **Injection via hooks** — Activation TDD de 20% → 84%
- **Blocage non-TDD** — L'implementation est bloquee si les tests n'existent pas
- **Toggle rapide** — Activer/desactiver le mode TDD selon le besoin
- **Gestion de session** — Persistance du mode TDD entre les commandes

---

## Liens

- [Depot GitHub](https://github.com/nizos/tdd-guard)
- [Article explicatif](https://nizar.se/tdd-guard-for-claude-code/)

---

*Derniere verification : 2026-03-22 · [Signaler un probleme](../../.github/ISSUE_TEMPLATE/tool-update.md)*
