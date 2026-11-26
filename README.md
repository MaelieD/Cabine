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

Les installeurs ne sont pas encore publiés. Ils arriveront sur la [page Releases](https://github.com/MaelieD/Cabine/releases). Chaque release contiendra :

| Système | Fichier | Version minimale |
| --- | --- | --- |
| macOS Apple Silicon | `Cabine_x.y.z_aarch64.dmg` | macOS 12 |
| macOS Intel | `Cabine_x.y.z_x64.dmg` | macOS 12 |
| Windows 64 bits | `Cabine_x.y.z_x64-setup.exe` | Windows 10 |

Les sommes SHA-256 seront publiées à côté des fichiers. On vérifie la somme avant d’ouvrir l’installeur.

Premier lancement :

- **Mac.** Si le système indique que l’application vient d’un développeur non identifié, clic droit sur l’application, puis Ouvrir. Ensuite : Réglages Système, Confidentialité et sécurité, Microphone, autoriser Cabine.
- **Windows.** Tant que le binaire n’est pas signé, SmartScreen affiche un avertissement : Informations complémentaires, puis Exécuter quand même. Autoriser le micro si Windows le demande.

## État

La v1 est dans ce dépôt : séance au clavier, moteur audio Rust, interface React. On la lance depuis le code source avec les commandes ci-dessus. La prise est le micro, sans filtre. Le retour casque se coupe pendant l’enregistrement.

L’export propose le WAV maître, le FLAC (Findaway Voices) et le MP3 192 kbit/s constant (ACX et Audible), plus le CSV des repères. La finition (v1.1 : RMS, limiteur, ambiance) et la transcription (v1.2) sont spécifiées, pas encore construites.

Le comportement, les raccourcis et le format des fichiers sont décrits dans [docs/SPECIFICATION.md](docs/SPECIFICATION.md).

## Licence

Tous droits réservés. Voir [LICENSE](LICENSE).
