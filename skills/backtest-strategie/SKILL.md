---
name: backtest-strategie
description: Méthode professionnelle pour tester (backtester), stresser et valider une stratégie de trading avant de l'utiliser en réel ou sur un challenge prop firm. Utiliser quand l'utilisateur veut savoir si une stratégie est robuste, interpréter des résultats de backtest, éviter la sur-optimisation ou fixer des attentes réalistes de frais et slippage.
---

# Backtest et validation de stratégie

Objectif : trouver la stratégie qui **casse le moins**, pas celle qui gagne le plus sur le papier. Principe : ajouter de la friction, stresser chaque hypothèse, et garder ce qui survit.

Répondre en français, simplement. Aucune clé d'API : les données et métriques viennent de l'utilisateur (export MT5, TradingView, tableur…).

## Démarche

1. **Hypothèse en une phrase.** Exemple : « Sur EURUSD H1, un retour sur la zone cassée après une cassure de range de session asiatique offre un rebond exploitable. » Si l'avantage (l'« edge ») ne tient pas en une phrase, ne pas tester.
2. **Règles sans aucune discrétion** : entrée (conditions, moment, type d'ordre), sortie (stop, objectif, sortie au temps), taille de position, filtres (session, volatilité, news), actifs autorisés. Chaque décision doit être mécanique.
3. **Premier test** : idéalement 5 ans ou plus, plusieurs régimes de marché (tendance, range, forte/faible volatilité), frais et slippage réalistes (spread, commissions).
4. **Stress test (80 % du temps)** :
   - Sensibilité des paramètres : stop à 50/75/100/125/150 % de la valeur de base, objectif à 80-120 %. Chercher des **plateaux** stables, pas des pics étroits.
   - Friction : slippage ×1,5 à ×2, pires remplissages, spreads élargis aux news et à l'ouverture.
   - Robustesse dans le temps : résultat année par année ; espérance positive la plupart des années ; pas de dépendance à 1-2 périodes exceptionnelles.
   - Échantillon : minimum absolu 30 trades, 100+ préférable, 200+ pour une vraie confiance.
5. **Validation hors échantillon** : réserver une période jamais vue (ou faire du walk-forward) ; la performance ne doit pas s'effondrer.
6. **Évaluation** : le script `scripts/evaluate_backtest.py` (Python, sans clé) note un backtest à partir de métriques fournies. Le lancer si l'utilisateur donne ses chiffres ; sinon faire l'analyse manuellement.

## Pièges à signaler systématiquement

Sur-optimisation (curve fitting), biais d'anticipation (utiliser une info future), biais de survie, échantillon trop petit, frais ignorés, résultats portés par un seul trade géant.

## Lien avec la prop firm

Traduire les résultats en règles de challenge : drawdown maximal historique vs limite de la prop firm, pire série de pertes vs stop journalier, part de la meilleure journée dans le profit total (règle de constance des 30 % sur Bridge Markets). Une stratégie dont le drawdown historique dépasse la moitié de la limite de perte du compte est trop risquée pour un challenge.

Pour les détails (méthodologie complète, biais, modélisation du slippage), lire `references/` et `references/original-en.md`.

Rappeler : un bon backtest ne garantit pas les résultats futurs. Pas un conseil en investissement.

---
Adapté et traduit par Merex Academy à partir de « backtest-expert » de TraderMonty (github.com/tradermonty/claude-trading-skills), licence MIT.
