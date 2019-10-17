# Carte de la bibliographie

## Debruitage des EEG

### These_Hajipour_Sardouie.pdf

Thèse de 2017 qui compare différente de débruitage des EEG pour le traitement de l'épilepsie.

Méthodes abordées :

 - GEVD (generalize eigen value decomposition); extension Temps-Fréquence (TF-GEVD)
 - DSS (denoising source separation); extension Temps-Fréquence (TF-DSS)
 - JDICA (Jacobi-like deflationary independant components analysis);
 - SSD-CP (simultaneous Schur decomposition)

Lien original : https://tel.archives-ouvertes.fr/tel-01493660

### These_Isaac_Yohan.pdf

Thèse de 2015 qui propose une technique de signaux redondants.

Bibliographie intéressante ?

### ExtractionStatistiqueDeCaractéristiques.pdf

**Statistical Feature Extraction for Artifact Removal from Concurrent fMRI-EEG Recordings**

*Zhongming Liu, Jacco A. de Zwart, Peter van Gelderen, Li-Wei Kuo, and Jeff H. Duyn, for NeuroImage*

Article de février 2012 qui propose une méthode statistique de suppression d'artéfacts de gradient et de pouls, inspirée des méthodes de classification.

Hypothèse : périodicité des artefacts de gradient et de pouls, d'où l'utilisation de méthodes de soustraction de modèle.
            Pour l'AP, la variabilité temporelle est bien plus grande (détails en introduction), ce qui limite leur efficacité.

Mention des techniques de séparation de source à l'aveugle, type analyse de composents indépendants (*ICA*).

Étapes de la correction du gradient :
  1. normalisation par soustraction de la moyenne des périodes (entre deux stimuli);
  2. décomposition en valeurs singulières (*SVD*);
  3. décomposition en une base de produits vectoriels; le premier représente un modèle temporel qui couvre la durée de l'acquisition d'une tranche, et le second les variations d'amplitude entre différentes acquisitions;
  4. les composantes de cette base sont classifiés AG, si ils reflètent une stabilité ou une faible variation temporelle, tandis que les signaux cérébraux sont indépendants du découpage, avec des amplitudes variant autour de zéro au cours des acquisitions.
  5. application d'un filtre passe-bas à 125 Hz et sous-échantillonnage à 250 Hz.

Étapes de la correction du pouls :
  1. application de l'ACI;
  2. identification des composants liés au pouls à l'aide des données calculées entre le signal EEG et le *component time-cours*;
  3. identification des "pics R";
  4. application d'un filtre basée sur la DVS pour neutraliser leur effet.
  5. inversion de l'ACI.

Lien original : https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3254729/pdf/nihms333200.pdf

Code Matlab : http://www.amri.ninds.nih.gov/software.html

### DébruitageOndelettes_2016.pdf

**Better Approach for Denoising EEG Signals**

*Gautam Kaushal, Amanpreet Singh, V.K. Jain for IEEE*

Article de 2016 qui présente une méthode non-supervisée et à calcul rapide pour le débruitage d'EEG par l'emploi d'ondelettes.

Présentation des bandes de fréquences EEG.

Difficultés liés au retrait d'artefacts :
  - plus grande amplitude que le signal d'intérêt;
  - large bande de fréquence occupée;
  - leur distribution topographique variable.

Deux principaux artefacts :
  - électro-oculogramme (EOG), lié aux mouvements oculaires (clignement, déplacement du regard);
  - électro-cardiogramme (ECG), lié aux battement du cœur (artefact de pouls).

Méthode efficace et peu coûteuse : détecter l'EOG et le soustraire à l'EEG.

**Référence  M. A. Klados et al [7,8] qui aurait comparé plusieurs méthodes.**

Méthode (**analyse des composants indépendants améliorée par vaguelettes**) (*Wavelet-ICA*):
  1. application d'une ACI;
  2. identification des sources d'artefacts;
  3. remplacement des composantes artéfactuelles par leur partie bruitée à l'aide de vaguelettes;
  4. application inversée d'une ACI pour les sources non artéfactuelles.

Utilisation de l'outil *FastICA* pour l'ACI.

Détails de l'étape 3 :
  1. décomposition des composantes artéfactuelles par transformée par vaguelettes stationnaires (*STW*); la vaguelette mère employée est celle de Haar (simple et à convergence rapide) au cinquième niveau de décomposition (cela fournit des résultats satisfaisants);
  2. application d'un seuil; *WTCF*;
  3. reconstruction inverse des vaguelettes.

Outils pour l'identification des sources artéfactuelles :
  - *Mutual Info*;
  - *Projection Strength*;
  - *Correlation*;
  - *Kurtosis*



Lien original : https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=7993455

### Revue_Débruitage.pdf

**A survey on different noise removal techniques of EEG signals**

*Priyanka Khatwani1, Archana Tiwari*

Article de février 2013 qui passe en revue différente méthodes de débruitage des signaux EEG.

Méthodes évaluées :
  - **analyse de la composante principale** (*PCA*); sensible aux variations d'échelles entre les variables initiales (même variables d'échantillonnage et corrélation positive);
  - **analyse des composantes indépendantes** (*ICA*); cf. *Hyvarinen et al.*; généralement, perte d'information, car la composante d'intérêt est souvent unique et contient des informations non liées à l'artefact; performances dépendantes de la taille du jeu de données; incapacité de la méthode à faire des analyses fréquentielles (seulement temporelles), **alors que les artéfacts EEG occupent généralement un champ de fréquences particulier**, et se mélangent au spectre du signal d'intérêt.
  - **ondelettes**; efficace sur les phénomènes non-stationnaires ou transitoires;
  - **paquets d'ondelettes**; cf. *Michal  Kubinyi  et al.*, 2011; résultats efficaces à la fois sur les approximations et les détails.

La méthode basée sur les paquets d'ondelettes obtient de plus grands ratios bruit-signal (*PSNR* et *SNR*) et une plus faible erreur carrée moyenne (*MSE*), ce qui est synonyme d'un signal moins bruité.

Lien original : https://pdfs.semanticscholar.org/5fd1/00cd6261e11760fe3b4009b9f686c397cae7.pdf

### Soustraction_ArtefactPouls_1998.pdf

**Identification of EEG Events in the MR Scanner: The Problem of Pulse Artifact and a Method for Its Subtraction**

*Philip J. Allen, Giovanni Polizzi, Karsten Krakow, David R. Fish, et Louis Lemieux*

Article de 1998 paru dans NeuroImage qui présente une méthode de soustraction de l'artefact de pouls dans un signal EEG.

Utilisation de l'IRM pour repérer immédiatement les endroits où se déroulent les événements repérés par une EEG. Plusieurs applications existent.
Artefacts nés d'interactions entre le patient, les électrodes métalliques, et le champ magnétique. Détail étendu de telles interactions.

Mesure de l'amplitude et de la distribution de l'artefact.

Algorithme de soustraction initial (seconde par seconde) :
  1. identification des pics ECG (complexe QRS) dans les 10 secondes précédentes;
  2. calcul de la forme moyenne d'AP sur ces 10 secondes, plus ou moins la moitié de l'intervalle RR (intervalle entre deux pics), pour chaque signal EEG de référence;
  3. soustraction de la forme moyenne du signal sur les 3 dernières secondes, i.e. sur l'avant dernière seconde et les deux l'entourant;
  4. affichage de l'avant dernière seconde.

L'affichage est donc **décalé d'une seconde**.

Raison des choix :
  - avant-dernière seconde parce que le calcul de la forme moyenne d'AP pourrait devoir déborder sur une durée d'un intervalle R-R après la seconde affichée.
  - fenêtre de 10 secondes comme compromis entre assez long pour un bon moyennage, et assez court pour s'adapter aux variations.

Il est important de détecter un maximum de pics car ceux non perçus peuvent perturber ces calculs, mais cela est difficile.

Méthode de détection des pics: recherche d'un point d'inversion de la courbe après un passage de seuil d'amplitude;

Pour faciliter cela :
  1. application d'un filtre passe bas à moyenne glissante sur trois coefficients pour réduire le bruit de haute fréquence;
  2. application d'un filtre passe haut à réponse impulsionnelle finie, avec 25 coefficients et une coupure de 20 Hz pour atténuer les changements de référentiel;
  3. découpage de la fenêtre de 10s en sections de 0.5s; rejet des sections d'amplitude moyenne relativement trop haute pour éviter des faux positifs dûs aux artefacts de l'ECG;
      la méthode est comme suit;
        1. un premier seuil est fixé comme 4 fois l'amplitude moyenne des 10 sections d'amplitude minimale;
        2. on calcule des valeurs maximales et minimale, et on regarde laquelle est la plus éloignée de la valeur moyenne; ces valeurs sont calculées comme la moyenne des 5 plus grandes (resp. plus faibles) valeurs dans des sections différentes; celles des 5 qui sont au moins 2 fois supérieures à la plus faible sont finalement exclues comme pics de bruit;
        3. on définit un seuil comme la différence entre le maximum et le minimum, plus ou moins 33% de celle-ci, selon le résultat de l'étape précédente.

Validation des pics a posteriori par le calcul fonction de corrélation croisée entre la forme d'onde ECG à chaque pic et une forme d'onde ECG moyenne.
Ajout de pics manqués dans les premières étapes.

**Figure 2. résumant bien l'algorithme**.

Validation de l'algorithme de soustraction par analyse de fréquence.

Composants résiduels après traitement, mais réduction significative des artefacts.

### Suppression_ArtefactsImagerie_2000.pdf

**A Method for Removing Imaging Artifact from Continuous EEG Recorded during Functional MRI**

*Philip J. Allen, Oliver Josephs, et Robert Turner*

Article publié en 2000 dans NeuroImage présentant une méthode de réduction de l'artefact d'imagerie (*Imaging Artifact*).

Artefacts nés d'interactions entre le patient, les électrodes métalliques, et le champ magnétique. Détail étendu de telles interactions.

**TODO**

## Transport optimal

### OST_Music_2016.pdf

**Optimal spectral transportation with application to music transcription**

*Rémi Flamary, Cédric Févotte, Nicolas Courty, Valentin Emiya*

Article paru dans NIPS, d'octobre 2016 qui emploie le transport optimal pour la transcription de signaux musicaux.

Les propriétés de la multiplicité des harmoniques sont exploitées, ce que nous ne pouvons pas faire.

Usage de la méthode *PLCA*, inspirée de *PLSA* (*Probabilistic Latent Semantic Analysis*) qui est utilisée dans le traitement du signal audio.

Usage de la régularisation entropique

Code python https://github.com/rflamary/OST

Lien original : https://arxiv.org/abs/1609.09799

### MinimumWassersteinEstimate.pdf

*Hicham Janati, Thomas Bazeille, Bertrand Thirion, Marco Cuturi, Alexandre Gramfort*

(Procédure MWE - Minimum Wasserstein Estimate)

Prépublié de février 2019 qui propose une procédure pour la localisation des sources de signaux EEG.

Il propose des statistiques sur plusieurs sujets pour pallier le manque de précision des détections.

Sa référence [15] (MTW) emploie un transport optimal déséquilibré (UOT), apparemment sur un seul sujet (À regarder !).
L'UOT est également présenté en début de section 3

Lien original : https://hal.inria.fr/hal-02013889v2/document

### MultiTaskWasserstein.pdf

*Hicham Janati,  Marco Cuturi,  Alexandre Gramfort*

Prépublié de mai 2018 (revu janvier 2019) qui propose un méthode de résolution des problèmes de régression en haute dimension, basée sur le TO, avec un champ d'ouverture en neuroimagerie.

Emploi d'un transport optimal déséquilibré (UOT). Le calcul ajoute des termes faibles au produit de Frobénius (entropie et contraintes marginales).

La régularisation entropique amènerait une stricte convexité et un calcul plus rapide (cf. Cuturi 2013).

Les contraintes marginales (contribution) semblent permettre de rapprocher la solution (ramenée sur un vecteur) des vecteurs source et cible.

Code python en annexe.

Lien original : https://arxiv.org/pdf/1805.07833.pdf

###NB : Ajouter biblio Julie

### Liens :

Suppression du gradient & pouls https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3254729/
