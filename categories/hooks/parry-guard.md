# Parry-Guard

> Scanner d'injection de prompts en Rust — detection multi-etapes avec DeBERTa ML + tree-sitter AST. Scan en ~8ms.

| Info | Detail |
|------|--------|
| **GitHub** | [vaporif/parry-guard](https://github.com/vaporif/parry-guard) |
| **Installation** | `cargo install parry-guard` |
| **Categorie** | Hooks / Securite |
| **Statut** | Actif |
| **Derniere verification** | 2026-03-22 |

---

## Ce que ca fait

Parry-Guard protege Claude Code contre les attaques par injection de prompts dans les fichiers clones, les pages web fetchees, et les sorties de commandes. Il utilise une detection multi-etapes :

1. **Analyse Unicode** — Detecte les caracteres invisibles et homoglyphes
2. **Aho-Corasick** — Matching rapide de sous-chaines suspectes
3. **40+ regex** — Detection de credentials et patterns d'exfiltration
4. **ML DeBERTa v3** — Classification par transformers pour les injections sophistiquees
5. **tree-sitter AST** — Analyse syntaxique des scripts bash pour detecter l'exfiltration de donnees

Le tout en **~8ms** (cache) grace a l'implementation Rust.

---

## Fonctionnalites cles

- **Multi-etapes** — 5 niveaux de detection, du pattern matching au ML
- **Ultra-rapide** — ~8ms en cache, ne ralentit pas le workflow
- **Rust natif** — Performance maximale, pas d'interpreteur
- **Detection credentials** — 40+ patterns pour cles API, tokens, mots de passe
- **AST analysis** — Comprend la structure des scripts, pas juste le texte

---

## Installation

```bash
cargo install parry-guard
```

Configuration hook dans `.claude/settings.json` :

```json
{
  "hooks": {
    "PreToolUse": [
      {
        "type": "command",
        "command": "parry-guard scan --stdin",
        "description": "Scanner les injections de prompts"
      }
    ]
  }
}
```

---

## Liens

- [Depot GitHub](https://github.com/vaporif/parry-guard)

---

*Derniere verification : 2026-03-22 · [Signaler un probleme](../../.github/ISSUE_TEMPLATE/tool-update.md)*
