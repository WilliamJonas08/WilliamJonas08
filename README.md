Ce projet a été réalisé dans le cadre d'un projet de mon Master Intelligence Artificielle et Apprentissage Automatique.

Il s'agit d'un projet de labélisation non supervisée d’une base de données de vocalisations de Marmoset, réalisé dans le contexte de l’étude comparative de la perception de la voix chez les primates (projet ERC COVOPRIM dirigé par le Professeur Pascal Belin) en partenariat avec l’Institut des Neurosciences de la Timone (INT).

L'objectif est de construire un jeu de données labélisé de vocalisation de Marmousets (Callithrix jacchus) suffisamment important pour pouvoir entraîner des réseaux de neurones.
Un tel réseau pourrait servir à calculer des représentations de haut niveau des différentes vocalisations présentes chez l’espèce.

On dispose d'enregistrements segmentés de plusieurs centaines d’heures (+ de 300k données) ainsi que des représentations temps-fréquence qui sont calculées pour chaque segment correspondant à une vocalisation.
La quantité de données étant trop importantes pour une labélisation manuelle, le but de ce projet est l’utilisation de stratégies non supervisées afin de les labéliser.

📌 Les stratégies utilisées sont :
- la réduction de dimensionnalité
- le clustering non supervisé des représentations (afin de dégager des premières tendances de labélisation),
- implémentation d’une stratégie de Deep Online Active Learning

📌 Stratégie de Deep Online Active Learning:
- Entrainement d'un auto-encodeur sur des images correspondant à des représentations temps-fréquence des vocalises ( le CNN encodeur agira comme un classifieur pour nos futurs exemples )
- Proposition itérative des meilleures données à labéliser à un expert humain
- Fine-tuning du CNN (Convolutionnal Neural Network) grâce aux nouvelles données labélisées
