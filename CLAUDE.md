# CLAUDE.md — Depot Claude AI Tools

## Objectif du projet
Ce depot est un catalogue exhaustif et communautaire des outils, frameworks, skills, plugins, serveurs MCP, hooks, workflows et ressources pour Claude AI et Claude Code. Il contient de la documentation Markdown, mais aussi des scripts, configs et exemples de code quand c'est pertinent pour un outil.

## Langue
Tout le contenu est redige en **francais**.

## Structure du depot
```
├── README.md                    # Page d'accueil — vue d'ensemble et navigation
├── CONTRIBUTING.md              # Guide de contribution
├── CLAUDE.md                    # Ce fichier — instructions pour Claude
├── templates/tool-template.md   # Format standardise pour chaque fiche outil
├── docs/
│   ├── demarrage-rapide.md      # Guide de demarrage pour les utilisateurs
│   └── ajouter-un-outil.md     # Comment ajouter un outil au catalogue
├── categories/
│   ├── frameworks/              # BMAD, GSD, Vibe Kanban, Claude Code Templates
│   ├── mcp-servers/             # Serveurs MCP par sous-categorie
│   │   ├── official/            # Serveurs MCP officiels Anthropic
│   │   ├── databases/           # PostgreSQL, MongoDB, etc.
│   │   ├── browser-automation/  # Playwright, Puppeteer
│   │   ├── web-scraping/        # Firecrawl, Tavily
│   │   ├── cloud-devops/        # AWS, Azure, Cloudflare
│   │   ├── api-integrations/    # GitHub, Notion, Slack
│   │   ├── monitoring-security/ # Sentry, Datadog, SonarQube
│   │   └── aggregators/         # Pipedream, Composio
│   ├── skills/                  # Skills, collections, places de marche
│   ├── plugins/                 # Plugins Claude Code
│   ├── hooks/                   # Hooks de securite et d'automatisation
│   ├── orchestration/           # Multi-agents, gestion de taches
│   ├── workflows/               # TDD, CI/CD, workflows agentiques
│   ├── guides/                  # Bonnes pratiques, astuces, CLAUDE.md
│   └── resources/               # Listes awesome, registres, Agent SDK
└── .github/                     # Templates d'issues et PR
```

## Regles de contribution
- Chaque fiche outil DOIT suivre le format de `templates/tool-template.md`
- Les noms de fichiers utilisent le kebab-case : `nom-outil.md`
- Lors de l'ajout d'un outil, toujours mettre a jour le `README.md` index de la categorie
- Pas de sections vides — si l'information est indisponible, noter "Non disponible"
- Toutes les URLs GitHub doivent etre verifiees
- Les dates utilisent le format AAAA-MM-JJ
- Pas de langage marketing — etre factuel et precis
- Les nombres d'etoiles sont approximatifs et notes avec le prefixe `~`
- Le contenu peut inclure du code, des scripts et des configs quand c'est pertinent
- Tout le contenu est en francais

## Pour les IAs qui lisent ce repo
Si tu es une IA et qu'un utilisateur t'a donne le lien de ce depot :
1. Lis le `README.md` pour une vue d'ensemble de tous les outils disponibles
2. Navigue dans `categories/` pour trouver les outils par type
3. Chaque fiche outil contient : description, installation, fonctionnalites, utilisation avec Claude Code
4. Pour installer un outil, suis les instructions de la section "Installation" de chaque fiche
5. Les commandes d'installation les plus courantes sont dans la section "Reference rapide" du README
