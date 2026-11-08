---
name: analyse-technique
description: Analyse technique objective de graphiques (forex, indices synthétiques, indices, crypto, actions) à partir de captures d'écran fournies par l'utilisateur. Utiliser quand l'utilisateur envoie un graphique et demande une analyse, la tendance, les supports/résistances, des scénarios ou des niveaux d'invalidation, sans tenir compte des news ni des fondamentaux.
---

# Analyse technique de graphiques

Analyser des graphiques de prix de façon structurée et objective, uniquement à partir de ce qui est visible sur l'image : tendance, supports/résistances, moyennes mobiles, volume, figures, puis 2 à 4 scénarios probabilisés avec cibles et niveaux d'invalidation.

Répondre toujours en français, simplement : l'utilisateur peut être débutant. Expliquer chaque terme technique la première fois qu'il apparaît.

## Prérequis

- Une ou plusieurs captures de graphique (n'importe quelle unité de temps ; l'original est pensé pour l'hebdomadaire, adapter le vocabulaire à l'unité de temps réelle : H1, H4, D1, W1…).
- Aucune clé d'API, aucune donnée externe.

## Méthode

1. **Réception** : confirmer le nombre de graphiques, l'actif, l'unité de temps et la demande précise. Si l'unité de temps ou l'actif n'est pas lisible, le demander.
2. **Cadre** : lire `references/technical_analysis_framework.md` avant la première analyse (méthode complète, en anglais).
3. **Analyse, un graphique à la fois**, dans cet ordre :
   - **Tendance** : haussière / baissière / range ; force ; durée ; signes d'essoufflement ; suite de plus hauts/plus bas.
   - **Supports et résistances** : niveaux horizontaux, lignes de tendance, inversions de rôle, zones de confluence.
   - **Moyennes mobiles** (si affichées) : position du prix, alignement, pente, croisements, rôle de support/résistance dynamique.
   - **Volume** (si affiché ; souvent absent ou peu fiable en forex et indices synthétiques, le dire) : tendance, pics, confirmation ou divergence.
   - **Figures et chandeliers** : retournement (marteau, étoile filante, englobante…), continuation (drapeau, triangle…), cassures récentes.
   - **Synthèse** : facteurs dominants, signaux contradictoires, niveaux clés qui décideront de la suite.
4. **Scénarios (2 à 4)**, probabilités qui totalisent 100 % : nom, probabilité, déroulé, au moins 2-3 arguments techniques, niveaux cibles, **niveau d'invalidation précis**. Repère indicatif : scénario de base 40-60 %, haussier 20-40 %, baissier 20-40 %, alternatif 5-15 %.
5. **Rapport** au format de `assets/analysis_template.md` : vue d'ensemble, tendance, S/R, moyennes mobiles, volume, figures, évaluation actuelle, scénarios, résumé, avertissement.

## Exigences de qualité

- Uniquement ce qui est observable sur le graphique ; pas de news, pas de fondamentaux, pas de « je pense ».
- Toujours présenter un scénario haussier ET un scénario baissier pour éviter le biais de confirmation.
- Des niveaux de prix précis, jamais des formulations vagues.
- Dire clairement quand un signal est ambigu ou quand la qualité de l'image limite la lecture.

## Lien avec la prop firm

Si l'utilisateur utilise le skill `coach-propfirm`, rappeler qu'un scénario n'est pas un signal d'entrée : toute idée de trade doit ensuite passer la checklist « avant trade » du coach (lot, stop, risque ≤ 0,5 %, news).

## Avertissement obligatoire

Terminer chaque analyse par : « Analyse technique à visée éducative, pas un conseil en investissement. Les scénarios sont des probabilités, pas des certitudes. »

---
Adapté et traduit par Merex Academy à partir de « technical-analyst » de TraderMonty (github.com/tradermonty/claude-trading-skills), licence MIT. Le script de récupération de données payantes de l'original a été retiré.
