---
name: clips-courts
description: Découper ses propres vidéos longues (YouTube, live, webinaire, formation) en clips courts verticaux pour Shorts, Reels et TikTok - repérer les meilleurs passages grâce aux sous-titres, couper avec FFmpeg, recadrer en 9:16 et incruster les sous-titres. Utiliser quand l'utilisateur veut transformer une vidéo longue en extraits, faire des Shorts ou Reels à partir d'un live, ou sous-titrer un clip.
---

# Clips courts à partir de vidéos longues

Transformer une vidéo longue **dont l'utilisateur détient les droits** en clips courts prêts à publier. Répondre en français.

Ne pas télécharger de vidéos de tiers depuis YouTube ou d'autres plateformes : travailler uniquement sur les fichiers fournis par l'utilisateur (le téléchargement automatique de l'original a été retiré).

## Étape 1 : vérifier l'environnement

- FFmpeg disponible (`ffmpeg -version`) ; pour incruster des sous-titres, FFmpeg doit gérer libass.
- Python 3 pour les scripts du dossier `scripts/`.

## Étape 2 : récupérer la vidéo et ses sous-titres

- Le fichier vidéo (MP4 de préférence) envoyé par l'utilisateur.
- Les sous-titres (.vtt ou .srt). Sources possibles : export YouTube Studio de sa propre vidéo, transcription vidéo vidIQ, outil de transcription. Sans sous-titres, demander une transcription horodatée ; ne jamais inventer le contenu.

## Étape 3 : trouver les meilleurs passages (le cœur du skill)

1. Structurer les sous-titres : `python3 scripts/analyze_subtitles.py sous-titres.vtt [durée_cible_s] [sortie.json]`.
2. Analyser le texte et proposer des **chapitres / clips** de 30 à 90 s, chacun avec : titre accrocheur, début et fin précis, résumé en une phrase, mots-clés, potentiel (fort / moyen) et pourquoi.
3. Principes : un clip = une idée complète ; ça commence par une phrase forte (pas par « alors… ») ; ça finit sur une conclusion ou un rebondissement ; pas de coupe au milieu d'une phrase. Privilégier : conseils concrets, erreurs à éviter, moments d'émotion, chiffres surprenants, réponses à des questions fréquentes.

## Étape 4 : faire choisir l'utilisateur

Présenter la liste et demander quels clips produire et avec quelles options (format vertical 9:16, sous-titres incrustés, taille de police).

## Étape 5 : produire

- Couper : `python3 scripts/clip_video.py entree.mp4 00:05:47 00:06:52 clip1.mp4`
- Extraire les sous-titres du passage : `python3 scripts/extract_subtitle_clip.py sous-titres.vtt 00:05:47 00:06:52 clip1.srt`
- Recadrer en vertical si demandé (ex. : `ffmpeg -i clip1.mp4 -vf "crop=ih*9/16:ih,scale=1080:1920" -c:a copy clip1_vertical.mp4`, en ajustant le cadrage sur le visage).
- Incruster les sous-titres : `python3 scripts/burn_subtitles.py clip1_vertical.mp4 clip1.srt clip1_final.mp4 [taille_police] [marge_basse]`
- Optionnel : traduction des sous-titres (faite par Claude directement) et sous-titres bilingues via `scripts/merge_bilingual_subtitles.py`.
- Résumé de publication par clip (titre, description, hashtags) : `scripts/generate_summary.py` ou rédigé directement.

## Étape 6 : livrer

Envoyer les fichiers finaux et un tableau : clip, durée, titre proposé, description, hashtags, plateforme conseillée.

---
Adapté et traduit par Merex Academy à partir de « Youtube-clipper-skill » d'op7418 (github.com/op7418/Youtube-clipper-skill), licence MIT. Le module de téléchargement YouTube a été retiré ; les scripts d'origine (commentaires en chinois) sont conservés.
