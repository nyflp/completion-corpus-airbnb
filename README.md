# Titre du projet

Ce projet s'inscrit dans le cadre de mon master d'humanités numériques co-acrédité par l'*Université Lumière Lyon 2*, l'*Université Jean Moulin Lyon 3*, l'*École Nationale Supérieure des Sciences de l'Information et des Bibliothèques, et l'École Normale Supérieure de Lyon*. 

Nous étions originalement deux sur ce projet, mon ami MJEKU Olti et moi-même. Initialement, il avait pour but de travailler sur les _reviews_ Airbnb. L'objectif était de profiter de la grande taille des bases de données fournies par la plateforme pour nous exercer sur l'utilisation de l'IA dans les analyses statistiques. Cependant, nous avons rapidement été confrontés à un problème d'envergure : la qualité des données. Même les informations les plus basiques, comme l'âge ou le genre des _reviewers_, sont manquantes, rendant impossible toute analyse sociologique rigoureuse. 

Parmi les rares informations disponibles dans la base de données compilant l'ensemble des _reviews_, se trouvait le prénom de la personne ayant rédigé l'avis. À partir de ce seul nom, nous nous sommes demandé si, forts de la littérature scientifique existante sur la sociologie des prénoms, il n'était pas possible de reconstruire une base de données plus intéressante. Par exemple, est-il possible de retrouver, à l'aide des prénoms et des autres sources minimales d'informations disponibles, le genre, l'âge, l'origine et éventuellement la classe sociale des individus présents dans la base de données ?

Nous pourrions résumer l'intérêt de ce projet ainsi : reconstruire une base de données **exploitable et scientifiquement pertinente** à partir d'un corpus incomplet.

## Méthodologie
Pour analyser ce corpus, nous allons construire plusieurs versions d'un même grand modèle de langage public, que nous allons _fine-tuner_ pour nos utilisations précises.

### Pour le genre
Dans le but de simplifier notre approche et de nous concentrer sur la pertinence scientifique des données construites, nous avons fait le choix de nous limiter aux deux étiquetages de genre les plus communs et fréquents dans l'analyse sociologique : celui d'« homme » et celui de « femme ».

**Modèles :**

- Un premier modèle dont le rôle est d'attribuer à chaque prénom un genre et une valeur reflétant la confiance que le modèle porte en sa prédiction.
- Un deuxième modèle s'appuyant sur les _reviews_ (conjugaison des adjectifs, façons d'écrire...) des personnes dont le score de confiance n'est pas assez élevé, pour essayer de discriminer une partie d'entre eux.
- Un troisième et dernier modèle, plus complexe, dont l'objectif est d'attribuer un genre et un score de confiance final aux données non encore discriminées. Pour ce faire, il s'appuiera sur la quantité et les types d'annonces commentées par chaque profil, qu'il comparera avec la quantité et les types d'annonces commentées en général par les hommes et les femmes (données issues du corpus construit avec l'aide des deux modèles précédents).

### Pour l'origine
_Méthodologie en cours de construction._

### Pour l'âge
_Méthodologie en cours de construction._

### Pour la classe sociale
_Méthodologie en cours de construction._
