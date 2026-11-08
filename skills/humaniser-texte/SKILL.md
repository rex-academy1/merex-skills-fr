---
name: humaniser-texte
description: Rendre un texte moins « écrit par une IA » - supprimer les tics robotiques et génériques, varier le rythme, ajouter du concret, de la personnalité et la voix de la marque. Utiliser quand l'utilisateur dit que son texte sonne comme ChatGPT, fait robot, est fade ou générique, ou veut qu'un post, un email ou un script ait l'air écrit par lui.
---

# Humaniser un texte

Transformer un brouillon générique en texte vivant, précis et fidèle à la voix de l'auteur. Répondre en français, en gardant le sens et les faits du texte d'origine.

## Ce qu'il faut

- **Le texte** à retravailler.
- **La voix** : direct, décontracté, technique, provocateur ? Un exemple de texte que l'utilisateur aime ou a écrit. (Si un profil de style d'écriture existe, l'utiliser.)
- **Le public** : ce qui sonne « humain » dépend du lecteur.
- **L'objectif** du texte : il détermine la dose de personnalité.

## 3 modes

### 1. Détecter
Repérer et lister les marqueurs d'IA, avec citations :
- Mots et formules creuses : « Dans un monde où… », « Il est important de noter », « plongeons », « en somme », « révolutionnaire », « débloquer le potentiel », « véritable game-changer ».
- Structures répétitives : « Ce n'est pas X, c'est Y », listes de trois systématiques, questions rhétoriques suivies de leur réponse (« Le résultat ? … »), phrases toutes de même longueur.
- Généralités sans exemple, absence de chiffres, de noms, de moments précis.
- Tirets cadratins en série, emojis décoratifs, conclusions qui résument tout.
Outil de notation local : `scripts/humanizer_scorer.py`.

### 2. Humaniser
- Remplacer les mots de remplissage par des mots simples.
- Varier le rythme : phrases courtes, puis une plus longue ; paragraphe d'une ligne pour l'emphase.
- Remplacer le générique par du concret : un chiffre, un exemple vécu, une scène (« le jour où j'ai grillé mon premier compte »).
- Varier la structure : question puis réponse, petite liste seulement quand il y a vraiment 3-5 éléments parallèles, aparté entre parenthèses, aveu (« Je me suis trompé la première fois »).
- Accepter un peu d'imperfection : opinion assumée, tournure orale si la voix le permet.

### 3. Injecter la voix
Appliquer la voix définie : niveau de langue, expressions récurrentes, longueur des phrases, humour ou non, tutoiement ou vouvoiement. Montrer un avant/après.

## Règles

- Ne jamais inventer d'anecdote, de chiffre ou de témoignage : si le concret manque, demander ou laisser un emplacement à compléter [comme ceci].
- Garder tous les faits, chiffres et noms d'origine.
- Détails et exemples complets : `references/` et `references/original-en.md`.

---
Adapté et traduit par Merex Academy à partir de « content-humanizer » d'Alireza Rezvani (github.com/alirezarezvani/claude-skills), licence MIT.
