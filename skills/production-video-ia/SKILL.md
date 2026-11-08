---
name: production-video-ia
description: Choisir et utiliser les bons outils pour produire des vidéos - vidéo programmatique (Remotion, HTML), génération vidéo par IA (Veo, Kling, Runway…), avatars IA (HeyGen, Synthesia), outils de montage et de recyclage. Utiliser quand l'utilisateur veut produire une vidéo, une pub vidéo, une vidéo explicative animée, un avatar IA ou se demande quel outil vidéo utiliser.
---

# Production vidéo avec l'IA et le code

Aider à choisir la bonne méthode de production et à l'exécuter. Répondre en français.

## Avant de commencer

1. **But de la vidéo** : pub, explication, démo, contenu social, formation.
2. **Méthode envisagée** : filmée, animée, générée par IA, avatar.
3. **Contexte technique** : outils et abonnements disponibles, budget, délai.

## Choisir sa méthode

| Besoin | Méthode |
|---|---|
| Animations précises, graphiques, textes, données, déclinaisons en série | **Vidéo programmatique** (Remotion en React, ou HTML) — ici, aussi la skill video-making et Codesign |
| Plans réalistes impossibles à filmer, b-roll | **Génération vidéo IA** |
| Présentateur sans caméra, versions multilingues | **Avatar IA** |
| Vidéo existante à découper, sous-titrer, recadrer | **Montage / recyclage** (FFmpeg, `clips-courts`) |
| B-roll, voix off, musique, clips via YouTube | **vidIQ** si connecté |

## Génération vidéo IA (repères)

- Meilleure qualité avec son : Veo 3.
- Volume et coût : Kling, Seedance.
- Personnage constant sur plusieurs plans : Hailuo.
- Storyboard → vidéo : Runway, LTX Studio.
- Animer une image existante : Kling, Pika, Runway.
- Prompt : sujet + action + cadre + mouvement de caméra + lumière + style + durée ; un plan par prompt.

Ces outils demandent un compte (parfois payant) : les proposer comme options, sans les imposer. Les modèles évoluent vite, vérifier les offres actuelles.

## Avatars IA

HeyGen, Synthesia : utiles pour des formations multilingues ou des vidéos récurrentes ; moins efficaces que le vrai formateur pour la confiance. Ne jamais créer l'avatar ou la voix d'une personne sans son accord.

## Vidéo programmatique

Remotion (React → MP4) ou HTML animé : idéal pour des vidéos de marque, résultats de stratégie, explications animées, déclinaisons de pubs. Écrire les scènes en code, rendre, itérer.

## Recyclage

Vidéo longue → clips courts → sous-titres → formats 9:16 / 1:1 / 16:9 → miniatures. Voir `clips-courts` et `strategie-video`.

## Garde-fous

Respect des droits (musique, images, visages), pas de deepfake trompeur, mention « contenu généré par IA » quand la plateforme l'exige. En trading : pas de résultats fictifs présentés comme réels.

Détails : `references/` et `references/original-en.md`.

---
Adapté et traduit par Merex Academy à partir de « video » de Corey Haines (github.com/coreyhaines31/marketingskills), licence MIT.
