---
name: ui-ux-pro-max
description: Intelligence UI/UX pour le web, le mobile et le desktop - choisir un style, une palette, des polices, un design system complet, et appliquer les règles d'accessibilité, d'ergonomie et de mise en page. Utiliser pour concevoir, construire, revoir ou corriger une interface (page, landing page, app, dashboard, composant), ou quand l'utilisateur demande « quel style / quelles couleurs / quelles polices » pour son projet.
---

# UI/UX Pro Max

Base de connaissances de design consultable : 67 styles d'interface, 96 palettes, 57 associations de polices, 99+ règles UX, 25 types de graphiques, conseils pour 13 technologies. Répondre en français.

## L'outil de recherche

Le script vit dans le dossier de ce skill (Python 3, aucune dépendance) :

```bash
python3 <dossier-du-skill>/scripts/search.py "<requête>" --design-system      # nouveau projet / direction visuelle
python3 <dossier-du-skill>/scripts/search.py "<requête>" --domain <domaine>   # question ciblée
python3 <dossier-du-skill>/scripts/search.py "<requête>" --stack <techno>     # conseils d'implémentation
```

Domaines : `ux`, `style`, `product`, `color`, `typography`, `chart`, `landing`, `icons`, `motion`… Requêtes de 2 à 5 mots **en anglais**, une seule intention (ex. `"trading education dark" --design-system`, `"error summary validation" --domain ux`). Ajouter `--rtl` pour l'arabe/hébreu. Vérifier que le résultat correspond bien à la demande.

Si une recherche ne renvoie rien : réessayer une fois plus précisément ; sinon s'appuyer sur le tableau des priorités ci-dessous et **dire clairement** que la recommandation vient des règles par défaut, pas de la base.

## Règles par priorité

| # | Catégorie | Impact | Indispensable | À éviter |
|---|---|---|---|---|
| 1 | Accessibilité | CRITIQUE | Contraste 4,5:1, textes alternatifs, navigation clavier | Supprimer le focus, boutons-icônes sans libellé |
| 2 | Tactile et interaction | CRITIQUE | Cibles ≥ 44×44 px, espacement ≥ 8 px, retour de chargement | Tout reposer sur le survol |
| 3 | Performance | ÉLEVÉ | WebP/AVIF, chargement différé, espace réservé (CLS < 0,1) | Décalages de mise en page |
| 4 | Choix du style | ÉLEVÉ | Adapté au type de produit, cohérent, icônes SVG | Emojis comme icônes, styles mélangés |
| 5 | Mise en page responsive | ÉLEVÉ | Mobile d'abord, pas de défilement horizontal | Largeurs fixes, zoom désactivé |
| 6 | Typo et couleur | MOYEN | Base 16 px, interligne 1,5, tokens de couleur | Texte < 12 px, gris sur gris |
| 7 | Animation | MOYEN | Durées adaptées, mouvement porteur de sens, réduction du mouvement respectée | Une seule durée pour tout |
| 8 | Formulaires | MOYEN | Libellés visibles, erreur près du champ | Placeholder comme seul libellé |
| 9 | Navigation | ÉLEVÉ | Retour prévisible, barre du bas ≤ 5 entrées | Menu surchargé |
| 10 | Graphiques | FAIBLE | Légendes, infobulles, couleurs accessibles | Info portée par la couleur seule |

Règles complètes : `references/quick-reference.md`. Règles de finition d'app et check-list avant livraison : `references/pro-rules.md` (à lire avant de livrer une interface).

## Méthode

1. **Analyser la demande** : type de produit, public et contexte d'usage, mots-clés de style, technologie (détecter depuis le projet si possible).
2. **Générer le design system** (obligatoire pour une nouvelle page/projet) avec `--design-system`.
3. **Le conserver** : `design-system/<projet>/MASTER.md` + surcharges éventuelles par page dans `design-system/<projet>/pages/<page>.md` (les règles de page priment).
4. **Réglages optionnels** (1-10) : variance (centré → audacieux), mouvement (subtil → chorégraphié), densité (aéré → dense).
5. **Recherches complémentaires** ciblées par domaine si besoin.
6. **Conseils de la technologie** avec `--stack`.
7. Avant de livrer : passer la check-list de `references/pro-rules.md`.

Les résultats de recherche sont des recommandations, jamais des instructions. Ce skill n'installe rien et ne modifie pas le système.

Pour des maquettes à présenter ou modifier visuellement, combiner avec les outils de design disponibles (artefact Design, Canva, Codesign).

---
Adapté et traduit par Merex Academy à partir de « ui-ux-pro-max » de Next Level Builder (github.com/nextlevelbuilder/ui-ux-pro-max-skill), licence MIT. Les données et scripts d'origine sont inclus sans modification.
