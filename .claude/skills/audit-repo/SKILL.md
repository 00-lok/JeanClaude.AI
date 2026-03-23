---
name: audit-repo
description: "Auditer la qualite de toutes les fiches outils du repo : sections manquantes, liens casses, coherence, infos obsoletes"
---

# Skill : Auditer le repo

## Declencheur
Quand l'utilisateur demande un audit, une verification de qualite, ou utilise `/audit-repo`.

## Processus

### 1. Audit structurel

Pour CHAQUE fichier `.md` dans `categories/` (hors README.md) :
- Verifier que le fichier suit le format de `templates/tool-template.md`
- Verifier la presence de TOUTES les sections obligatoires :
  - Tableau d'en-tete (GitHub, Installation, Categorie, Statut, Derniere verification)
  - "Ce que ca fait" (2-3 paragraphes)
  - "Fonctionnalites cles" (au moins 3 items)
  - "Installation" (commande concrete, pas "voir GitHub")
  - "Utilisation avec Claude Code" (exemples concrets)
  - "Liens"
  - Date de derniere verification
- Signaler les sections vides ou trop courtes (< 2 lignes)

### 2. Audit des liens internes

Pour CHAQUE lien interne `[texte](chemin.md)` :
- Verifier que le fichier cible existe
- Verifier que les README de categories referent bien tous les fichiers de leur repertoire
- Verifier que le README racine est coherent avec les categories

### 3. Audit de coherence

- Les noms de fichiers sont en kebab-case
- Les dates utilisent le format AAAA-MM-JJ
- Les stars utilisent le prefixe ~
- Pas de texte en anglais dans le contenu (hors noms propres/commandes)
- Pas de sections placeholder avec du texte generique

### 4. Audit de fraicheur

- Lister les fiches dont la "Derniere verification" date de plus de 30 jours
- Lister les fiches dont le statut devrait etre verifie (repos potentiellement archives)

### 5. Rapport

Produire un rapport structure :

```
## Rapport d'audit — {date}

### Problemes critiques (a corriger maintenant)
- [ ] {fichier} : {probleme}

### Avertissements (a corriger bientot)
- [ ] {fichier} : {probleme}

### Fiches a re-verifier (potentiellement obsoletes)
- [ ] {fichier} : derniere verification {date}

### Stats
- Total fiches : {N}
- Fiches conformes : {N}
- Fiches avec problemes : {N}
- Score qualite : {pourcentage}%
```
