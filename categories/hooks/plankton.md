# Plankton

> Systeme d'enforcement de qualite au moment de l'ecriture — pipeline 3 phases (auto-format → lint 20+ outils → fix Claude) qui bloque l'agent tant que le code ne passe pas.

| Info | Detail |
|------|--------|
| **GitHub** | [alexfazio/plankton](https://github.com/alexfazio/plankton) |
| **Site web** | Non disponible |
| **Installation** | `git clone` + hooks auto-detectes |
| **Categorie** | Hooks / Qualite |
| **Licence** | MIT |
| **Statut** | Actif |
| **Derniere verification** | 2026-03-22 |

---

## Ce que ca fait

Plankton est un systeme qui rend impossible pour Claude de livrer du code sale. Il se declenche a **chaque ecriture de fichier** et execute un pipeline en 3 phases :

1. **Auto-format** — Des outils Rust ultra-rapides (Biome, ruff, shfmt, taplo) corrigent silencieusement 40-50% des problemes de style (indentation, espaces, imports)
2. **Collecte des violations** — 20+ linters analysent le code et produisent un rapport JSON structure des problemes restants
3. **Fix delegue a Claude** — Des instances Claude dediees reçoivent les violations en JSON et les corrigent intelligemment

Le point crucial : **l'agent est bloque tant que la sortie ne passe pas** les checks de style, types, securite et complexite. Claude ne peut litteralement pas passer a l'etape suivante avec du code qui ne respecte pas les standards.

---

## Fonctionnalites cles

- **Declenchement a chaque ecriture** — Pas besoin de lancer manuellement, chaque fichier modifie est analyse
- **20+ linters integres** — ESLint, Biome, ruff, mypy, shellcheck, hadolint, taplo, et plus
- **Auto-format Rust** — Biome/ruff sont 25x plus rapides que Prettier/ESLint, formatage en millisecondes
- **Fix intelligent** — Les violations restantes sont envoyees a Claude en JSON structure pour correction semantique
- **Blocage avant commit** — Le code ne peut pas etre commite tant qu'il ne passe pas tous les checks
- **Zero configuration** — Cloner et lancer Claude Code dans le repertoire — les hooks se chargent automatiquement

---

## Installation

```bash
# Cloner le depot
git clone https://github.com/alexfazio/plankton.git
cd plankton

# Lancer Claude Code depuis ce repertoire
# Les hooks dans .claude/hooks/ sont detectes automatiquement
claude
```

Pour integrer dans un projet existant, copiez les hooks :

```bash
cp -r plankton/.claude/hooks/ votre-projet/.claude/hooks/
```

### Prerequis

- Claude Code CLI
- Node.js (pour les linters JS/TS)
- Python (pour ruff/mypy si projet Python)

---

## Utilisation avec Claude Code

Plankton est **transparent** — il fonctionne en arriere-plan a chaque ecriture :

```bash
# Vous demandez a Claude de coder normalement
"Ajoute un endpoint POST /users avec validation"

# Claude ecrit le code
# → Plankton se declenche automatiquement :
#   Phase 1: Biome formate (40-50% de problemes corriges silencieusement)
#   Phase 2: 20+ linters analysent, produisent un rapport JSON
#   Phase 3: Si violations restantes → Claude les corrige
#   → Repete jusqu'a zero violations

# Le code commite est TOUJOURS propre
# Impossible de livrer du code avec des warnings ou erreurs de lint
```

---

## Configuration

Les linters actifs sont configurables dans les fichiers de hooks. Par defaut, Plankton active tous les linters pertinents pour votre stack (detectes automatiquement).

---

## Liens

- [Depot GitHub](https://github.com/alexfazio/plankton)

---

*Derniere verification : 2026-03-22 · [Signaler un probleme](../../.github/ISSUE_TEMPLATE/tool-update.md)*
