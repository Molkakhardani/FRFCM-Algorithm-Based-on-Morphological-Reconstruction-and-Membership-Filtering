# FRFCM-Algorithm-Based-on-Morphological-Reconstruction-and-Membership-Filtering
Significantly Fast and Robust Fuzzy C-Means Clustering Algorithm Based on Morphological Reconstruction and Membership Filtering
# Significantly Fast and Robust Fuzzy C-Means Clustering Algorithm Based on Morphological Reconstruction and Membership Filtering
## 
_Tao Lei , Xiaohong Jia, Yanning Zhang, Senior Member, IEEE, Lifeng He, Senior Member, IEEE,

[![N|Solid](https://cldup.com/dTxpPi9lDf.thumb.png)](https://nodesource.com/products/nsolid)

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

c'est une implimentation de l'article " Significantly Fast and Robust Fuzzy C-Means Clustering Algorithm Based on Morphological Reconstruction and Membership Filtering "


"Comme l'algorithme de clustering Fuzzy C-Means (FCM) est sensible au bruit, des informations spatiales locales sont souvent introduites dans une fonction objective pour améliorer la robustesse de l'algorithme FCM pour la segmentation d'images. Cependant, l'introduction d'informations spatiales locales entraîne souvent une complexité computationnelle élevée, due au calcul itératif de la distance entre les pixels au sein de voisins spatiaux locaux et des centres de clustering. Pour résoudre ce problème, un algorithme FCM amélioré basé sur la reconstruction morphologique et le filtrage des appartenances (FRFCM) est proposé dans cet article, étant significativement plus rapide et plus robuste que le FCM. Premièrement, les informations spatiales locales des images sont incorporées dans le FRFCM en introduisant une opération de reconstruction morphologique pour garantir l'immunité au bruit et la préservation des détails de l'image. Deuxièmement, la modification de la partition d'appartenance, basée sur la distance entre les pixels au sein de voisins spatiaux locaux et des centres de clustering, est remplacée par un filtrage d'appartenance locale qui dépend uniquement des voisins spatiaux de la partition d'appartenance. Comparé aux algorithmes de pointe, l'algorithme FRFCM proposé est plus simple et significativement plus rapide, car il n'est pas nécessaire de calculer la distance entre les pixels au sein de voisins spatiaux locaux et des centres de clustering. De plus, il est efficace pour la segmentation d'images bruitées car les filtrages d'appartenance sont capables d'améliorer efficacement la matrice de partition d'appartenance. Les expériences réalisées sur des images synthétiques et réelles démontrent que l'algorithme proposé.



## Features

- !pip install scikit-image
- 
## Tech
- Python
- Numpy
- openCv
- Google Colab
## Data 
Berkeley Segmentation Data Set (BSDS) 

## Development

#### Fonction label_image

Cette fonction prend une image et un ensemble d'étiquettes de clustering et renvoie une image segmentée. Pour chaque segment (cluster), elle calcule la médiane des couleurs ou de l'intensité des pixels dans ce segment et applique cette valeur médiane à tous les pixels du segment. Cela permet de segmenter l'image en différentes régions basées sur les clusters.
#### Fonction fcm_image_color
Cette fonction effectue le clustering FCM sur une image donnée. Elle commence par aplatir et préparer les matrices d'appartenance pour chaque pixel de l'image. Ensuite, elle détermine le cluster dominant pour chaque pixel et utilise label_image pour segmenter l'image en fonction de ces clusters.

#### Fonction initialize_membership
Initialise les matrices d'appartenance pour le clustering FCM. Elle crée une matrice d'appartenance aléatoire pour chaque échantillon (pixel) et chaque cluster, puis normalise ces matrices.

#### Fonction frfcm_c
C'est la fonction principale qui implémente l'algorithme FRFCM (Fuzzy-Robust FCM). Le processus se déroule en plusieurs étapes :

Reconstruction morphologique : Applique la reconstruction morphologique pour préserver les détails et réduire le bruit dans l'image. Cette étape est effectuée séparément pour chaque canal de couleur si l'image est en couleur.

Conversion en espace colorimétrique LAB : Convertit l'image traitée en espace LAB pour une meilleure segmentation des couleurs.

Clustering FCM sur histogramme : Effectue le clustering FCM sur les données de l'image en espace LAB. Cette étape comprend le calcul des centres de cluster et la mise à jour des matrices d'appartenance.

Filtrage des appartenances : Applique un filtre médian sur les matrices d'appartenance pour chaque cluster pour améliorer la robustesse contre le bruit.

Normalisation des appartenances : Normalise les matrices d'appartenance après le filtrage.

Conversion des centres en RGB : Convertit les centres des clusters de l'espace LAB en RGB pour la représentation finale.
## Evaluation
#### metriques
Segmentation Accuracy (SA):  mesure la proportion de pixels correctement classifiés dans l'image segmentée
𝑆𝐴=  "TP + TN" /(𝑇𝑃 + 𝑇𝑁 + 𝐹𝑃 + 𝐹𝑁)


Matthews Correlation Coefficient (MCC): prend en considération l'équilibre entre la sensibilité ( + ) et la spécificité ( - )
𝑀𝐶𝐶=  (𝑇𝑃∙ 𝑇𝑁 − 𝐹𝑃∙ 𝐹𝑁)/√("(TP + FP) " ∙" (TP + FN) " ∙" (TN + FP) " ∙" (TP + FN" ))


Sorensen-Dice Similarity (SDS):  quantifie la similitude entre la région segmentée et la région du masque (VT)
𝑆𝐷𝑆=  (2∙"TP " )/(2∙𝑇𝑃 +𝐹𝑁 + 𝐹𝑃 )

#### evaluation de l'image reelle 
Accuracy: 0.9661660222407886
MCC: 0.92761917356032
sds: 0.9827919019164761
#### evaluation des images synthetiques
 Noise
1er image 
2eme image 
Salt & Pepper 10%
99.93% 
99.89%
Uniform 10%
71.81%
87.44%
Gaussian 3%
35.47%
38.23%



/README.md>
