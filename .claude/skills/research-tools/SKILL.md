---
name: research-tools
description: "Rechercher de nouveaux outils Claude AI a ajouter au catalogue via GitHub, web et flux RSS"
---

# Skill : Rechercher de nouveaux outils

## Declencheur
Quand l'utilisateur demande de chercher de nouveaux outils, de mettre a jour le catalogue, ou utilise `/research-tools`.

## Processus

### 1. Recherche GitHub

Executer ces recherches en parallele :

```bash
# Repos Claude Code trending (par etoiles)
gh search repos "claude code" --sort=stars --order=desc --limit=30

# Nouveaux MCP servers
gh search repos "mcp server" --sort=updated --limit=30

# Skills et plugins recents
gh search repos "claude skills" --sort=updated --limit=20
gh search repos "claude code plugin" --sort=updated --limit=20

# Frameworks et workflows
gh search repos "claude code workflow" --sort=stars --limit=20
gh search repos "claude code framework" --sort=stars --limit=20

# Repos crees recemment (derniers 30 jours)
gh search repos "claude" --sort=stars --created=">$(date -d '30 days ago' +%Y-%m-%d 2>/dev/null || date -v-30d +%Y-%m-%d)" --limit=30
```

### 2. Recherche web

Utiliser WebSearch pour :
- "best new claude code tools {mois} {annee}"
- "new mcp servers {mois} {annee}"
- "claude code ecosystem updates"
- Verifier les sites de reference : pulsemcp.com, mcp.so, smithery.ai

### 3. Filtrage

Pour chaque outil trouve, verifier :
- Est-il DEJA dans notre catalogue ? (chercher dans `categories/`)
- Est-il pertinent pour Claude AI ? (pas juste un projet qui mentionne Claude)
- Est-il suffisamment mature ? (au moins un README, des commits recents, pas un fork trivial)
- A-t-il une valeur ajoutee ? (apporte quelque chose que les outils existants ne font pas)

### 4. Rapport de decouverte

Produire un rapport structure :

```
## Nouveaux outils decouverts — {date}

### Haute priorite (a ajouter rapidement)
| Outil | GitHub | Stars | Categorie | Pourquoi |
|-------|--------|-------|-----------|----------|
| {nom} | {url}  | {N}   | {cat}     | {raison} |

### Moyenne priorite (a evaluer)
| Outil | GitHub | Stars | Categorie | Pourquoi |
|-------|--------|-------|-----------|----------|

### Deja catalogues (pas d'action)
| Outil | Fiche existante |
|-------|----------------|

### Rejetes (pas pertinent)
| Outil | Raison du rejet |
|-------|----------------|
```

### 5. Actions suggerees

Pour chaque outil haute priorite, proposer :
- "Voulez-vous que je cree la fiche pour {nom} ? (`/create-fiche {nom}`)"

## Frequence recommandee

- Lancer `/research-tools` au moins 1 fois par semaine pour rester a jour
- Apres un evenement majeur Anthropic (release, blog post), lancer immediatement
