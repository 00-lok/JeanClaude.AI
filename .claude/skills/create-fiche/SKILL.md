---
name: create-fiche
description: "Generer une fiche outil complete a partir du template, en recherchant automatiquement les informations"
---

# Skill : Creer une fiche outil

## Declencheur
Quand l'utilisateur demande d'ajouter un outil au catalogue, ou utilise `/create-fiche <nom-outil>`.

## Processus

### 1. Identifier l'outil et la categorie

A partir du nom fourni :
- Chercher le depot GitHub (utiliser WebSearch ou gh CLI si disponible)
- Determiner la categorie appropriee (frameworks, mcp-servers, skills, plugins, hooks, orchestration, workflows, guides, resources)
- Pour les MCP servers, determiner la sous-categorie (official, databases, browser-automation, web-scraping, cloud-devops, api-integrations, monitoring-security, aggregators)

### 2. Collecter les informations

Rechercher et verifier :
- **URL GitHub exacte** — Verifier que le repo existe
- **Description** — Lire le README du repo
- **Stars** — Nombre approximatif (prefixer avec ~)
- **Installation** — Commande exacte depuis le README
- **Licence** — Depuis le repo
- **Statut** — Actif / Archive / Beta (verifier la date du dernier commit)
- **Fonctionnalites cles** — Extraire les features principales du README
- **Usage avec Claude Code** — Comment l'integrer concretement

### 3. Generer la fiche

Creer le fichier `categories/{categorie}/{nom-en-kebab-case}.md` en suivant EXACTEMENT le format de `templates/tool-template.md`.

Regles absolues :
- **Tout en francais** (sauf noms propres, commandes, URLs)
- **Aucune section vide** — Si l'info est indisponible, ecrire "Non disponible"
- **Nom de fichier en kebab-case** : `mon-outil.md`
- **Descriptions factuelles** — Pas de marketing, pas de superlatifs sans preuve
- **Exemples concrets** dans "Utilisation avec Claude Code" — pas de descriptions vagues
- **Date de verification** — Mettre la date du jour au format AAAA-MM-JJ

### 4. Mettre a jour les index

Apres creation de la fiche :
1. Ajouter une ligne dans le `README.md` de la categorie (trier par pertinence/stars)
2. Si l'outil a 10k+ stars ou est majeur pour l'ecosysteme, l'ajouter aussi dans le `README.md` racine

### 5. Verifier

- Relire la fiche une fois terminee
- Verifier que toutes les sections du template sont remplies
- Verifier que les liens internes sont corrects
- Verifier que les commandes d'installation sont exactes
