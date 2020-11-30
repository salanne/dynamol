## TP 1 : Premiers pas de dynamique moléculaire

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
- Le pas de temps de la simulation `Timestep_fs` (en femtosecondes) 
- Le nombre de pas total `Nsteps`
- La température d'équilibration `Temperature_imposed` (en K), ainsi que le nombre de pas pendant lesquels cette température est maintenue `Nequil`

Au cours de cette première séance nous étudierons les effets de l'équilibration et du choix du pas de temps. Dans un premier temps, nous utiliserons les paramètres par défaut (`Timestep_fs` = 5.0, `Nsteps` = 5000, `Temperature_imposed` = 120 & `Nequil` = 1000). Pour que la simulation démarre correctement, il faut bien exécuter toutes les cellules du notebook ; lorsque le programme principal est lancé cela prend quelques minutes. À la fin de la simulation, tracer les différentes énergies et la température. Qu'observez-vous?

En zoomant sur les différentes courbes d'énergie à partir du 1001ème pas (c'est-à-dire après `Nequil`, en utilisant par exemple `total_energy[Nwrite_physical_properties_equil:]` pour l'énergie totale), vous pourrez vérifier que l'énergie totale est conservée, et donc que les fluctuations d'énergie potentielle sont exactement compensées par les fluctuations d'énergie cinétique dans l'ensemble micro-canonique (pour visualiser les trois énergies à la même échelle, vous pouvez utiliser la fonction `np.mean` de la bibliothèque `numpy`). Il est également possible d'évaluer de manière quantitative les fluctuations à l'aide de la variance, donnée par la fonction `np.var`. 
 
Afin d'observer l'impact de la période d'équilibration, redémarrer la simulation en fixant cette fois `Nequil` à 0 (vous pouvez mettre `Nsteps` = 1000 pour gagner du temps). Que se passe-t-il?

Nous allons maintenant augmenter le pas de temps de la simulation ; les nombres de pas sont alors réduits en conséquence: 
- `Timestep_fs` = 10.0, `Nsteps` = 2500, `Temperature_imposed` = 120 & `Nequil` = 500
- `Timestep_fs` = 20.0, `Nsteps` = 1250, `Temperature_imposed` = 120 & `Nequil` = 250
- `Timestep_fs` = 50.0, `Nsteps` =  500, `Temperature_imposed` = 120 & `Nequil` = 100
- `Timestep_fs` = 100.0, `Nsteps` = 250, `Temperature_imposed` = 120 & `Nequil` = 50

Effectuer les mêmes analyses que précédemment. Qu'en déduisez-vous?



