# Article

**Optimal spectral transportation with application to music transcription**

*Rémi Flamary, Cédric Févotte, Nicolas Courty, Valentin Emiya*

NIPS, décembre 2016

# Résumé

## Introduction

Un spectre de signal est composé de composantes temporelles **(v_n)**, qui sont ses trames. Nous noterons **M** leur dimension.

Une méthode classique est d'utiliser un dictionnaire **W** tel que l'on puisse approximer **v_n** par **W\*h_n** avec **h_n > 0**, et ce pour tout n.

On observe cependant un léger décalage en fréquence en réalité, ce qui complique l'application de cette méthode.

Une solution, quoiqu'irréaliste, est d'agrandir la taille du dictionnaire utilisé. Certains articles de la littérature lui préfèrent l'usage de dictionnaires adaptatifs. Cependant ceux-ci ne sont pas capables de prendre en compte les variations temporelles dans le jeu des notes. C'est alors que l'emploi du transport optimal peut permettre de contourner cette difficulté.

## PLCA

La méthode PLCA est très utilisée en traitement du signal audio. Elle repose sur une factorisation matricielle non-négative.

Les échantillons **v_n** sont alors vu comme distribution de probabilité (leur colonne se somme à 1).

Pour approximer **V** comme **WH**, on cherche donc **H = argmin (DKL(V|WH))** où **DKL** est la divergence KL.
