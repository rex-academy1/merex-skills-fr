---
name: journal-trading
description: Journal de trading structuré - enregistrer chaque trade avec son contexte, faire des bilans quotidiens/hebdo/mensuels, attribuer les résultats par setup et détecter les comportements qui détruisent l'avantage (revenge trading, FOMO, sorties prématurées). Utiliser quand l'utilisateur veut noter un trade, analyser son historique ou savoir quels setups gagnent vraiment.
---

# Journal de trading

Transformer le « ressenti » en données objectives. La plupart des traders échouent à cause de leur comportement, pas de leur stratégie : le journal le rend visible.

Répondre en français. Aucune clé d'API. Adapté au forex et aux indices synthétiques (l'original vise la crypto).

## Fiche de trade (champs minimum)

| Champ | Exemple |
|---|---|
| id | T-20261109-001 |
| actif | EURUSD / Volatility 75 |
| sens | achat / vente |
| date et heure d'entrée | 2026-11-09 09:15 (UTC+1) |
| prix d'entrée, stop, objectif | 1,0850 / 1,0830 / 1,0890 |
| lot | 0,12 |
| risque prévu ($ et %) | 25 $ / 0,5 % |
| setup (tag) | cassure-range, pullback-tendance, rebond-support… |
| raison écrite AVANT l'entrée | « Cassure du range asiatique H1, retest de 1,0848 » |
| qualité du setup (1-10) | 7 |
| sortie (date, prix), résultat ($ et R) | +50 $ / +2R |
| durée (≥ 2 min pour Bridge Markets) | 1 h 20 |
| plan respecté ? | oui / non + quoi |
| émotion à l'entrée / à la sortie | calme / pressé |
| leçon | une phrase |

Schéma complet de l'original : `references/record_format.md`.

## Modèles de « raison avant entrée »

- Tendance : « [Actif] casse [niveau] en [UT] avec [confirmation]. Objectif [prix], stop [prix]. »
- Retour à la moyenne : « [Actif] à [X] du [repère] en [UT], retour attendu vers [objectif]. »

## Stockage

Tenir le journal dans un fichier (CSV ou tableur) ou dans la conversation. Si l'utilisateur le souhaite, proposer un tableau qu'il garde et complète. Les scripts `scripts/trade_logger.py` et `scripts/journal_analyzer.py` (Python, locaux) permettent d'enregistrer et d'analyser un journal JSON.

## Bilans

- **Quotidien** : P&L, nombre de trades, respect du plan, marge restante avant les limites prop firm.
- **Hebdomadaire** : taux de réussite, gain moyen / perte moyenne, espérance (en R), meilleur et pire setup, journées en violation.
- **Mensuel** : attribution par setup, par session (Asie/Londres/New York), par jour de la semaine, par actif ; évolution des comportements.

## Détection des comportements

Signaler avec preuves : revenge trade (nouvelle entrée rapide après une perte, lot plus gros), FOMO (entrée sans setup, après un gros mouvement), sorties prématurées (gains coupés bien avant l'objectif alors que les pertes vont au stop), sur-trading (trop de trades un même jour), changements de lot brutaux. Pour une revue approfondie, enchaîner avec `coach-performance-trading`.

Rappel : outil de suivi, pas un conseil en investissement.

---
Adapté et traduit par Merex Academy à partir de « trade-journal » d'AGIPro Labs (github.com/agiprolabs/claude-trading-skills), licence MIT.
