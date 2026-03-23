# Agent SDK

> SDKs officiels d'Anthropic pour construire des agents personnalises bases sur Claude.

---

## SDKs officiels

| SDK | Langage | GitHub |
|-----|---------|--------|
| **claude-agent-sdk-python** | Python | [anthropics/claude-agent-sdk-python](https://github.com/anthropics/claude-agent-sdk-python) |
| **claude-agent-sdk-typescript** | TypeScript | [anthropics/claude-agent-sdk-typescript](https://github.com/anthropics/claude-agent-sdk-typescript) |
| **claude-agent-sdk-demos** | Multi | [anthropics/claude-agent-sdk-demos](https://github.com/anthropics/claude-agent-sdk-demos) |

---

## Ce que ca fait

Le Claude Agent SDK permet de construire des agents IA personnalises qui utilisent les memes capacites que Claude Code : execution d'outils, serveurs MCP, streaming, gestion de conversation. Vous pouvez creer des agents specialises pour vos propres cas d'usage.

---

## Fonctionnalites cles

- **Decorateur `@tool`** — Definir des outils personnalises que l'agent peut utiliser
- **Creation de serveurs MCP** — Construire vos propres serveurs MCP
- **Streaming** — Reponses en temps reel
- **Boucles de conversation** — Gestion multi-tours automatique
- **Systeme multi-agents** — Orchestration de plusieurs agents

---

## Exemple rapide (Python)

```python
from claude_agent_sdk import Agent, tool

@tool
def get_weather(city: str) -> str:
    """Obtenir la meteo d'une ville."""
    return f"Il fait 22°C a {city}"

agent = Agent(
    model="claude-sonnet-4-6",
    tools=[get_weather]
)

response = agent.run("Quel temps fait-il a Paris ?")
```

---

## Ressources d'apprentissage

| Ressource | Description |
|-----------|-------------|
| [Documentation officielle](https://platform.claude.com/docs/en/agent-sdk/overview) | Reference complete de l'API |
| [kenneth-liao/claude-agent-sdk-intro](https://github.com/kenneth-liao/claude-agent-sdk-intro) | Modules d'apprentissage couvrant requetes, parsing, outils, config agents, boucles, MCP, multi-agents |
| [claude-quickstarts](https://github.com/anthropics/claude-quickstarts) | Collection de starters deployables utilisant l'API Claude |
| [Guide de construction d'agents](https://gist.github.com/dabit3/93a5afe8171753d0dbfd41c80033171d) | Tutoriel pratique pour construire un agent de revue de code |

---

*Derniere verification : 2026-03-22 · [Signaler un probleme](../../.github/ISSUE_TEMPLATE/tool-update.md)*
