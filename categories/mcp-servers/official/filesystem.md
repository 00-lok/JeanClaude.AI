# Filesystem (MCP officiel)

> Serveur MCP officiel fournissant des operations fichier securisees avec controles d'acces configurables.

| Info | Detail |
|------|--------|
| **GitHub** | [modelcontextprotocol/servers — filesystem](https://github.com/modelcontextprotocol/servers/tree/main/src/filesystem) |
| **Site web** | [modelcontextprotocol.io](https://modelcontextprotocol.io/) |
| **Installation** | `npx -y @modelcontextprotocol/server-filesystem` |
| **Categorie** | Serveur MCP — Systeme de fichiers |
| **Licence** | MIT |
| **Statut** | Actif |
| **Derniere verification** | 2026-03-22 |

---

## Ce que ca fait

Le serveur Filesystem MCP donne a Claude un acces securise au systeme de fichiers local. Il permet de lire, ecrire, creer, deplacer et chercher des fichiers et repertoires, tout en appliquant des controles d'acces stricts. Seuls les repertoires explicitement autorises dans la configuration sont accessibles.

C'est le serveur MCP le plus fondamental — il permet a Claude d'interagir avec les fichiers de votre projet de maniere controlee et securisee.

---

## Fonctionnalites cles

- **Lecture/ecriture de fichiers** — Lire et ecrire des fichiers avec encodage configurable
- **Gestion de repertoires** — Creer, lister, deplacer des repertoires
- **Recherche de fichiers** — Chercher des fichiers par pattern glob
- **Controles d'acces** — Seuls les repertoires explicitement autorises sont accessibles
- **Metadonnees** — Obtenir la taille, date de modification, permissions des fichiers

---

## Installation

```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-filesystem",
        "/chemin/vers/repertoire/autorise"
      ]
    }
  }
}
```

### Prerequis

- Node.js v18+

---

## Utilisation avec Claude Code

Une fois configure, Claude Code peut automatiquement lire et manipuler des fichiers dans les repertoires autorises via le serveur MCP. Les outils disponibles incluent :

- `read_file` — Lire le contenu d'un fichier
- `write_file` — Ecrire du contenu dans un fichier
- `list_directory` — Lister le contenu d'un repertoire
- `create_directory` — Creer un nouveau repertoire
- `move_file` — Deplacer ou renommer un fichier
- `search_files` — Chercher des fichiers par pattern
- `get_file_info` — Obtenir les metadonnees d'un fichier

---

## Configuration

Vous pouvez autoriser plusieurs repertoires en les ajoutant comme arguments supplementaires :

```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-filesystem",
        "/chemin/projet1",
        "/chemin/projet2"
      ]
    }
  }
}
```

---

## Liens

- [Depot GitHub](https://github.com/modelcontextprotocol/servers/tree/main/src/filesystem)
- [Specification MCP](https://modelcontextprotocol.io/specification/2025-11-25)

---

*Derniere verification : 2026-03-22 · [Signaler un probleme](../../../.github/ISSUE_TEMPLATE/tool-update.md)*
