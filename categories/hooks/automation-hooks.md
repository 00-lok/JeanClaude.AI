# Hooks d'automatisation

> Hooks pour automatiser le formatage, les notifications, la gestion Git et d'autres taches repetitives dans Claude Code.

---

## Outils d'automatisation

| Outil | Description | Evenement |
|-------|-------------|-----------|
| **CC Notify** | Notifications desktop pour les evenements de taches. Cross-plateforme | `Stop`, `Notification` |
| **Britfix** | Convertit l'anglais americain en anglais britannique dans la documentation | `PostToolUse` |
| **HCOM** | Systeme de communication inter-hooks. Permet aux hooks de se coordonner | Tous |
| **cchooks** | SDK Python avec API propre pour la creation de hooks | Tous |
| **GitButler hooks** | Gestion automatique des branches et commits Git pendant que Claude travaille | `PostToolUse` |

---

## Exemples pratiques

### Auto-formater apres ecriture de fichier

```json
{
  "hooks": {
    "PostToolUse": [
      {
        "type": "command",
        "command": "npx prettier --write $CLAUDE_FILE_PATH",
        "description": "Formater avec Prettier apres ecriture",
        "matcher": {
          "tool": "Write"
        }
      }
    ]
  }
}
```

### Notification desktop quand Claude a fini

```json
{
  "hooks": {
    "Stop": [
      {
        "type": "command",
        "command": "notify-send 'Claude Code' 'Tache terminee'",
        "description": "Notification quand Claude finit"
      }
    ]
  }
}
```

### Linting automatique apres edition

```json
{
  "hooks": {
    "PostToolUse": [
      {
        "type": "command",
        "command": "npx eslint --fix $CLAUDE_FILE_PATH",
        "description": "ESLint auto-fix apres edition",
        "matcher": {
          "tool": "Edit"
        }
      }
    ]
  }
}
```

---

## Ressources

| Ressource | Description |
|-----------|-------------|
| [claude-code-hooks-mastery](https://github.com/disler/claude-code-hooks-mastery) | Guide complet pour maitriser les hooks |
| [GitButler Hooks](https://docs.gitbutler.com/features/ai-integration/claude-code-hooks) | Documentation hooks GitButler |
| [Documentation officielle](https://code.claude.com/docs/en/hooks) | Guide officiel Anthropic |

---

*Derniere verification : 2026-03-22 · [Signaler un probleme](../../.github/ISSUE_TEMPLATE/tool-update.md)*
