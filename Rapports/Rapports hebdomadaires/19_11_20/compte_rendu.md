# DONE

## Manipulations
### Solveur TO
- Application du solveur à des exemples de difficulté croissante :
    1. Complexification du dictionnaire avec des signaux inutiles
    2. Complexification du signal par du bruit blanc

### Prétraitement des données
- Affinage de la méthode de soustraction de l'artefact de pouls
    -> Recalibrage des mesures des pics par délai (fixé à la main)
    -> Recentrage sur les pics
    => Signal non satisfaisant


# TODO

## Manipulations
### Solveur
- Augmenter la précision du solveur; pour évaluation : reconstruire spectrogrammes et comparer visuellement voire utiliser la  "min squared error".
- Exemples :
    1. variations temporelles : amplitude,
    2. Construire un signal eeg réaliste :
        1. Prendre un signal nettoyé par MNE
        2. appliquer un filtre passe-bande 8-10 Hz
        3. ajouter un artefact de pouls classique en retirant quelques fréquences secondaires pour simplifier
        4. ajouter un artefact de gradient classique en retirant quelques fréquences secondaires pour simplifier
        5. appliquer le solveur (avec dictionnaire composé des trois signaux)
        6. regarder ce que ça donne (spectrogramme et éventuellement signal signal ?)
        7. ajouter du bruit.

# Éventuellement :
### MNE
Obtenir un signal propre d'artefact de pouls



## Date de la prochaine réunion :
**Mercredi 27 novembre, 11h00**
