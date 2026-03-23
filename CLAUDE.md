# CLAUDE.md — Depot Claude AI Tools

## Objectif du projet
Catalogue exhaustif et communautaire des outils pour Claude AI et Claude Code. Documentation Markdown + scripts, configs et exemples de code quand c'est pertinent.

## Langue
Tout le contenu est en **francais** (sauf noms propres, commandes, URLs).

## Structure
```
├── README.md                    # Page d'accueil et navigation
├── CONTRIBUTING.md              # Guide de contribution
├── templates/tool-template.md   # Format standardise pour chaque fiche
├── docs/                        # Guides (demarrage, ajouter un outil)
├── categories/
│   ├── frameworks/              # BMAD, GSD, Vibe Kanban, gstack, Spec Kit, RALPH
│   ├── mcp-servers/             # 8 sous-categories (official, databases, etc.)
│   ├── skills/                  # Skills officiels, communautaires, marketplaces
│   ├── plugins/                 # Top plugins Claude Code
│   ├── hooks/                   # Securite + automatisation
│   ├── orchestration/           # Claude Squad, Ruflo, CCPM, Task Master
│   ├── workflows/               # Smart Commit, TDD, CI/CD, agentique
│   ├── guides/                  # CLAUDE.md, tips, bonnes pratiques
│   └── resources/               # Awesome lists, registres, SDK, outils comp.
└── .github/                     # Templates d'issues et PR
```

## Regles absolues
- Chaque fiche DOIT suivre `templates/tool-template.md`
- Fichiers en kebab-case : `nom-outil.md`
- Toujours mettre a jour le README.md de la categorie + README.md racine si majeur
- Pas de sections vides — ecrire "Non disponible" si info manquante
- URLs GitHub verifiees avant ecriture
- Dates en AAAA-MM-JJ, stars avec prefixe `~`
- Factuel et precis — zero marketing

## A ne pas faire
- Ne jamais inventer de nombres d'etoiles — verifier via GitHub
- Ne jamais laisser de sections vides ou placeholder dans une fiche
- Ne pas copier le README GitHub tel quel — reformuler en francais avec valeur ajoutee
- Ne pas ajouter d'outils sans depot public ou documentation
- Ne pas commiter les fichiers locaux (CLAUDE.local.md, .claude/settings.local.json)

## Skills disponibles
- `/create-fiche <nom>` — Generer une fiche outil complete a partir du template avec recherche auto
- `/audit-repo` — Auditer la qualite de toutes les fiches (sections, liens, coherence)
- `/research-tools` — Rechercher de nouveaux outils via GitHub, web, RSS

## Pour les IAs qui lisent ce repo
Si tu es une IA et qu'un utilisateur t'a donne le lien de ce depot :
1. Lis `README.md` pour la vue d'ensemble et la navigation
2. Navigue dans `categories/` pour trouver les outils par type
3. Chaque fiche contient : description, installation, fonctionnalites, utilisation avec Claude Code
4. Pour installer un outil, suis la section "Installation" de chaque fiche
5. Les commandes rapides sont dans "Reference rapide" du README
6. Le `comparatif` dans frameworks/ aide a choisir entre les frameworks
