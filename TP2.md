## TP 2 : Capacité calorifique de l'argon

La capacité calorifique molaire à volume constant d'un composé, notée *Cv*, est l'énergie qu'il faut apporter à une mole de ce composé pour augmenter sa température d'un Kelvin. On peut la définir pour un système de *N* particules :

```math
Cv(T,P)=\frac{1}{N}\left(\frac{\partial U}{\partial T}\right)_V 
```

Elle peut donc être calculée dans par dynamique moléculaire en faisant une série de simulations dans l'ensemble *NVT* à des températures différentes et en déterminant l'énergie moyenne du système U. Calculer la variation de *Cv=f(T)* pour l'argon à la densité *d* = 1,428. 

Rappel: Le notebook `dynamol.ipynb` est disponible sur GitHub à l'[adresse suivante](https://github.com/salanne/dynamol). Vous pouvez télécharger directement le notebook sur votre ordinateur si vous avez installé [Jupyter](https://jupyter.org/). Sinon, il est possible de le lancer en ligne [à cette adresse](https://mybinder.org/v2/gh/salanne/dynamol/main) -- il faut généralement attendre une ou deux minutes pour le chargement. Dans ce cas le programme tournera sur un ordinateur distant. 



