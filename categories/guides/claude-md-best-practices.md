# Bonnes pratiques CLAUDE.md

> Comment ecrire des fichiers CLAUDE.md efficaces pour configurer le comportement de Claude Code dans vos projets.

---

## Qu'est-ce que CLAUDE.md ?

`CLAUDE.md` est le fichier de configuration principal de Claude Code. Il contient les instructions, regles et contexte que Claude lit au demarrage de chaque session. C'est l'equivalent d'un "briefing" donne a Claude avant qu'il commence a travailler.

---

## Emplacements et priorite

| Emplacement | Portee | Priorite |
|-------------|--------|----------|
| `~/.claude/CLAUDE.md` | Global (toutes les sessions) | La plus basse |
| `CLAUDE.md` (racine du projet) | Projet | Moyenne |
| `CLAUDE.local.md` | Local (non commite) | La plus haute |
| Sous-repertoires `CLAUDE.md` | Repertoire specifique | Contextuelle |

Les regles locales ecrasent les regles projet, qui ecrasent les regles globales.

---

## Regles d'or

### Faire

- **Garder le CLAUDE.md global sous 15 lignes** — Il est charge dans CHAQUE session
- **Garder le CLAUDE.md projet sous 60-80 lignes** — Au-dela, Claude commence a ignorer des parties
- **Se concentrer sur ce que Claude fait mal** — Pas besoin de lui dire ce qu'il fait deja bien
- **Inclure les commandes bash** — `npm test`, `npm run build`, `npm run lint`
- **Inclure les conventions de code** — Nommage, patterns, structure
- **Inclure les regles de workflow** — Quand commiter, quand tester, quand demander
- **Inclure la terminologie projet** — Jargon specifique au domaine
- **Utiliser `/init`** — Genere un CLAUDE.md de base analyse a partir de votre projet

### Ne pas faire

- **Pas d'instructions de personnalite** — "Sois un ingenieur senior" gaspille des tokens
- **Pas de regles de formatage** — "Utilise 2 espaces d'indentation" → utilisez un linter/formatter
- **Pas de contenu statique volumineux** — Pas de documentation API complete dans le fichier
- **Pas de regles redondantes** — Si c'est dans `.eslintrc`, pas besoin de le repeter

---

## Exemple de CLAUDE.md projet

```markdown
# CLAUDE.md

## Commandes
- `npm test` — Lancer les tests
- `npm run build` — Build de production
- `npm run lint` — Linting ESLint + Prettier

## Conventions
- TypeScript strict, pas de `any`
- Composants React : function components + hooks uniquement
- Tests : colocalisé avec le code (`Component.test.tsx` a cote de `Component.tsx`)
- Commits en francais, format conventionnel

## Architecture
- `src/api/` — Routes API Express
- `src/components/` — Composants React
- `src/hooks/` — Custom hooks
- `src/utils/` — Fonctions utilitaires pures

## Regles
- Toujours lancer les tests avant de commiter
- Ne pas modifier les fichiers de migration existants
- Les variables d'environnement vont dans `.env.example`, jamais dans le code
```

---

## Templates de reference

| Depot | Description |
|-------|-------------|
| [abhishekray07/claude-md-templates](https://github.com/abhishekray07/claude-md-templates) | Templates pour Next.js/React/TypeScript, Python/FastAPI et projets generiques |
| [ruvnet/ruflo Wiki](https://github.com/ruvnet/ruflo/wiki/CLAUDE-MD-Templates) | Wiki avec templates CLAUDE.md |
| [shanraisshan/claude-code-best-practice](https://github.com/shanraisshan/claude-code-best-practice) | Reference d'implementation avec skills, subagents, hooks et commandes |

---

## Documentation officielle

- [Best Practices (Anthropic)](https://code.claude.com/docs/en/best-practices)

---

*Derniere verification : 2026-03-22 · [Signaler un probleme](../../.github/ISSUE_TEMPLATE/tool-update.md)*
