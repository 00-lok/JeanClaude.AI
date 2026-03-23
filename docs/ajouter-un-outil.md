# Comment ajouter un outil

Guide etape par etape pour ajouter un nouvel outil au catalogue.

---

## Etape 1 : Verifier l'outil

Avant d'ajouter un outil, confirmez :

- [ ] L'outil a un **depot GitHub public** ou un site officiel
- [ ] L'outil est **activement maintenu** (commits dans les 6 derniers mois) ou clairement marque comme archive
- [ ] L'outil est **pertinent pour Claude AI** (fonctionne avec Claude Code, l'API Claude ou MCP)
- [ ] L'outil **n'est pas deja dans le catalogue** (cherchez dans le repo d'abord)

---

## Etape 2 : Choisir la bonne categorie

| Categorie | Criteres |
|-----------|----------|
| `frameworks/` | Methodologies ou systemes complets (BMAD, GSD, etc.) |
| `mcp-servers/{sous-categorie}/` | Serveurs protocole MCP connectant Claude a des services externes |
| `skills/` | Jeux d'instructions bases sur SKILL.md ou collections de skills |
| `plugins/` | Packages installables via `/plugin install` |
| `hooks/` | Gestionnaires d'evenements du cycle de vie (PreToolUse, PostToolUse, etc.) |
| `orchestration/` | Outils de coordination multi-agents ou de gestion de taches |
| `workflows/` | Processus de developpement (TDD, CI/CD, pipelines agentiques) |
| `guides/` | Contenu educatif, bonnes pratiques, astuces |
| `resources/` | Repertoires, registres, SDKs, listes awesome |

---

## Etape 3 : Creer la fiche outil

1. Copiez `templates/tool-template.md`
2. Enregistrez-le sous `categories/{categorie}/{nom-outil}.md` (kebab-case)
3. Remplissez **chaque section** — aucune section vide autorisee

### Convention de nommage

```
nom-outil.md          ✓  (kebab-case, minuscules)
Nom_Outil.md          ✗  (pas de underscores)
NOM-OUTIL.md          ✗  (pas de majuscules)
nomoutil.md           ✗  (utilisez des tirets pour la lisibilite)
```

---

## Etape 4 : Mettre a jour l'index de la categorie

Ouvrez `categories/{categorie}/README.md` et ajoutez votre outil au tableau :

```markdown
| [Nom de l'outil](nom-outil.md) | Description en une ligne | ~{etoiles} |
```

Gardez le tableau trie par pertinence ou etoiles (le plus eleve en premier).

---

## Etape 5 : Mettre a jour le README principal (si significatif)

Si l'outil a **10k+ etoiles** ou est un **outil majeur de l'ecosysteme**, ajoutez-le au tableau pertinent dans le `README.md` principal.

---

## Etape 6 : Soumettre votre PR

1. Creez une branche : `add/{nom-outil}`
2. Commitez vos modifications
3. Ouvrez une PR en utilisant le [template](../.github/PULL_REQUEST_TEMPLATE.md)
4. Un mainteneur effectuera la revue sous 48 heures

---

## Exemple

Ajout d'un outil fictif appele "Claude Turbo" :

1. Creer `categories/plugins/claude-turbo.md` a partir du template
2. Ajouter a `categories/plugins/README.md` :
   ```markdown
   | [Claude Turbo](claude-turbo.md) | Streaming de reponses accelere pour Claude Code | ~5.2k |
   ```
3. Soumettre une PR avec le titre : "Ajout de Claude Turbo aux plugins"
