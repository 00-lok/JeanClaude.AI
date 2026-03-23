# Skills

Les skills sont des dossiers d'instructions, scripts et ressources que Claude charge dynamiquement pour ameliorer ses performances sur des taches specialisees. Ils suivent le standard ouvert **Agent Skills** (publie par Anthropic, adopte par Microsoft, OpenAI, Cursor, GitHub Copilot et 20+ plateformes).

Chaque skill necessite un fichier `SKILL.md` avec un frontmatter YAML (nom, description, declencheurs) et du contenu Markdown avec des instructions.

**Emplacement** : `.claude/skills/<n>/SKILL.md`

---

| Ressource | Description |
|-----------|-------------|
| [Skills officiels](official-skills.md) | Depot officiel `anthropics/skills` d'Anthropic |
| [Collections communautaires](community-collections.md) | Meilleures collections curatees de skills |
| [Places de marche](marketplaces.md) | Plateformes de decouverte et installation de skills |

---

## Difference entre skills et commandes slash

- **Skills** — Peuvent etre invoques automatiquement par Claude quand il detecte la pertinence, OU manuellement via `/nom`
- **Commandes slash** — Declenchees uniquement par l'utilisateur via `/nom`

---

## Comment installer un skill

```bash
# Via SkillKit (400K+ skills)
npx skillkit install <nom-du-skill>

# Via Claude Code Templates
npx claude-code-templates@latest --skill <nom-du-skill> --yes

# Manuellement
# Creer .claude/skills/<n>/SKILL.md dans votre projet
```

---

## Comment creer un skill

```markdown
---
name: mon-skill
description: Description de ce que fait le skill
triggers:
  - pattern: "quand Claude detecte ce pattern"
---

Instructions pour Claude quand ce skill est actif...
```

Documentation officielle : [code.claude.com/docs/en/skills](https://code.claude.com/docs/en/skills)
