# Spec Kit

> Toolkit open-source de GitHub pour le developpement spec-driven — definissez principes, exigences et plan, puis les agents IA implementent contre cette spec comme source de reference unique.

| Info | Detail |
|------|--------|
| **GitHub** | [github/spec-kit](https://github.com/github/spec-kit) |
| **Site web** | Non disponible |
| **Installation** | `bun install -g @spec-kit/cli` |
| **Categorie** | Framework |
| **Licence** | MIT |
| **Statut** | Actif (v0.3.2, mars 2026) |
| **Derniere verification** | 2026-03-22 |

---

## Ce que ca fait

Spec Kit est un toolkit cree par **GitHub** (pas un projet communautaire — c'est un produit officiel GitHub) qui structure le developpement IA autour de **specifications formelles comme reference unique**. Le probleme qu'il resout : quand vous donnez des instructions ad hoc a une IA, il n'y a pas de source de verite partagee. Le resultat varie d'une session a l'autre, les exigences se perdent, et le projet derive.

Avec Spec Kit, vous construisez un cadre formel en 5 etapes :
1. **Principes** — Les regles immuables du projet (techno, style, contraintes)
2. **Exigences** — Ce que le logiciel doit faire (fonctionnel et non-fonctionnel)
3. **Plan** — La strategie d'implementation (architecture, composants, ordre)
4. **Taches** — Les unites de travail atomiques derivees du plan
5. **Implementation** — L'agent IA implemente contre la spec, pas contre un prompt vague

La spec est stockee dans le projet et versionnee avec Git, donc chaque session IA lit la meme reference.

---

## Fonctionnalites cles

- **CLI `specify`** — Scaffolding de specs avec commandes interactives
- **Multi-agents** — Compatible Claude Code, GitHub Copilot, Gemini CLI
- **Spec versionnee** — Stockee dans le projet, commitee avec Git, toujours a jour
- **Produit officiel GitHub** — Maintenu par GitHub, pas un projet communautaire
- **Structure en 5 etapes** — Principes → Exigences → Plan → Taches → Implementation

---

## Installation

```bash
# Via Bun (recommande)
bun install -g @spec-kit/cli
bunx @spec-kit/cli init mon-projet

# Via npm
npx @spec-kit/cli init mon-projet

# Via Python/UV
uvx --from git+https://github.com/github/spec-kit.git specify init mon-projet
```

### Prerequis

- Bun, npm ou Python avec UV
- Un agent IA compatible (Claude Code, Copilot, Gemini CLI)

---

## Utilisation avec Claude Code

```bash
# 1. Initialiser les specs dans votre projet
bunx @spec-kit/cli init mon-projet
cd mon-projet

# 2. Cela cree la structure suivante :
# specs/
# ├── principles.md    # Regles du projet
# ├── requirements.md  # Exigences fonctionnelles
# ├── plan.md          # Plan d'implementation
# └── tasks/           # Taches atomiques
#     ├── 001-setup.md
#     └── 002-auth.md

# 3. Remplissez les specs (manuellement ou avec Claude)
# Claude Code lit automatiquement les fichiers specs/ comme contexte

# 4. Demandez a Claude d'implementer contre la spec
# "Implemente la tache 001-setup.md en respectant les principes definis"

# 5. Chaque session Claude voit la meme reference — pas de derive
```

### Quand utiliser Spec Kit vs BMAD vs GSD

| Critere | Spec Kit | BMAD | GSD |
|---------|----------|------|-----|
| Focus | Specs comme reference | Equipe agile complete | Gestion du contexte |
| Complexite | Legere | Lourde | Moyenne |
| Agents | 0 (vous, + l'IA) | 12+ agents specialises | Multi-agents |
| Ideal pour | Projets avec specs claires | Projets enterprise | Projets longs |
| Peut se combiner avec | BMAD ou GSD | Spec Kit, Vibe Kanban | Spec Kit, CCPM |

---

## Configuration

Les specs sont de simples fichiers Markdown dans le repertoire `specs/` de votre projet. Pas de configuration speciale — Claude Code les lit automatiquement comme contexte projet.

Ajoutez les fichiers specs a votre `CLAUDE.md` pour que Claude les priorise :

```markdown
# CLAUDE.md
## Contexte projet
- Lire specs/principles.md avant toute modification
- Les exigences de specs/requirements.md priment sur les suggestions
```

---

## Liens

- [Depot GitHub](https://github.com/github/spec-kit)
- [Article de blog GitHub](https://github.blog/ai-and-ml/generative-ai/spec-driven-development-with-ai-get-started-with-a-new-open-source-toolkit/)

---

*Derniere verification : 2026-03-22 · [Signaler un probleme](../../.github/ISSUE_TEMPLATE/tool-update.md)*
