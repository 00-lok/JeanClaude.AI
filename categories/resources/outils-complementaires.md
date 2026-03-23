# Outils complementaires

> Outils, utilitaires et integrations qui ne rentrent pas dans les autres categories mais sont precieux pour les utilisateurs de Claude Code.

---

## Analytique et suivi

| Outil | Description | Installation |
|-------|-------------|-------------|
| [ccusage](https://github.com/ryoppippi/ccusage) | CLI pour analyser la consommation de tokens et couts Claude Code depuis les fichiers JSONL locaux. Rapports quotidiens, hebdomadaires, mensuels | `npx ccusage daily` |
| [everything-claude-code](https://github.com/affaan-m/everything-claude-code) | Systeme d'optimisation de performance (gagnant hackathon Anthropic). Skills, instincts, memoire, securite. ~60% reduction de couts | `/plugin install everything-claude-code` |

## Gestion de configuration

| Outil | Description | Installation |
|-------|-------------|-------------|
| [ClaudeCTX](https://github.com/FGRibreau/claudectx) | Basculer rapidement entre configurations et comptes Claude Code. Gere les profils (Max, Team, personnel) | `brew install FGRibreau/tap/claudectx` |

## Integrations editeur

| Outil | Description | Installation |
|-------|-------------|-------------|
| [claude-code.nvim](https://github.com/greggh/claude-code.nvim) | Integration Claude Code dans Neovim. Toggle en un appui, detection/rechargement auto des fichiers modifies | Plugin lazy.nvim |
| [claudecode.nvim](https://github.com/coder/claudecode.nvim) | Integration par Coder, incluse dans LazyVim `extras/ai/claudecode` | Plugin lazy.nvim |
| Claudix | Extension VS Code (Vue 3/TypeScript) | VS Code Marketplace |
| claude-code-ide.el | Integration Emacs avec LSP | MELPA |

## Education et apprentissage

| Outil | Description | Installation |
|-------|-------------|-------------|
| [learn-claude-code](https://github.com/shareAI-lab/learn-claude-code) | Reconstruire l'architecture de Claude Code en ~300 lignes Python. Progression v0 a v3 (boucle agent → outils → sous-agents) | `git clone` + `pip install` |

## Clients alternatifs

| Outil | Description | Installation |
|-------|-------------|-------------|
| [OpenCode](https://github.com/opencode-ai/opencode) | Agent de coding terminal open-source, 75+ providers LLM, 100K+ stars | `npm i -g opencode-ai@latest` |
| [opcode](https://github.com/winfunc/opcode) | GUI desktop Tauri 2 pour gerer les sessions Claude Code, creer des agents, suivre l'usage | Binaires depuis les Releases GitHub |

---

*Derniere verification : 2026-03-22 · [Signaler un probleme](../../.github/ISSUE_TEMPLATE/tool-update.md)*
