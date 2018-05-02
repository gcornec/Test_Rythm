Voici le notebook que j’ai réalisé dans le cadre du challenge data de Rythm !
Les données peuvent être trouvé par ce lien : 
https://challengedata.ens.fr/en/challenge/37/learning_sleep_stages_from_physiological_signals_on_dreem_headband.html

Elles sont constituées de 9 bases différentes sous le format h5 qui représentent différentes mesures faite grâce au bandeau dreem.
Comme les données sont assez volumineuses et que je ne peux pas les charger entièrement en local car la RAM de mon mac est trop faible, je me suis attaché à récupérer un nombre réduit de variables pour effectuer mes prédictions.

Mon notebook est décomposé en quatres parties :
-	apport des packages nécessaires (essentiellement pandas, numpy et scikit.learn)
-	fonctions intermédiaires 
-	Mise en place d’un modèle basique sur chacune des sous-bases de l’échantillon d’apprentissage pour récupérer dans chaque cas les 10% des variables les plus importantes puis récupération des bases d’apprentissage et de test mais seulement avec les 10% de variables importantes présélectionnées 

Rq : on remarque que la précision du modèle est meilleure pour les bases de données de type « eeg » que les autres 
Rq : je n’ai pas mis la normalisation par défaut car lorsque j’ai fait des tests, elle ne donnait pas de meilleurs résultats 


-	Ensuite j’ai choisi de faire tourner un Random Forest Classifier et j’ai fait une 5-CV sur 5000 observations de la base d’apprentissage pour choisir quels hyperparamètres choisir (nombre d’arbres dans la forêt et nb minimum d’observations dans les feuilles)

-	Enfin j’ai fait tourné le meilleur modèle que j’ai trouvé sur les données d’apprentissage et j’ai fait la prédiction finale sur les données de test

Si j’avais eu plus de temps :
-	j’aurais implémenté la métrique de Cohen Kappa
-	j’aurais testé d’autres modèles (notamment des modèles de Deep Learning) et leur hyperparamètres 
-	j’aurais réfléchi à une meilleure manière de normaliser les données 

