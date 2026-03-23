# Top plugins

> Les plugins Claude Code les plus impactants et populaires, avec exemples d'utilisation concrets.

---

## Plugins essentiels

### feature-dev — Developpement structure de fonctionnalites

**Installations** : 89 000+

Le plugin le plus populaire. Il impose un processus structure pour le developpement de fonctionnalites : specs → implementation → tests → revue. Au lieu de coder directement, Claude suit un pipeline defini.

```bash
# Installer
/plugin install feature-dev

# Utiliser
/feature-dev "Ajouter un systeme de notifications push"

# Claude va suivre ce pipeline :
# 1. Specification — Definir les exigences, les cas d'usage, les criteres d'acceptation
# 2. Design — Choisir l'architecture, les composants, les interfaces
# 3. Implementation — Ecrire le code en suivant le design
# 4. Tests — Ecrire et executer les tests unitaires et d'integration
# 5. Revue — Auto-revue du code, verification des bonnes pratiques
```

---

### Context7 — Documentation de bibliotheques a jour

Injecte la documentation officielle et a jour de vos bibliotheques directement dans la session Claude. Plus besoin que Claude invente des APIs qui n'existent pas.

```bash
# Installer
/plugin install context7

# Utiliser — Claude utilise automatiquement Context7
# Quand vous demandez "utilise Prisma pour creer un schema",
# Claude consulte la doc Prisma v6.x actuelle au lieu de
# se baser sur ses connaissances d'entrainement (potentiellement obsoletes)
```

**Quand c'est utile** : Quand vous travaillez avec des bibliotheques qui evoluent vite (Next.js, Prisma, Tailwind, etc.) et que Claude utilise des APIs depreciees.

---

### Claude-Mem — Memoire persistante entre sessions

Permet a Claude de conserver le contexte et les preferences entre les sessions. Claude se souvient de vos conventions, de l'etat du projet, de vos preferences.

```bash
# Installer
/plugin install claude-mem

# Claude se souvient automatiquement entre les sessions :
# - "Tu preferes les composants fonctionnels React"
# - "Le projet utilise Prisma, pas TypeORM"
# - "Les tests sont dans __tests__/, pas a cote du code"
```

---

### connect-apps — Pont vers 500+ services SaaS

Connecte Claude a des services externes pour executer des actions reelles : envoyer des emails, creer des issues GitHub, poster sur Slack.

```bash
# Installer
/plugin install connect-apps

# Exemples d'actions disponibles :
# "Envoie un email a l'equipe pour prevenir du deploiement"
# "Cree une issue GitHub avec le bug que je viens de decrire"
# "Poste un message dans #releases sur Slack"
```

---

### Local-Review — Revues de code paralleles

Lance des revues de code automatisees en local, en parallele. Analyse la qualite, la securite, la performance et les conventions.

```bash
# Installer
/plugin install local-review

# Lancer une revue sur les changements en cours
/local-review

# Claude analyse en parallele :
# - Qualite du code (lisibilite, complexite, duplication)
# - Securite (injections, fuites de donnees, permissions)
# - Performance (requetes N+1, re-renders, caching)
# - Conventions (nommage, structure, patterns du projet)
```

---

## Installation et gestion des plugins

```bash
# Parcourir les plugins disponibles
/plugin

# Installer un plugin
/plugin install <nom>

# Lister les plugins installes
/plugin list

# Desinstaller un plugin
/plugin uninstall <nom>
```

## Depots de reference

| Depot | Description |
|-------|-------------|
| [anthropics/claude-plugins-official](https://github.com/anthropics/claude-plugins-official) | Repertoire officiel Anthropic |
| [ComposioHQ/awesome-claude-plugins](https://github.com/ComposioHQ/awesome-claude-plugins) | Registre curate communautaire |

---

*Derniere verification : 2026-03-22 · [Signaler un probleme](../../.github/ISSUE_TEMPLATE/tool-update.md)*
