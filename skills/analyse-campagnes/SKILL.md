---
name: analyse-campagnes
description: Analyser les performances des campagnes à partir des chiffres de l'utilisateur - ROAS, CPA, CPL, CAC, ROI, CTR, attribution multi-canal et pertes dans le tunnel. Utiliser quand l'utilisateur demande quelle pub ou quel canal marche, où part son budget, s'il est rentable, ou partage un export de ses campagnes (Meta, Google, TikTok, tableur).
---

# Analyse de campagnes

Calculer et interpréter la rentabilité des campagnes à partir de données réelles. Répondre en français, avec des conclusions claires et actionnables. Aucune clé d'API : l'utilisateur fournit ses exports ou ses chiffres.

## Démarche en 3 étapes

1. **Attribution** : quels canaux génèrent les conversions ? Comparer 5 modèles avec `scripts/attribution_analyzer.py` :
   - Premier contact (notoriété), dernier contact (réponse directe), linéaire (multi-canal équilibré), décroissance temporelle (cycles courts), en U 40/20/40 (tunnel complet).
2. **Tunnel** : où les prospects décrochent-ils ? `scripts/funnel_analyzer.py` (étapes et volumes, ex. : vues → clics → inscrits → présents au webinaire → acheteurs).
3. **ROI** : `scripts/campaign_roi_calculator.py` calcule ROI, ROAS, CPA, CPL, CAC, CTR, taux de conversion, et compare aux repères (`references/campaign-metrics-benchmarks.md`).

Les scripts sont en Python, sans dépendance externe ; formats d'entrée dans `assets/sample_campaign_data.json`. Si les données sont trop incomplètes pour les scripts, faire les calculs directement et montrer les formules.

## Formules clés

- ROAS = chiffre d'affaires ÷ dépense pub
- CPA = dépense ÷ nombre d'acquisitions
- CPL = dépense ÷ nombre de prospects
- ROI = (revenu − coût total) ÷ coût total
- CTR = clics ÷ impressions ; taux de conversion = conversions ÷ clics
- ROAS de rentabilité = 1 ÷ marge (ex. : marge 50 % → ROAS minimum 2)

## Règles d'interprétation

- Toujours calculer, ne jamais estimer « à l'œil ».
- Comparer des périodes de même durée et tenir compte du délai de conversion.
- Signaler les échantillons trop petits (quelques conversions = bruit).
- Distinguer un problème de créa (CTR faible), de page (taux de conversion faible) ou d'offre (panier, prix).
- Guides : `references/attribution-models-guide.md`, `references/funnel-optimization-framework.md`.

## Livrable

Tableau des indicateurs par campagne/canal, ce qui marche, ce qui perd de l'argent, 3-5 actions prioritaires (couper, garder, scaler, tester). Pour un tableau de bord visuel, proposer un dashboard.

---
Adapté et traduit par Merex Academy à partir de « campaign-analytics » d'Alireza Rezvani (github.com/alirezarezvani/claude-skills), licence MIT.
