# Hooks de securite

> Outils et configurations de hooks pour proteger votre environnement Claude Code contre les injections de prompts, les actions non autorisees et les fuites de donnees.

---

## Outils de securite

| Outil | Description | GitHub |
|-------|-------------|--------|
| **claude-hooks** (Lasso Security) | Defense contre l'injection de prompts. Detecte 50+ patterns d'injection en temps reel | [lasso-security/claude-hooks](https://github.com/lasso-security/claude-hooks) |
| **claude-guardrails** (Dwarves) | Configuration de securite renforcee avec regles de refus de permissions | [dwarvesf/claude-guardrails](https://github.com/dwarvesf/claude-guardrails) |
| **claude-code-hooks-mastery** | Guide complet pour maitriser les hooks, avec exemples pour tous les evenements | [disler/claude-code-hooks-mastery](https://github.com/disler/claude-code-hooks-mastery) |

---

## Configurations pretes a copier

### Bloquer les commandes shell dangereuses

Empêche Claude d'executer des commandes destructives comme `rm -rf`, `DROP TABLE`, `sudo`, ou des commandes qui telechargeraient et executeraient du code externe.

```json
{
  "hooks": {
    "PreToolUse": [
      {
        "type": "command",
        "command": "node -e \"const d=JSON.parse(require('fs').readFileSync('/dev/stdin','utf8'));if(d.tool==='Bash'){const c=d.args?.command||'';if(/rm\\s+-rf|sudo\\s|DROP\\s+TABLE|TRUNCATE|curl.*\\|.*sh|wget.*\\|.*sh|chmod\\s+777|mkfs|dd\\s+if/i.test(c)){console.error('BLOQUE: commande dangereuse detectee');process.exit(1)}}\"",
        "description": "Bloquer les commandes shell dangereuses"
      }
    ]
  }
}
```

### Forcer le formatage apres chaque ecriture de fichier

Automatiquement formater avec Prettier chaque fichier que Claude ecrit ou modifie.

```json
{
  "hooks": {
    "PostToolUse": [
      {
        "type": "command",
        "command": "bash -c 'FILE=$(echo $CLAUDE_TOOL_OUTPUT | jq -r \".file_path // empty\"); if [ -n \"$FILE\" ] && [[ \"$FILE\" =~ \\.(ts|tsx|js|jsx|css|json|md)$ ]]; then npx prettier --write \"$FILE\" 2>/dev/null; fi'",
        "description": "Auto-formater avec Prettier apres ecriture",
        "matcher": {
          "tool": ["Write", "Edit"]
        }
      }
    ]
  }
}
```

### Notification desktop quand Claude termine une tache

Recevoir une notification quand Claude a fini de travailler (utile quand on fait autre chose pendant que Claude code).

```json
{
  "hooks": {
    "Stop": [
      {
        "type": "command",
        "command": "bash -c 'if command -v notify-send &>/dev/null; then notify-send \"Claude Code\" \"Tache terminee\"; elif command -v osascript &>/dev/null; then osascript -e \"display notification \\\"Tache terminee\\\" with title \\\"Claude Code\\\"\"; fi'",
        "description": "Notification desktop quand Claude finit"
      }
    ]
  }
}
```

### ESLint auto-fix apres edition

Appliquer automatiquement les corrections ESLint sur chaque fichier modifie.

```json
{
  "hooks": {
    "PostToolUse": [
      {
        "type": "command",
        "command": "bash -c 'FILE=$(echo $CLAUDE_TOOL_OUTPUT | jq -r \".file_path // empty\"); if [ -n \"$FILE\" ] && [[ \"$FILE\" =~ \\.(ts|tsx|js|jsx)$ ]]; then npx eslint --fix \"$FILE\" 2>/dev/null; fi'",
        "description": "ESLint auto-fix apres edition",
        "matcher": {
          "tool": ["Write", "Edit"]
        }
      }
    ]
  }
}
```

---

## Ou configurer les hooks

| Fichier | Portee | Commite ? |
|---------|--------|-----------|
| `~/.claude/settings.json` | Toutes vos sessions | Non (personnel) |
| `.claude/settings.json` | Ce projet (tous les devs) | Oui |
| `.claude/settings.local.json` | Ce projet (vous seul) | Non |

Vous pouvez aussi utiliser le menu interactif : `/hooks`

---

## Documentation officielle

- [Hooks Guide](https://code.claude.com/docs/en/hooks)
- [Hooks Reference](https://code.claude.com/docs/en/hooks-guide)

---

*Derniere verification : 2026-03-22 · [Signaler un probleme](../../.github/ISSUE_TEMPLATE/tool-update.md)*
