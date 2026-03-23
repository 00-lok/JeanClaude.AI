# Contribuer a Claude AI Tools

Merci de nous aider a faire de ce depot la meilleure ressource pour la communaute Claude AI.

## Comment contribuer

### Ajouter un nouvel outil

1. **Forkez** ce depot
2. **Copiez** le template depuis [`templates/tool-template.md`](templates/tool-template.md)
3. **Remplissez** chaque champ — aucune section vide
4. **Placez** le fichier dans le bon repertoire `categories/{categorie}/`
5. **Mettez a jour** le `README.md` index de la categorie pour inclure votre outil
6. **Mettez a jour** le `README.md` principal si l'outil est suffisamment important pour le tableau principal
7. **Soumettez** une Pull Request

### Mettre a jour un outil existant

Si vous remarquez des informations obsoletes (liens casses, commandes incorrectes, fonctionnalites depreciees) :

1. Ouvrez le fichier `.md` de l'outil
2. Effectuez la correction
3. Mettez a jour la date `Derniere verification` a aujourd'hui
4. Soumettez une PR avec une description claire de ce qui a change et pourquoi

### Signaler un probleme

Utilisez les [templates d'issues](.github/ISSUE_TEMPLATE/) pour :
- **Suggerer un nouvel outil** — Utilisez le template "Nouvel outil"
- **Signaler une info obsolete** — Utilisez le template "Mise a jour"

---

## Standards de qualite

Chaque entree d'outil **doit** respecter ces criteres :

### Informations requises

- [ ] Nom de l'outil et description en une ligne
- [ ] Lien GitHub fonctionnel (verifie)
- [ ] Commande d'installation exacte (testee)
- [ ] Categorie assignee
- [ ] Statut de maintenance actuel (Actif / Archive / Beta)
- [ ] Section "Ce que ca fait" avec 2-3 paragraphes clairs
- [ ] Au moins 3 fonctionnalites cles avec descriptions
- [ ] Instructions d'installation avec prerequis
- [ ] Section "Utilisation avec Claude Code" avec des exemples concrets
- [ ] Date de verification

### Directives de redaction

- **Soyez factuel** — Pas de langage marketing, pas de superlatifs sans preuve
- **Soyez precis** — "Supporte 12 agents" est mieux que "supporte beaucoup d'agents"
- **Soyez a jour** — Verifiez que tous les liens et commandes fonctionnent avant de soumettre
- **Soyez concis** — Dites ce qui doit etre dit, rien de plus
- **Utilisez le template** — Ne deviez pas du format standardise

### Ce que nous n'acceptons pas

- Outils sans depot public ni documentation
- Outils exclusivement payants sans version gratuite ou composant open-source
- Doublons pour le meme outil
- Entrees avec des informations non verifiees ou provisoires
- Contenu marketing ou d'affiliation

---

## Conventions de nommage

- Utilisez le **kebab-case** pour tous les noms de fichiers : `bmad-method.md`, pas `BMAD_Method.md`
- Utilisez le nom courant de l'outil : `claude-squad.md`, pas `smtg-ai-claude-squad.md`
- Les fichiers README de categorie sont toujours `README.md`

## Structure des repertoires

```
categories/
└── {categorie}/
    ├── README.md          # Index de la categorie avec tableau de tous les outils
    └── {nom-outil}.md     # Documentation individuelle de l'outil
```

---

## Processus de Pull Request

1. Assurez-vous que vos modifications respectent les standards de qualite ci-dessus
2. Remplissez le template de PR completement
3. Un outil par PR (sauf mise a jour groupee des dates de verification)
4. Un mainteneur effectuera la revue sous 48 heures

---

## Code de conduite

- Soyez respectueux et constructif
- Concentrez-vous sur les faits et l'utilite
- Creditez les auteurs et mainteneurs originaux
- Pas d'auto-promotion sans transparence

Merci de contribuer.
