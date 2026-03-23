# Serveurs MCP — Integrations API

Serveurs MCP pour connecter Claude a des services SaaS, outils de productivite et plateformes de collaboration.

---

| Serveur | Description | Service | Maintenu par |
|---------|-------------|---------|-------------|
| [GitHub](https://github.com/modelcontextprotocol/servers-archived) | PRs, issues, repos, recherche de code, workflows | Dev | Communaute (archive officiel) |
| [Notion](https://github.com/makenotion/notion-mcp-server) | Integration officielle : pages, bases de donnees, blocs | Productivite | Notion (officiel) |
| Slack | Gestion de canaux, messagerie, recherche | Communication | Communaute (archive officiel) |
| [Linear](https://linear.app/) | Issues, projets, commentaires, gestion de sprints | Gestion de projet | Linear |
| Atlassian | Elements de travail Jira + pages Confluence | Gestion de projet | Communaute |
| Google Drive | Acces et recherche de fichiers Google | Stockage | Communaute (archive officiel) |
| [Stripe](https://stripe.com/) | Paiements, abonnements, factures, clients | Finance | Communaute |
| PayPal | Integration plateforme de paiement | Finance | Communaute |
| Twilio | Services de communication (SMS, voix, verification) | Communication | Communaute |
| HubSpot | CRM, contacts, deals, marketing | CRM | Communaute |
| Mailchimp | Campagnes email, audiences, templates | Marketing | Communaute |

---

## Exemple de configuration

```json
{
  "mcpServers": {
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "ghp_votre_token"
      }
    }
  }
}
```

---

## Recommandation

Pour connecter Claude a **plusieurs services en une fois**, considerez les [Agregateurs](../aggregators/) comme Pipedream (2 500 APIs) ou Composio (500+ apps) plutot que de configurer chaque serveur MCP individuellement.

---

*Derniere verification : 2026-03-22 · [Signaler un probleme](../../../.github/ISSUE_TEMPLATE/tool-update.md)*
