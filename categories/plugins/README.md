# Plugins

Les plugins Claude Code sont des packages qui regroupent skills, serveurs MCP, hooks et commandes en un seul package distribuable. Ils s'installent en une commande via `/plugin install <nom>`.

**En mars 2026** : 9 000+ plugins disponibles a travers les places de marche.

---

| Ressource | Description |
|-----------|-------------|
| [Top plugins](top-plugins.md) | Les plugins les plus impactants et populaires |

---

## Comment installer un plugin

```bash
# Via le CLI Claude Code
/plugin install <nom-du-plugin>

# Parcourir les plugins disponibles
/plugin

# Depuis le depot officiel
# Les plugins du depot anthropics/claude-plugins-official
# sont accessibles directement via /plugin
```

---

## Comment creer un plugin

- Utilisez `/plugin-dev:create-plugin` pour une creation assistee par IA
- Utilisez le flag `--plugin-dir` pour le developpement local
- Specification : [github.com/anthropics/claude-code/tree/main/plugins](https://github.com/anthropics/claude-code/tree/main/plugins)
- Documentation : [code.claude.com/docs/en/plugins](https://code.claude.com/docs/en/plugins)

---

## Depots de reference

| Depot | Description |
|-------|-------------|
| [anthropics/claude-plugins-official](https://github.com/anthropics/claude-plugins-official) | Repertoire officiel Anthropic de plugins de haute qualite |
| [ComposioHQ/awesome-claude-plugins](https://github.com/ComposioHQ/awesome-claude-plugins) | Registre curate et toolkit d'extensions |
| [quemsah/awesome-claude-plugins](https://github.com/quemsah/awesome-claude-plugins) | Collection automatisee avec metriques d'adoption |
