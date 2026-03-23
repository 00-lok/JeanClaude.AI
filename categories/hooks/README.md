# Hooks

Les hooks Claude Code sont des gestionnaires d'evenements du cycle de vie qui s'executent automatiquement en reponse a des evenements specifiques. Ils permettent l'automatisation, le controle de securite et l'observabilite sans intervention manuelle.

**En mars 2026** : 21 evenements lifecycle, 4 types de handlers.

---

| Ressource | Description |
|-----------|-------------|
| [Hooks de securite](security-hooks.md) | Defense injection de prompts, guardrails, controle des permissions |
| [Hooks d'automatisation](automation-hooks.md) | Auto-formatage, notifications, automatisation Git |

---

## Evenements disponibles

### Execution d'outils

| Evenement | Declencheur | Usage type |
|-----------|-------------|-----------|
| `PreToolUse` | Avant l'execution d'un outil | Approuver/refuser des actions, securite |
| `PostToolUse` | Apres l'execution reussie d'un outil | Formatage, linting |
| `PostToolUseFailure` | Apres l'echec d'un outil | Logging, alertes |

### Cycle de vie de session

| Evenement | Declencheur | Usage type |
|-----------|-------------|-----------|
| `SessionStart` | Debut de session | Initialisation |
| `SessionEnd` | Fin de session | Nettoyage, rapports |
| `Setup` | Via `--init`, `--init-only` ou `--maintenance` | Installation |

### Interaction utilisateur

| Evenement | Declencheur | Usage type |
|-----------|-------------|-----------|
| `UserPromptSubmit` | Avant que Claude traite un prompt | Validation, enrichissement |
| `Notification` | Quand Claude envoie une alerte | Notifications externes |
| `Stop` | Quand Claude finit de repondre | Post-traitement |
| `SubagentStop` | Quand un sous-agent finit | Orchestration |
| `PermissionRequest` | Quand Claude demande une permission | Auto-approbation |

---

## Types de handlers

| Type | Description |
|------|-------------|
| **Command** | Commandes shell en sous-processus, reçoivent du JSON sur stdin |
| **HTTP** | Envoient des requetes a des endpoints HTTP |
| **Prompt** | Envoient du texte a un modele Claude rapide pour evaluation single-turn |
| **Agent** | Lancent un sous-agent avec acces a Read, Grep, Glob pour verification multi-turn |

---

## Configuration

Les hooks se configurent dans les fichiers de parametres :

```json
{
  "hooks": {
    "PreToolUse": [
      {
        "type": "command",
        "command": "node scripts/validate-tool.js",
        "description": "Valider les appels d'outils"
      }
    ],
    "PostToolUse": [
      {
        "type": "command",
        "command": "npx prettier --write $FILE",
        "description": "Formater apres ecriture"
      }
    ]
  }
}
```

Emplacements :
- `~/.claude/settings.json` (niveau utilisateur)
- `.claude/settings.json` (niveau projet)
- `.claude/settings.local.json` (local, non commite)

Ou via le menu interactif : `/hooks`

Documentation officielle : [code.claude.com/docs/en/hooks](https://code.claude.com/docs/en/hooks)
