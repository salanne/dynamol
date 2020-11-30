## TP 1: Premiers pas de dynamique moléculaire

Le notebook `dynamol.ipynb` est disponible sur GitHub à l'[adresse suivante](https://github.com/salanne/dynamol). GitHub est le service web d'hébergement et de développement de logiciels le plus utilisé à l'heure actuelle. Il permet notamment à plusieurs développeurs de travailler en parallèle sans avoir à se soucier des modifications réalisées par les autres, ainsi que d'avoir un suivi de version très efficace. `dynamol.ipynb` est disponible sous une licence publique générale, ce qui signifie que tout le monde est libre de l'utiliser, le modifier et de le diffuser.

Vous pouvez télécharger directement le notebook sur votre ordinateur si vous avez installé [Jupyter](https://jupyter.org/). Sinon, il est possible de le lancer en ligne [à cette adresse](https://mybinder.org/v2/gh/salanne/dynamol/main) -- il faut généralement attendre une ou deux minutes pour le chargement. Dans ce cas le programme tournera sur un ordinateur distant. 

`dynamol.ipynb` permet d'effectuer des simulations de dynamique moléculaire d'un système monoatomique dans l'ensemble thermodynamique microcanonique (nombre d'atomes, volume et énergie constants). Il utilise l'algorithme de [Verlet-vitesse](https://en.wikipedia.org/wiki/Verlet_integration#Velocity_Verlet) pour intégrer les équations du mouvement. Les interactions entre les atomes sont représentées par un potentiel de [Lennard-Jones](https://fr.wikipedia.org/wiki/Potentiel_de_Lennard-Jones).

Le notebook comporte quatre parties:
- Saisie des différents paramètres de simulation
- Des fonctions (au nombre de 11) qui réalisent les différentes opérations utilisées au cours de la simulation
- Le coeur du programme qui appelle les différentes fonctions pour calculer la trajectoire des atomes et accumuler plusieurs quantités physiques du système :
  - L'énergie totale ainsi que sa décomposition en énergie potentielle et en énergie cinétique : 
  - La température 
  - La pression 
  - La [fonction de distribution radiale](https://fr.wikipedia.org/wiki/Fonction_de_distribution_radiale) 
- Quelques exemples de visualisations de ces quantités

Le nombre d'atomes est pour l'instant fixé à 108 (ce nombre est un peu petit mais la faible efficacité du programme en Python ne permet pas de simuler plus d'atomes dans des temps raisonnables ; à titre d'exemple le même programme écrit en Fortran ou en C sera 100 fois plus rapide à executer). Au démarrage de la simulation, ils sont répartis sur les noeuds d'une maille cubique à faces centrées. En revanche de nombreux paramètres sont modifiables:
- Les paramètres du potentiel de Lennard-Jones ainsi que la masse atomique des atomes, qui sont par défaut ceux de l'argon
- La longueur de la boite cubique (et donc son volume)
- Le pas de temps de la simulation
- Le nombre de pas total
- La température d'équilibration, ainsi que le nombre de pas pendant lesquels cette température est maintenue

Au cours de cette première séance nous allons étudier les effets de l'équilibration et du choix du pas de temps. Pour cela, nous allons réaliser les simulations suivantes:
