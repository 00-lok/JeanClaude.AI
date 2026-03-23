# Places de marche de skills

> Plateformes en ligne pour decouvrir, evaluer et installer des skills pour Claude Code.

---

## Principales places de marche

| Plateforme | Taille | URL | Description |
|------------|--------|-----|-------------|
| **SkillHub** | 7 000+ | [skillhub.club](https://www.skillhub.club) | Skills evalues par IA, filtrage par qualite |
| **SkillsMP** | 500 000+ | [skillsmp.com](https://skillsmp.com/) | Plus grande place de marche, recherche avancee |
| **claude-plugins.dev** | — | [claude-plugins.dev](https://claude-plugins.dev/) | Registre communautaire avec CLI d'installation |
| **aitmpl.com** | 100+ | [aitmpl.com](https://www.aitmpl.com/) | Navigateur de templates Claude Code (skills + agents + commandes) |

---

## Installation depuis une place de marche

```bash
# Via SkillKit (compatible avec toutes les places de marche)
npx skillkit install <nom-du-skill>

# Via Claude Code Templates
npx claude-code-templates@latest --skill <nom-du-skill> --yes

# Via le CLI Claude Code (plugins incluant des skills)
/plugin install <nom-du-plugin>
```

---

*Derniere verification : 2026-03-22 · [Signaler un probleme](../../.github/ISSUE_TEMPLATE/tool-update.md)*
