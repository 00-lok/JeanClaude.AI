<div align="center">

# Claude AI Tools

### Le catalogue definitif et communautaire des outils, frameworks et ressources pour Claude AI

[![Licence : MIT](https://img.shields.io/badge/Licence-MIT-blue.svg)](LICENSE)
[![PRs Bienvenues](https://img.shields.io/badge/PRs-bienvenues-brightgreen.svg)](CONTRIBUTING.md)
[![Derniere MAJ](https://img.shields.io/badge/Dernière%20MAJ-Mars%202026-orange.svg)](#)
[![Outils Catalogues](https://img.shields.io/badge/Outils%20Catalogués-100%2B-purple.svg)](#categories)

**Chaque outil est verifie, documente selon un format standardise, et maintenu a jour.**

[Demarrage rapide](docs/demarrage-rapide.md) · [Ajouter un outil](docs/ajouter-un-outil.md) · [Contribuer](CONTRIBUTING.md)

</div>

---

## Pourquoi ce repo ?

L'ecosysteme Claude AI est immense — des milliers de serveurs MCP, des centaines de skills, des dizaines de frameworks. Trouver le **bon outil** pour votre workflow ne devrait pas prendre des heures.

Ce depot fournit :

- **Documentation standardisee** — Chaque outil suit le meme format : description, installation, fonctionnalites, utilisation avec Claude Code
- **Informations verifiees** — Chaque entree est manuellement verifiee avec des liens, commandes et statuts exacts
- **Categorisation claire** — Trouvez ce dont vous avez besoin en secondes
- **Documentation vivante** — Mise a jour regulierement selon l'evolution de l'ecosysteme

---

## Categories

### Frameworks

Methodologies et systemes de developpement complets pour Claude AI.

| Outil | Description | Stars |
|-------|-------------|-------|
| [BMAD Method](categories/frameworks/bmad-method.md) | Framework agile complet avec 12+ agents IA specialises | ~41.8k |
| [GSD (Get Shit Done)](categories/frameworks/gsd.md) | Context engineering et developpement spec-driven | ~39k |
| [Vibe Kanban](categories/frameworks/vibe-kanban.md) | Orchestration kanban pour 10+ agents de coding | ~23.6k |
| [Claude Code Templates](categories/frameworks/claude-code-templates.md) | 100+ configs, agents et commandes prets a l'emploi | ~23.4k |
| [gstack](categories/frameworks/gstack.md) | Setup Claude Code de Garry Tan (YC) — 15 outils role-based | ~20k |
| [Spec Kit](categories/frameworks/spec-kit.md) | Toolkit GitHub pour le developpement spec-driven | — |
| [RALPH](categories/frameworks/ralph.md) | Boucle de dev IA autonome avec garde-fous intelligents | — |

→ [Voir tous les frameworks](categories/frameworks/) · [Comparatif detaille](categories/frameworks/comparatif.md)

---

### Serveurs MCP

Serveurs Model Context Protocol qui etendent les capacites de Claude.

| Sous-categorie | Description | Nombre |
|----------------|-------------|--------|
| [Officiels](categories/mcp-servers/official/) | Serveurs de reference Anthropic (Filesystem, Git, Memory, etc.) | 7 |
| [Bases de donnees](categories/mcp-servers/databases/) | PostgreSQL, MongoDB, DuckDB, Neo4j, etc. | 14+ |
| [Automatisation navigateur](categories/mcp-servers/browser-automation/) | Playwright, Puppeteer, Browserbase | 4+ |
| [Web scraping](categories/mcp-servers/web-scraping/) | Firecrawl, Apify, Bright Data, Tavily | 8+ |
| [Cloud et DevOps](categories/mcp-servers/cloud-devops/) | AWS, Azure, Cloudflare, Vercel, Kubernetes | 12+ |
| [Integrations API](categories/mcp-servers/api-integrations/) | GitHub, Notion, Slack, Linear, Stripe | 10+ |
| [Monitoring et securite](categories/mcp-servers/monitoring-security/) | Sentry, Datadog, Grafana, SonarQube | 10+ |
| [Agregateurs](categories/mcp-servers/aggregators/) | Pipedream, Composio, MetaMCP | 5+ |

→ [Voir tous les serveurs MCP](categories/mcp-servers/)

---

### Skills

Jeux d'instructions specialises qui ameliorent le comportement de Claude sur des taches specifiques.

| Ressource | Description |
|-----------|-------------|
| [Skills officiels](categories/skills/official-skills.md) | Depot officiel `anthropics/skills` d'Anthropic |
| [Collections communautaires](categories/skills/community-collections.md) | Meilleures collections curatees (400K+ via registres) |
| [Places de marche](categories/skills/marketplaces.md) | SkillHub, SkillsMP, claude-plugins.dev |

→ [Voir tous les skills](categories/skills/)

---

### Plugins

Packages regroupant skills, hooks, commandes et serveurs MCP.

| Ressource | Description |
|-----------|-------------|
| [Top plugins](categories/plugins/top-plugins.md) | Plugins les plus impactants (feature-dev, Context7, Claude-Mem, etc.) |

→ [Voir tous les plugins](categories/plugins/)

---

### Hooks

Gestionnaires d'evenements du cycle de vie pour l'automatisation, la securite et l'observabilite.

| Ressource | Description |
|-----------|-------------|
| [Hooks de securite](categories/hooks/security-hooks.md) | Defense contre l'injection de prompts, guardrails, controle des permissions |
| [Hooks d'automatisation](categories/hooks/automation-hooks.md) | Auto-formatage, notifications, automatisation Git |

→ [Voir tous les hooks](categories/hooks/)

---

### Orchestration

Outils de coordination multi-agents et de gestion de taches.

| Outil | Description | Stars |
|-------|-------------|-------|
| [Claude Squad](categories/orchestration/claude-squad.md) | Application terminal pour gerer des sessions agents en parallele | — |
| [Ruflo](categories/orchestration/ruflo.md) | Plateforme enterprise de swarm multi-agents | — |
| [CCPM](categories/orchestration/ccpm.md) | Orchestration GitHub Issues + Git worktrees | ~7.6k |
| [Claude Task Master](categories/orchestration/claude-task-master.md) | Gestion de taches IA a partir de PRDs | ~25.3k |

→ [Voir tous les outils d'orchestration](categories/orchestration/)

---

### Workflows

Methodologies de developpement et integrations CI/CD.

| Ressource | Description |
|-----------|-------------|
| [Smart Commit](categories/workflows/smart-commit.md) | Commits atomiques intelligents au format Conventional Commits — installable |
| [TDD / BDD](categories/workflows/tdd-bdd.md) | Workflows de developpement pilote par les tests avec Claude Code |
| [CI/CD](categories/workflows/ci-cd.md) | GitHub Actions, revue automatisee de PR |
| [Workflows agentiques](categories/workflows/agentic-workflows.md) | Pipelines de developpement multi-agents |

→ [Voir tous les workflows](categories/workflows/)

---

### Guides et bonnes pratiques

| Ressource | Description |
|-----------|-------------|
| [Bonnes pratiques CLAUDE.md](categories/guides/claude-md-best-practices.md) | Comment ecrire des fichiers CLAUDE.md efficaces |
| [Astuces et conseils](categories/guides/tips-and-tricks.md) | 45+ astuces pratiques pour Claude Code |
| [Bonnes pratiques](categories/guides/best-practices.md) | Configuration, workflows et conventions |

→ [Voir tous les guides](categories/guides/)

---

### Ressources

| Ressource | Description |
|-----------|-------------|
| [Listes awesome](categories/resources/awesome-lists.md) | Listes curatees communautaires et repertoires |
| [Registres et repertoires](categories/resources/registries-directories.md) | MCP.so, Smithery, PulseMCP, Glama, etc. |
| [Agent SDK](categories/resources/agent-sdk.md) | SDKs officiels Python et TypeScript |
| [Outils complementaires](categories/resources/outils-complementaires.md) | Analytique, integrations editeur, clients alternatifs |

→ [Voir toutes les ressources](categories/resources/)

---

## Reference rapide

### Commandes d'installation

```bash
# Frameworks
npx bmad-method install                    # BMAD Method
npx get-shit-done-cc@latest                # GSD
npx vibe-kanban                            # Vibe Kanban
npx claude-code-templates@latest           # Claude Code Templates

# Skills
npx skillkit install <nom-du-skill>        # N'importe quel skill via SkillKit

# Plugins
/plugin install <nom-du-plugin>            # Via Claude Code CLI
```

### Chiffres cles de l'ecosysteme (mars 2026)

| Metrique | Nombre |
|----------|--------|
| Serveurs MCP indexes | 17 500+ |
| Skills via registres | 400 000+ |
| Plugins disponibles | 9 000+ |
| Telechargements SDK mensuels | 97M+ |
| Evenements lifecycle hooks | 21 |

---

## Comment utiliser ce repo

1. **Parcourez par categorie** — Utilisez la table des matieres ci-dessus pour trouver le type d'outil dont vous avez besoin
2. **Lisez la fiche outil** — Chaque outil a un fichier `.md` dedie avec toutes les informations
3. **Installez et configurez** — Suivez les instructions d'installation sur chaque page
4. **Contribuez** — Vous connaissez un outil manquant ? [Ajoutez-le](docs/ajouter-un-outil.md)

---

## Contribuer

Les contributions sont les bienvenues ! Consultez [CONTRIBUTING.md](CONTRIBUTING.md) pour les directives.

**Processus rapide :**
1. Forkez le repo
2. Creez une fiche outil a partir du [template](templates/tool-template.md)
3. Mettez a jour le README de la categorie
4. Soumettez une PR

---

## Licence

Licence MIT — voir [LICENSE](LICENSE) pour les details.

---

<div align="center">

**Construit pour la communaute Claude AI**

Si ce repo vous aide, mettez une etoile pour aider les autres a le trouver.

</div>
