Projet Machine Learning : Analyse Bien-Être

Description du Projet
Ce projet porte sur un dataset de bien-être comprenant 20 variables numériques liées à la santé, aux habitudes de vie et aux données socio-économiques.
L'objectif est d'explorer les données, réduire la dimension, construire des modèles de classification et appliquer du clustering non supervisé.
Contenu du Dataset
Nombre d'observations : 10 000
Variables : age, taille, poids, revenu, education, imc, stress, nb_enfants, exercice, alimentation, sommeil, pression, cholesterol, activite, satisfaction, risque, sante, bienetre, etc.
Cible : target (3 classes)

Etapes de l'Analyse

1. Prétraitement

Nettoyage des doublons
Gestion des valeurs manquantes (aucune valeur manquante détectée)
Normalisation des données avec StandardScaler

2. PCA (Analyse en Composantes Principales)
   
PCA à 2 dimensions pour visualisation :
PC1 : 52.37% de variance expliquée
PC2 : 4.91%
PCA cumulée : 95% de la variance est capturée avec 16 composantes

3.  Modèles de Classification Supervisée

Modèle
Accuracy
KNN(k=5) = 99.90%

Régression Logistique=99.95%

Arbre de Décision =97.95%


Matrices de confusion affichées pour chaque modèle.

4.  Clustering Non Supervisé (KMeans)
Nombre de clusters : 3
Indice ARI (Adjusted Rand Index) comparaison avec classes réelles  : 1.00 ✔️
Visualisation des clusters vs. répartition réelle via PCA 2D

5. ⚖ Optimisation par Grid Search
Modèle : KNN
Meilleurs hyperparamètres trouvés :
{
  "metric": "euclidean",
  "n_neighbors": 9,
  "weights": "uniform"
}

Accuracy sur test : 99.90%

Validation croisée (5-fold) :
Moyenne : 99.95%
Écart-type : 0.03%

 Analyse Finale
L’analyse en composantes principales (PCA) a joué un rôle essentiel dans la compréhension de la structure des données. En projetant le dataset dans un espace réduit à deux dimensions, la PCA a permis de visualiser clairement la séparation naturelle entre les différentes classes, sans même utiliser la variable cible. Bien que la PCA n’ait pas été directement utilisée pour l'entraînement des modèles supervisés (les performances ayant été obtenues sur les données normalisées complètes), elle a permis de confirmer que les données étaient bien structurées et fortement discriminantes. Cette bonne séparabilité visuelle explique en grande partie les excellents résultats obtenus par les algorithmes de classification, ainsi que la performance parfaite du clustering non supervisé avec KMeans (ARI = 1.00). Ainsi, la PCA a agi comme un outil exploratoire et de validation précieuse, contribuant indirectement à l’interprétation et à la justification des performances des modèles.

 Conclusion

Ce projet illustre une approche de machine learning complète et robuste, allant du prétraitement à la classification supervisée et au clustering. Il montre l'efficacité des techniques modernes telles que la PCA, le GridSearchCV et la validation croisée dans l'analyse de données bien structurées.



