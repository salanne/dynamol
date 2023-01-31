## TP : Premiers pas de dynamique moléculaire

Le notebook `dynamol-nvt.ipynb` est disponible sur GitHub à l'[adresse suivante](https://github.com/salanne/dynamol). GitHub est le service web d'hébergement et de développement de logiciels le plus utilisé à l'heure actuelle. Il permet notamment à plusieurs développeurs de travailler en parallèle sans avoir à se soucier des modifications réalisées par les autres, ainsi que d'avoir un suivi de version très efficace. `dynamol-nvt.ipynb` est disponible sous une licence publique générale, ce qui signifie que tout le monde est libre de l'utiliser, le modifier et de le diffuser.

Vous pouvez télécharger directement le notebook sur votre ordinateur si vous avez installé [Jupyter](https://jupyter.org/). Sinon, il est possible de le lancer sur Google Colab. Dans ce cas le programme tournera sur un ordinateur distant. 

`dynamol-googlecolab.ipynb` permet d'effectuer des simulations de dynamique moléculaire d'un système monoatomique dans l'ensemble thermodynamique canonique (nombre d'atomes, volume et température constants). Il utilise l'algorithme de [Verlet-vitesse](https://en.wikipedia.org/wiki/Verlet_integration#Velocity_Verlet) pour intégrer les équations du mouvement. Les interactions entre les atomes sont représentées par un potentiel de [Lennard-Jones](https://fr.wikipedia.org/wiki/Potentiel_de_Lennard-Jones).

Le notebook comporte quatre parties:
- Saisie des différents paramètres de simulation
- Des fonctions qui réalisent les différentes opérations utilisées au cours de la simulation
- Le coeur du programme qui appelle les différentes fonctions pour calculer la trajectoire des atomes et accumuler plusieurs quantités physiques du système :
  - L'énergie totale ainsi que sa décomposition en énergie potentielle et en énergie cinétique : 
  - La température 
  - La pression 
  - La [fonction de distribution radiale](https://fr.wikipedia.org/wiki/Fonction_de_distribution_radiale) 
- Quelques exemples de visualisations de ces quantités

Le nombre d'atomes est pour l'instant fixé à 864 (ce nombre est un peu petit mais la faible efficacité du programme en Python ne permet pas de simuler plus d'atomes dans des temps raisonnables ; à titre d'exemple le même programme écrit en Fortran ou en C sera 100 fois plus rapide à executer). Au démarrage de la simulation, ils sont répartis sur les noeuds d'une maille cubique à faces centrées. En revanche de nombreux paramètres sont modifiables:
- Les paramètres du potentiel de Lennard-Jones ainsi que la masse atomique des atomes, qui sont par défaut ceux de l'argon
- La longueur de la boite cubique (et donc son volume)
- Le pas de temps de la simulation `Timestep_fs` (en femtosecondes) 
- Le nombre de pas total `Nsteps`
- La température d'équilibration `Temperature_imposed` (en K), ainsi que le nombre de pas pendant lesquels cette température est maintenue `Nequil`

Au cours de cette séance nous allons déterminer la capacité calorifique de l'argon. La capacité calorifique molaire à volume constant d'un composé, notée *Cv*, est l'énergie qu'il faut apporter à une mole de ce composé pour augmenter sa température d'un Kelvin. On peut la définir pour un système de *N* particules :

```math
Cv(T,P)=\frac{1}{N}\left(\frac{\partial U}{\partial T}\right)_V 
```

Elle peut donc être calculée par dynamique moléculaire en faisant une série de simulations dans l'ensemble *NVT* à des températures différentes et en déterminant l'énergie moyenne du système *U*. Calculer la variation de *Cv=f(T)* pour l'argon à la densité *d* = 1,428. 





