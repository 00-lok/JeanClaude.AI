# claude-mem

> Memoire persistante entre sessions Claude Code via SQLite + Chroma Vector Database. Claude se souvient de tout — decisions architecturales, corrections de bugs, preferences — d'une session a l'autre.

| Info | Detail |
|------|--------|
| **GitHub** | [thedotmack/claude-mem](https://github.com/thedotmack/claude-mem) |
| **Site web** | Non disponible |
| **Installation** | `/plugin install claude-mem` |
| **Categorie** | Plugin / Memoire |
| **Licence** | MIT |
| **Statut** | Actif |
| **Stars** | ~35.9k |
| **Derniere verification** | 2026-03-22 |

---

## Ce que ca fait

Claude Code oublie tout entre les sessions. Vous corrigez un bug lundi, et mardi Claude re-introduit le meme bug parce qu'il ne se souvient pas de la correction. claude-mem resout ce probleme en capturant automatiquement ce que Claude fait pendant les sessions et en reinjectant le contexte pertinent dans les sessions futures.

Le systeme utilise une **base SQLite** pour le stockage structure et une **base vectorielle Chroma** pour la recherche semantique. Quand une nouvelle session demarre, claude-mem retrouve les informations pertinentes (decisions, corrections, patterns) et les injecte dans le contexte — Claude "se souvient" sans que vous ayez besoin de re-expliquer.

Les hooks lifecycle capturent les evenements cles : debut de session, prompts utilisateur, resultats d'outils, resumes, et fin de session.

---

## Fonctionnalites cles

- **Capture automatique** — Enregistre ce que Claude fait via les hooks lifecycle (SessionStart, UserPromptSubmit, PostToolUse, Summary, SessionEnd)
- **Compression IA** — Utilise le Claude Agent SDK pour comprimer les informations avant stockage, gardant l'essentiel
- **Recherche semantique** — Base vectorielle Chroma pour retrouver les informations par sens, pas juste par mots-cles
- **Recherche hybride** — Combine recherche semantique + mots-cles (SQLite) pour une precision maximale
- **Injection contextuelle** — Les informations pertinentes sont automatiquement injectees au debut de chaque session
- **Stockage local** — Tout reste sur votre machine, pas de donnees envoyees a l'exterieur

---

## Installation

```bash
/plugin install claude-mem
```

### Prerequis

- Claude Code CLI

---

## Utilisation avec Claude Code

```bash
# claude-mem fonctionne automatiquement apres installation

# Session 1 : Vous corrigez un bug
"Le bug dans le module de paiement etait du a un race condition
 sur le verrou de transaction. Fix: ajouter un mutex async."
# → claude-mem enregistre : bug paiement, race condition, fix mutex

# Session 2 (le lendemain) : Vous travaillez sur le meme module
"Ajoute un nouveau mode de paiement au module de paiement"
# → claude-mem injecte automatiquement :
#   "Contexte precedent : race condition corrigee avec mutex async.
#    Faire attention aux acces concurrents sur les transactions."
# → Claude sait qu'il doit utiliser le meme pattern de mutex

# Session 3 : Vous demandez explicitement
"Qu'est-ce qu'on a corrige la semaine derniere dans le module auth ?"
# → claude-mem retrouve les informations par recherche semantique
```

### Ce que claude-mem retient

- Decisions architecturales ("On utilise le pattern Repository, pas Active Record")
- Corrections de bugs et leur cause racine
- Preferences de code ("Tests colocalisees, pas dans un dossier `__tests__/` separe")
- Patterns du projet ("Les hooks sont dans `src/hooks/`, les utils dans `src/lib/`")
- Erreurs a eviter ("Ne pas toucher au fichier `migration-001.sql`")

---

## Configuration

claude-mem stocke ses donnees dans le repertoire du projet. La base SQLite et les embeddings Chroma sont locaux.

---

## Liens

- [Depot GitHub](https://github.com/thedotmack/claude-mem)

---

*Derniere verification : 2026-03-22 · [Signaler un probleme](../../.github/ISSUE_TEMPLATE/tool-update.md)*
