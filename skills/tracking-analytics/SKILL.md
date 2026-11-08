---
name: tracking-analytics
description: Mettre en place, améliorer ou auditer le suivi et la mesure - Google Analytics 4, Google Tag Manager, pixel Meta, événements de conversion, paramètres UTM, plan de marquage. Utiliser quand l'utilisateur veut suivre ses ventes et inscriptions, installer un pixel, comprendre d'où viennent ses clients, ou quand ses chiffres de pub ne collent pas avec la réalité.
---

# Suivi et analytics

Mesurer ce qui sert à décider, pas tout ce qui est mesurable. Répondre en français, expliquer simplement (l'utilisateur peut ne pas être technique) et donner des étapes cliquables.

## Diagnostic

1. **Business** : quelles décisions ces données doivent-elles éclairer ? Quelles sont les conversions clés (achat, inscription, prise de RDV, entrée dans la communauté) ?
2. **Existant** : quels outils (GA4, GTM, pixel Meta, TikTok, plateforme de vente : Systeme.io, Chariow, Selar, Gumroad, Shopify…) et qu'est-ce qui est déjà suivi ?
3. **Technique** : site (WordPress, Systeme.io, autre), contraintes de confidentialité (consentement cookies, RGPD pour les visiteurs européens).

## Principes

1. Suivre pour décider.
2. Partir des questions business, puis définir les événements.
3. Nommer de façon cohérente : format **objet_action** en minuscules (`formulaire_envoye`, `achat_termine`).
4. Garder des données propres (filtrer les tests, éviter les doublons).
5. Calculer, ne pas estimer.
6. Comparer des fenêtres d'observation identiques.
7. Oser recommander contre l'objectif annoncé si les données le justifient.

## Plan de marquage minimum

| Événement | Propriétés |
|---|---|
| cta_clique | texte_bouton, emplacement |
| formulaire_envoye | type_formulaire |
| inscription_terminee | methode, source |
| inscription_webinaire | nom_webinaire |
| achat_termine | produit, valeur, devise |
| paiement_abandonne | produit, etape |

Liste complète : `references/event-library.md`.

## UTM

Toujours taguer les liens de pub, d'email, de bio et de WhatsApp : `utm_source` (facebook, youtube, whatsapp), `utm_medium` (paid, social, email), `utm_campaign` (nom-campagne), `utm_content` (créa). Garder un tableau des conventions.

## Mise en œuvre

- GA4 : `references/ga4-implementation.md`.
- Google Tag Manager : `references/gtm-implementation.md`.
- Pixel Meta / API Conversions et TikTok : suivre la documentation officielle de chaque plateforme ; vérifier avec leurs outils de test (Meta Events Manager, Tag Assistant).

## Livrable

Plan de marquage (événements, propriétés, déclencheurs), convention UTM, check-list d'installation pas à pas, check-list de vérification, et liste des écarts trouvés en cas d'audit.

---
Adapté et traduit par Merex Academy à partir de « analytics » de Corey Haines (github.com/coreyhaines31/marketingskills), licence MIT.
