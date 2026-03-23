# Astuces et conseils

> 45+ astuces pratiques pour tirer le meilleur de Claude Code, du debutant au power user.

---

## Source principale

Le depot [ykdojo/claude-code-tips](https://github.com/ykdojo/claude-code-tips) contient 45 astuces detaillees. Voici les plus impactantes :

---

## Gestion du contexte

- **`/compact`** — Compacter le contexte quand la session devient longue. Essentiel pour les sessions de plus de 30 minutes
- **`/context`** — Voir ou vont vos tokens. Identifier ce qui consomme le plus de contexte
- **Limiter le CLAUDE.md** — Garder le fichier court (60-80 lignes max) pour eviter la dilution
- **Sessions courtes** — Preferer des sessions courtes et focalisees a de longues sessions epuisantes

## Commandes essentielles

- **`/init`** — Generer un CLAUDE.md de base a partir de l'analyse du projet
- **`/hooks`** — Menu interactif pour configurer les hooks (plus facile que l'edition JSON)
- **`/cost`** — Voir le cout de la session en cours
- **`/doctor`** — Diagnostiquer les problemes de configuration

## Techniques avancees

- **Mode plan** — Utiliser le mode plan (`Shift+Tab`) pour planifier avant d'executer
- **Sous-agents** — Claude peut spawner des sous-agents pour des taches paralleles
- **Worktrees** — Utiliser des Git worktrees pour isoler le travail des agents
- **Conteneurs** — Executer Claude Code dans un conteneur Docker pour un sandbox complet

## Optimisation des prompts

- **Etre specifique** — "Ajoute un bouton de suppression dans le composant UserList qui appelle l'API DELETE /users/:id" > "Ajoute un bouton de suppression"
- **Donner du contexte** — "Le bug se manifeste quand l'utilisateur fait X, le comportement attendu est Y"
- **References de fichiers** — Mentionner les fichiers specifiques : "Dans `src/api/users.ts`..."
- **Exemples** — Montrer un exemple de ce que vous attendez quand c'est ambigu

## Productivite

- **Copier-coller d'erreurs** — Collez les erreurs completes directement dans Claude Code
- **Screenshots** — Claude Code peut lire les captures d'ecran (glisser-deposer)
- **Multi-onglets** — Ouvrir plusieurs sessions Claude Code pour des taches independantes

---

## Depots de reference

| Depot | Description |
|-------|-------------|
| [ykdojo/claude-code-tips](https://github.com/ykdojo/claude-code-tips) | 45 astuces detaillees avec le plugin dx |
| [FlorianBruniaux/claude-code-ultimate-guide](https://github.com/FlorianBruniaux/claude-code-ultimate-guide) | Guide debutant a expert |
| [Njengah/claude-code-cheat-sheet](https://github.com/Njengah/claude-code-cheat-sheet) | Cheat sheet complet |
| [Documentation officielle](https://code.claude.com/docs/en/best-practices) | Bonnes pratiques Anthropic |

---

*Derniere verification : 2026-03-22 · [Signaler un probleme](../../.github/ISSUE_TEMPLATE/tool-update.md)*
