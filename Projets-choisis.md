## Projet 1 : Courbe de fusion de l'argon (basse pression) 

À l'aide de simulations dans l'ensemble *NVT*, établir la courbe de fusion *P = f(T)* de l'argon pour des pressions allant de 1 \`a 100 bars.

## Projet 2 : Courbe de fusion de l'argon (haute pression) 

À l'aide de simulations dans l'ensemble *NVT*, établir la courbe de fusion *P = f(T)* de l'argon pour des pressions allant de 100 \`a 2000 bars.

## Projet 2 bis : Courbe de fusion du krypton (haute pression) 

À l'aide de simulations dans l'ensemble *NVT*, établir la courbe de fusion *P = f(T)* du krypton pour des pressions allant de 100 \`a 2000 bars. Attention à bien changer la masse molaire et les paramètres de Lennard-Jones du krypton.

## Projet 4 : Ajustement de paramètres de Lennard-Jones sur des résultats expérimentaux

L'objectif est de déterminer les paramètres de Lennard-Jones adéquat pour le krypton en utilisant la procédure suivante:
- En se baisant sur les paramètres de l'argon et de vos connaissances, essayer d'identifier des bornes minimale et maximale pour chacun des deux paramètres
- Trouver la densité du krypton à une température et une pression donnée. Fixer le paramètre de maille du système pour que la densité soit égale à cette valeur
- Réaliser une série de simulations dans l'ensemble *NVT*, à la température choisie, en faisant varier systématiquement les paramètres de Lennard-Jones entre les bornes. Repérer quelles valeurs de paramètres permettent d'obtenir une pression correcte
- Une fois un jeu de paramètre identifié, vérifier qu'ils permettent de reproduire le bon point de fusion (en faisant maintenant varier la température à volume fixé)

## Projet 5 : Tension de surface de l'argon liquide

- Modifier le code afin de pouvoir simuler des boites non cubiques et calculer les valeurs diagonales du tenseur de pression *P_{xx}*, *P_{yy}* et *P_{zz}*
- Construire une boite contenant une tranche de vide assez épaisse selon une des trois directions (typiquement 5 fois plus épaisse que la tranche de liquide). On note *L* la longueur de la boite dans cette direction
- À l'aide de simulations dans l'ensemble *NVT*, se placer dans l'état liquide. La tension de surface est donnée par *\gamma = \frac{1}{2}L[P_{zz}-\frac{1}{2}(P_{xx}+P_{yy})]*

## Projet 6 : La vitesse du son à l'aide de vos simulations

À l'aide de simulations dans l'ensemble *NVT*, identifier et tester un protocole pour prédire la vitesse du son dans l'argon liquide

## Projet 7 : Module d'élasticité isostatique de l'argon solide

À l'aide de simulations dans l'ensemble *NVT*, calculer le module d'élasticité isostatique (bulk modulus) de l'argon solide.

## Projet 11 : Mélanges binaires

Modifier le code pour prendre en compte les systèmes binaires. En déduire l'enthalpie de mélange de l'argon et du krypton.

