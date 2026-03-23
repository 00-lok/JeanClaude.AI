# Smart Commit

> Workflow intelligent qui analyse vos changements Git, les decoupe en commits atomiques au format Conventional Commits, valide le code, et execute apres votre approbation.

| Info | Detail |
|------|--------|
| **Source** | Workflow BMAD custom |
| **Installation** | Copier les fichiers dans `.claude/commands/` et le repertoire workflow |
| **Categorie** | Workflow |
| **Licence** | MIT |
| **Statut** | Actif |
| **Derniere verification** | 2026-03-22 |

---

## Ce que ca fait

Smart Commit automatise tout le processus de commit Git. Au lieu de faire manuellement `git add`, reflechir au message, `git commit` — et souvent finir avec un commit geant "fix stuff" — Smart Commit fait ce travail pour vous en 4 etapes :

1. **Analyse le contexte** — Verifie le depot Git, detecte les scripts de validation (lint, build, test), etudie vos conventions de commit existantes (format, langue, scopes)
2. **Valide le code** — Execute automatiquement lint, type-check, build, tests. Si quoi que ce soit echoue, il s'arrete et vous dit quoi corriger
3. **Propose un plan de commits** — Analyse chaque diff, regroupe les fichiers par preoccupation logique, genere des messages Conventional Commits, et vous presente le plan pour validation
4. **Execute les commits** — Apres votre approbation, cree chaque commit atomique dans l'ordre logique

Le resultat : un historique Git propre, des commits atomiques, des messages standardises, et du code valide.

---

## Fonctionnalites cles

- **Commits atomiques** — Chaque commit represente UN changement logique, independamment revertable
- **Conventional Commits** — Format `type(scope): description` respecte automatiquement (`feat`, `fix`, `chore`, `refactor`, `docs`, `test`, `build`, `ci`, `style`, `perf`)
- **Validation automatique** — Lint, type-check, build, tests executes avant tout commit. Code casse = pas de commit
- **Detection des conventions** — Analyse vos 20 derniers commits pour reproduire votre style (langue, scopes, format)
- **Validation utilisateur obligatoire** — Jamais de commit sans votre approbation explicite du plan
- **Detection du package manager** — Detecte automatiquement pnpm, yarn ou npm depuis les lock files
- **Gestion d'erreur** — Arret immediat en cas de probleme, rapport clair de ce qui a marche et ce qui a echoue

---

## Installation

### Option 1 : Copier depuis ce repo

Les fichiers source du workflow sont disponibles dans [`smart-commit/`](smart-commit/) :

```bash
# Depuis la racine de votre projet

# 1. Creer la commande slash
mkdir -p .claude/commands
cp categories/workflows/smart-commit/bmad-smart-commit.md .claude/commands/

# 2. Creer le workflow (adaptez le chemin selon votre structure)
mkdir -p _bmad/custom/workflows/smart-commit/steps-c
cp categories/workflows/smart-commit/workflow.md _bmad/custom/workflows/smart-commit/
cp categories/workflows/smart-commit/steps-c/* _bmad/custom/workflows/smart-commit/steps-c/
```

### Option 2 : Installation manuelle

Creez les fichiers decrits dans la section [Fichiers source](#fichiers-source) ci-dessous.

### Prerequis

- Claude Code CLI installe
- Git initialise dans votre projet
- (Optionnel) `package.json` avec des scripts de validation (lint, build, test)

---

## Utilisation avec Claude Code

```bash
# 1. Faites vos modifications normalement
#    (editez des fichiers, ajoutez des fonctionnalites, corrigez des bugs)

# 2. Lancez smart-commit
/smart-commit

# 3. Le workflow s'execute automatiquement :
#    ✓ Analyse du contexte (silencieux)
#    ✓ Validation du code (silencieux si tout passe)
#    → Presentation du plan de commits

# 4. Vous voyez le plan :
#    Commit Plan — 3 commit(s) proposed
#    ─────────────────────────────────
#    Commit 1/3: chore(config): update ESLint and Prettier configuration
#    | File                | Status   |
#    |---------------------|----------|
#    | .eslintrc.json      | modified |
#    | .prettierrc         | modified |
#
#    Commit 2/3: feat(auth): add JWT refresh token rotation
#    | File                      | Status   |
#    |---------------------------|----------|
#    | src/auth/jwt.service.ts   | modified |
#    | src/auth/refresh.guard.ts | new file |
#
#    Commit 3/3: test(auth): add tests for refresh token rotation
#    | File                           | Status   |
#    |--------------------------------|----------|
#    | src/auth/__tests__/jwt.test.ts | new file |
#
#    [V] Validate and execute  [R] Re-group / modify  [X] Cancel

# 5. Choisissez :
#    V → Les commits sont crees dans l'ordre
#    R → Vous demandez des modifications au plan
#    X → Annulation, rien n'est commite
```

---

## Workflow en detail

### Etape 1 : Analyse du contexte (silencieux)

- Verifie que c'est un depot Git avec des changements non commites
- Detecte les scripts de validation dans `package.json` (lint, build, test, check)
- Analyse les 20 derniers commits pour identifier les conventions (format, langue, scopes)
- Comprend la structure du projet (tech stack, repertoires sources)

### Etape 2 : Validation technique (silencieux si OK)

- Execute les scripts dans l'ordre : lint → type-check → build → test
- Utilise le bon package manager (pnpm/yarn/npm detecte depuis les lock files)
- **Si tout passe** : continue silencieusement
- **Si quoi que ce soit echoue** : arret immediat avec rapport d'erreur clair

### Etape 3 : Plan de commits (attend votre validation)

- Analyse chaque diff en detail (pas juste les noms de fichiers)
- Regroupe par preoccupation logique :
  - Fichiers implementant la meme feature → un commit `feat`
  - Fichiers corrigeant le meme bug → un commit `fix`
  - Config → `chore`, docs → `docs`, tests → `test`, etc.
- Ordonne logiquement : config d'abord, refactoring, features, fixes, tests, docs en dernier
- **Attend votre validation** — jamais de commit automatique

### Etape 4 : Execution (apres votre V)

- `git reset HEAD` pour un etat propre
- Pour chaque commit du plan : `git add` des fichiers specifiques → `git commit -m "message"`
- Verification apres chaque commit
- Rapport final avec hash et message de chaque commit

---

## Architecture des fichiers

```
.claude/commands/
└── bmad-smart-commit.md              # Point d'entree (commande /smart-commit)

_bmad/custom/workflows/smart-commit/
├── workflow.md                        # Definition du workflow
└── steps-c/
    ├── step-01-context.md             # Analyse du contexte
    ├── step-02-validate.md            # Validation technique
    ├── step-03-plan.md                # Proposition du plan
    └── step-04-execute.md             # Execution des commits
```

### Principe d'architecture micro-fichier

- Chaque etape est un fichier autonome
- Chargement juste-a-temps (seule l'etape courante est chargee)
- Execution sequentielle stricte (pas de saut d'etape)
- Execution prescriptive (pas d'improvisation)

---

## Fichiers source

Les fichiers source complets sont disponibles dans le repertoire [`smart-commit/`](smart-commit/) de ce repo, prets a etre copies dans votre projet.

---

*Derniere verification : 2026-03-22 · [Signaler un probleme](../../.github/ISSUE_TEMPLATE/tool-update.md)*
