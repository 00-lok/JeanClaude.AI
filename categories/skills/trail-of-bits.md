# Trail of Bits Security Skills

> 100+ skills de securite crees par Trail of Bits, une des firmes d'audit de securite les plus reconnues au monde. Couvre l'audit de code, l'analyse de smart contracts, le reverse engineering et la detection de vulnerabilites.

| Info | Detail |
|------|--------|
| **GitHub** | [trailofbits/skills](https://github.com/trailofbits/skills) |
| **Site web** | [trailofbits.com](https://www.trailofbits.com/) |
| **Installation** | `/plugin install trailofbits/skills` |
| **Categorie** | Skills / Securite |
| **Licence** | MIT |
| **Statut** | Actif |
| **Stars** | ~3.8k |
| **Derniere verification** | 2026-03-22 |

---

## Ce que ca fait

Trail of Bits est la firme qui audite la securite de projets comme Ethereum, Kubernetes et le noyau Linux. Ces skills encodent **l'expertise reelle de leurs auditeurs** en instructions que Claude peut suivre : checklists d'analyse, patterns de vulnerabilites connus, et la logique de decision qu'un auditeur experimente appliquerait.

Concretement, au lieu de demander a Claude "verifie la securite de ce code" (reponse vague), ces skills lui donnent les memes procedures qu'un auditeur senior de Trail of Bits utiliserait : analyse des flux de donnees, detection de reentrancy, verification d'autorisation, analyse de dependances, etc.

Le depot companion [trailofbits/claude-code-config](https://github.com/trailofbits/claude-code-config) fournit la configuration Claude Code complete de Trail of Bits — sandbox, permissions, hooks et pre-commit.

---

## Fonctionnalites cles

- **Audit de securite code** — Procedures completes d'audit avec checklists de vulnerabilites
- **Analyse de smart contracts** — Detection de reentrancy, manipulation d'oracle, front-running
- **Reverse engineering** — Analyse de binaires, decompilation, analyse de protocoles
- **Detection de vulnerabilites** — Injection SQL, XSS, CSRF, path traversal, deserialization
- **Analyse statique** — Integration CodeQL et Semgrep avec rules personnalisees
- **Personas d'agents** — Skills configures comme "auditeur senior ayant trie des centaines de bugs de reentrancy"
- **Verification de fix** — Valide que les corrections de vulnerabilites sont effectives

---

## Installation

```bash
# Via le systeme de plugins
/plugin install trailofbits/skills

# Pour la configuration securisee complete de Trail of Bits
git clone https://github.com/trailofbits/claude-code-config.git
# Adapter les configurations a votre projet
```

### Prerequis

- Claude Code CLI
- (Optionnel) Semgrep et CodeQL pour l'analyse statique

---

## Utilisation avec Claude Code

```bash
# Audit de securite complet d'un module
"Fais un audit de securite du module src/auth/ en utilisant les skills Trail of Bits"

# Claude va suivre la procedure d'audit :
# 1. Cartographier les surfaces d'attaque
# 2. Analyser les flux de donnees (input → traitement → output)
# 3. Verifier chaque pattern de vulnerabilite connu
# 4. Produire un rapport avec severite, preuve, et recommendation

# Analyse de smart contract
"Audite ce contrat Solidity pour les vulnerabilites de reentrancy"

# Revue de securite d'une PR
"Revois cette PR du point de vue securite avec les checklists Trail of Bits"
```

---

## Projets lies

| Depot | Description |
|-------|-------------|
| [trailofbits/claude-code-config](https://github.com/trailofbits/claude-code-config) | Configuration Claude Code complete de Trail of Bits (sandbox, hooks, permissions) |

---

## Liens

- [Depot GitHub](https://github.com/trailofbits/skills)
- [Trail of Bits](https://www.trailofbits.com/)

---

*Derniere verification : 2026-03-22 · [Signaler un probleme](../../.github/ISSUE_TEMPLATE/tool-update.md)*
