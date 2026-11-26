# Cabine
Cabine — enregistrer un livre audio au clavier, sur macOS et Windows, sans quitter la prise des yeux.

L’enregistrement et le montage se font dans le même geste. Entrée insère une prise. Maj + Entrée réécoute deux secondes puis remplace la suite, pour rattraper une phrase sans laisser de chute sur la piste.

Le fichier gardé est un WAV mono 44,1 kHz, 24 bits, un par chapitre. Cabine exporte aussi le FLAC correspondant, et le MP3 à débit constant 192 kbit/s qu’ACX et Audible demandent.

## Le geste, en une minute

1. Le micro est écouté en permanence (vu-mètre), mais **rien n’est écrit tant qu’on n’a pas appuyé sur Entrée**.
2. **Entrée** démarre l’enregistrement. **Entrée** l’arrête.
3. À l’arrêt, **Espace** lit et **Espace** met en pause. Le passage entendu reste **surligné**.
4. **Flèche gauche** et **flèche droite** déplacent la tête de lecture.
5. Des touches, affichées en permanence, posent un marqueur (début, fin, erreur), **séparent** la piste, ou **effacent** le passage sélectionné. **Maj + Entrée** reprend la phrase dans la foulée.
6. À la fin, Cabine exporte le chapitre déjà monté : WAV, FLAC, ou MP3 pour la plateforme.

## Télécharger

Les installeurs sont sur la [page Releases](https://github.com/MaelieD/Cabine/releases).

| Système | Fichier | Version minimale |
| --- | --- | --- |
| macOS Apple Silicon | `Cabine_x.y.z_aarch64.dmg` | macOS 12 |
| macOS Intel | `Cabine_x.y.z_x64.dmg` | macOS 12 |
| Windows 64 bits | `Cabine_x.y.z_x64-setup.exe` | Windows 10 |

Les sommes SHA-256 sont publiées à côté des fichiers. On vérifie la somme avant d’ouvrir l’installeur.

Premier lancement :

- **Mac.** Si le système indique que l’application vient d’un développeur non identifié, clic droit sur l’application, puis Ouvrir. Ensuite : Réglages Système, Confidentialité et sécurité, Microphone, autoriser Cabine.
- **Windows.** Tant que le binaire n’est pas signé, SmartScreen affiche un avertissement : Informations complémentaires, puis Exécuter quand même. Autoriser le micro si Windows le demande.

## État

La v1 couvre la séance au clavier : prise au micro, sans filtre, retour casque coupé pendant l'enregistrement, montage, puis export.

L'export propose le WAV maître, le FLAC (Findaway Voices) et le MP3 192 kbit/s constant (ACX et Audible), plus le CSV des repères. La finition (v1.1 : RMS, limiteur, ambiance) et la transcription (v1.2) ne sont pas encore construites.

## Licence

Tous droits réservés. Voir [LICENSE](LICENSE).

# Ce que fait Cabine

Cabine enregistre une voix de livre audio sur macOS et Windows, au clavier. Le son reste sur l’ordinateur : pas de compte, pas de serveur, pas de publicité. Rien n’est écrit tant qu’on n’a pas appuyé sur Entrée. La prise est le micro, sans filtre. Le retour casque se coupe pendant l’enregistrement.

## Projets et chapitres

- Nouveau projet, dans le menu Fichier. Le nom saisi devient le dossier, avec un premier chapitre vide. Les projets sont dans Documents/Cabine.
- Ouvrir un autre projet. Le sélecteur s’ouvre dans Cabine. Le projet choisi reprend son dernier chapitre.
- La fenêtre s’intitule « Cabine », suivi du nom du projet.
- Nouveau chapitre. Crée un chapitre vide dans le projet en cours. Le chapitre affiché reste sur le disque.
- Ouvrir un chapitre. Liste les chapitres du projet en cours.
- Le titre du chapitre se modifie en cliquant dessus.
- Cabine rouvre le dernier chapitre de chaque projet, au même endroit et avec le même zoom.
- Si l’application s’arrête pendant une prise, le son déjà écrit est conservé, à une seconde près.

## Enregistrer et écouter

- Entrée démarre une prise et l’insère à la tête. Entrée l’arrête.
- Maj + Entrée réécoute la fin (2 secondes par défaut), puis remplace seulement la fin de la section en cours. La section suivante est poussée, pas remplacée. Échap pendant cette pré-écoute n’écrit rien.
- Espace lit, et s’arrête tout seul à la fin du son enregistré. Le passage entendu reste surligné.
- Échap arrête une prise, ou retire la sélection sans effacer le son.
- Le vu-mètre montre le niveau, avec des repères à −12 et −3. Écrêtage s’allume si le micro sature, et reste allumé jusqu’au clic. Il ne modifie pas le son.
- Le retour casque s’ouvre ou se coupe. Cabine prévient s’il est trop lent pour parler en l’écoutant.

## Se déplacer et monter

- La piste montre l’onde, les sections, les repères, la tête et la sélection. On clique pour placer la tête, on trace pour sélectionner.
- La molette zoome. Glisser la règle de temps fait défiler. Le zoom ne déplace pas la tête.
- Flèches gauche et droite, par pas de 0,5 s. Alt et flèche, par pas de 3 s. Maj et flèche étend la sélection.
- Cmd et flèche gauche ou droite va au début ou à la fin de la piste. Sous Windows, c’est Ctrl et flèche.
- ( et ) passent à la section précédente ou suivante.
- I et O posent le début et la fin d’une sélection.
- Effacer retire le passage choisi et referme le trou. Après une lecture, sans sélection, il retire seulement la zone qui vient d’être entendue.
- C sépare la piste à la tête. Pendant une prise, cela ferme la section et enchaîne.
- Annuler et rétablir reviennent sur le dernier geste. Annuler une prise la retire de la piste. Le fichier reste jusqu’à « Oublier les prises écartées », dans les réglages.

## Repères

- M pose un point, B un début, F une fin, X une erreur. On peut les poser pendant qu’on parle.
- La liste en bas montre le type, le temps et une note. Cliquer une ligne place la tête. La note se rédige dans la liste.
- Les flèches haut et bas passent au repère précédent ou suivant.

## Réglages

- Choix du micro et de la sortie.
- Taille du tampon : 128, 256 ou 512.
- Durée de la pré-écoute, de 1 à 5 secondes, et fondu de reprise, de 5 à 30 ms.
- Chaque touche se change : on clique le raccourci, puis on appuie la nouvelle touche. Les raccourcis sont suspendus dans un champ de texte, et quand la fenêtre n’est pas au premier plan.
- Le bandeau sous la piste rappelle les touches, rangées par geste. Le bouton i de chaque groupe ouvre leur légende.

## Exporter

Un fichier par chapitre, déjà monté. Les prises écartées n’y sont pas. 

Un chapitre de plus de 120 minutes est refusé. 

Un CSV des repères est écrit à côté du fichier. Il ne part pas chez la plateforme.

Les formats :
- WAV 44,1 kHz, 24 bits, mono. Le fichier maître à garder.
- FLAC, le même son, sans perte. Utile pour Findaway Voices.
- MP3 à débit constant 192 kbit/s, 44,1 kHz, mono. Le fichier qu’ACX et Audible demandent.

## Soutenir

Le bouton Soutenir ouvre la page GitHub Sponsors. Cabine reste le même outil pour tout le monde.
