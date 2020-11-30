## TP 1: Premiers pas de dynamique moléculaire

Le notebook `dynamol.ipynb` est disponible sur GitHub à l'[adresse suivante](https://github.com/salanne/dynamol). GitHub est le service web d'hébergement et de développement de logiciels le plus utilisé à l'heure actuelle. Il permet notamment à plusieurs développeurs de travailler en parallèle sans avoir à se soucier des modifications réalisées par les autres, ainsi que d'avoir un suivi de version très efficace. `dynamol.ipynb` est disponible sous une licence publique générale, ce qui signifie que tout le monde est libre de l'utiliser, le modifier et de le diffuser.

Vous pouvez télécharger directement le notebook sur votre ordinateur si vous avez installé [Jupyter](https://jupyter.org/). Sinon, il est possible de le lancer en ligne [à cette adresse](https://mybinder.org/v2/gh/salanne/dynamol/main) -- il faut généralement attendre une ou deux minutes pour le chargement. Dans ce cas le programme tournera sur un ordinateur distant. 

`dynamol.ipynb` permet d'effectuer des simulations de dynamique moléculaire d'un système monoatomique dans l'ensemble thermodynamique microcanonique (nombre d'atomes $N$, volume $V$ et énergie $E$ constants). Il utilise l'algorithme de [Verlet-vitesse](https://en.wikipedia.org/wiki/Verlet_integration#Velocity_Verlet) pour intégrer les équations du mouvement. Les interactions entre les atomes sont représentées par un potentiel de [Lennard-Jones](https://fr.wikipedia.org/wiki/Potentiel_de_Lennard-Jones),

$$
V_{LJ}(r) = 4\epsilon \left[ \left(\frac{\sigma}{r}\right)^{12}-\left(\frac{\sigma}{r}\right)^6 \right]
$$

où $r$ est la distance entre deux atomes. $\epsilon$ et $\sigma$ sont deux paramètres qui définissent l'intensité et la portée des interactions.

Le notebook comporte quatre parties:
- Saisie des différents paramètres de simulation
- Des fonctions (au nombre de 11) qui réalisent les différentes opérations utilisées au cours de la simulation
- Le coeur du programme qui appelle les différentes fonctions pour calculer la trajectoire des atomes et accumuler plusieurs quantités physiques du système :
  - L'énergie totale $E_T$ ainsi que sa décomposition en énergie potentielle $E_P$ et en énergie cinétique $E_K$ : 
  $$
  E & = & E_P + E_K \\
  E_P & = & \sum_i \sum_{j>i} 4\epsilon \left[ \left(\frac{\sigma}{r_{ij}}\right)^{12}-\left(\frac{\sigma}{r_{ij}}\right)^6 \right]\\
  E_K & = & \sum_i \frac{1}{2}m v_i^2
  $$
  - La température 
  - La pression 
  - La fonction de distribution radiale 
- Quelques exemples de visualisat
