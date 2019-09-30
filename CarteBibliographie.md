# Carte de la bibliographie

##Debruitage des EEG

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

## Transport optimal

### OST_Music_2016.pdf

*Rémi Flamary, Cédric Févotte, Nicolas Courty, Valentin Emiya*

Article d'octobre 2016 qui emploie le transport optimal pour la transcription de signaux musicaux.

Les propriétés de la multiplicité des harmoniques sont exploitées, ce que nous ne pouvons pas faire.

Usage de la méthode PLCA, inspirée de PLSA (Probabilistic Latent Semantic Analysis) qui est utilisée dans le traitement du signal audio.

Usage de la regularisation entropique

Code python https://github.com/rflamary/OST

Lien original : Mail de Julie

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
