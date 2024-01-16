Nous allons réaliser une étude de la consommation de gaz en france et tenter de prédire la consommation entre fin 2021 et fin 2022.
Les données utilisés viennent de : https://odre.opendatasoft.com/explore/dataset/consommation-quotidienne-brute/information/?sort=-date_heure&refine.date_heure=2022.

La première étape de notre travail consiste à nettoyer les données et à les représenter. Pour cela nous utilisons la librairie Panda de Python qui nous permet de trier plus facilement les données et nous facilitera les operations suivantes. Une fois nos cela fait nous pouvons enfin tracer le graphe representatif de nos données:

![image](https://github.com/OhbSarah/SerieTemp/assets/139919020/15ab6103-e7d1-48e4-b26a-47b33501c55c)

Nous constatons à l'oeil nue la présence d'une saisonnalité. Nos données ne sembles pas être satationnaire. Nous allons donc passer au log nos données pour rendre toutes saisonnalités multiplicatives additives. Aprés cela nous effecturons une première différenciation sur une période de 1ans (période visible a l'oeil nue et assez logique : la consommation de gaz est saisonniére (hiver/automne et printemps/été)). Ce qui nous donne le graphique suivant :

![image](https://github.com/OhbSarah/SerieTemp/assets/139919020/6eb8e110-1300-4441-98a0-175913e4ce63)

Pour faciliter les tracer graphique suivant nous appliquons la fonction exponentielle à nos données.
Notre série nous semble maitenant stationnaire, pour verifier cela nous allons effectuer le Test augmenté de Dickey-Fuller qui consiste à vérifier l'existence de racine unitaire. 
On a H0= "Les données ne sont pas stationnaire" (présence de racine unitaire). Nous décidons de rejeter cette hypothése si la statistique de test fournit est inferieur au niveau de signifaction 
