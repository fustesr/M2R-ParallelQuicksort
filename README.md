M2R-ParallelQuicksort
=====================


_ETAPE 1_:

Les premiers tests ont été d'éxecuter le code plusieurs fois pour voir comment il se comporte sur ma machine. 
Différents tests effectués: sur secteur, hors secteur, O1, O2, O3.

Tous ces tests donne les courbes du 19 janvier qui sont tres bizarre. En effet, mon séquentiel est tres rapide suivi de la libC.
Cependant le programme lancé en parallele ne fonctionne pas du tout sur mon PC. C'est à dire qu'il est toujours plus long que le séquentiel et ce 
peut importe la taille du tableau. 

[Graphiques](data/PC-Raph_2017-01-19)
Test taille 5 valeurs par defaut en O1:
![alt text](https://github.com/fustesr/M2R-ParallelQuicksort/blob/master/data/PC-Raph_2017-01-19/measurements_14:36_wide_O1.png )
Test taille 5 valeurs par defaut en O2:
![alt text](https://github.com/fustesr/M2R-ParallelQuicksort/blob/master/data/PC-Raph_2017-01-19/measurements_15:01_wide_O2.png )
Test taille 5 valeurs par defaut en O3:
![alt text](https://github.com/fustesr/M2R-ParallelQuicksort/blob/master/data/PC-Raph_2017-01-19/measurements_15:04_wide_O3.png )
Test taille 6 valeurs par defaut en O3:
![alt text](https://github.com/fustesr/M2R-ParallelQuicksort/blob/master/data/PC-Raph_2017-01-19/measurements_16:17_wide_6valeurs_O3.png )
Test taille 7 valeurs par defaut en O3:
![alt text](https://github.com/fustesr/M2R-ParallelQuicksort/blob/master/data/PC-Raph_2017-01-19/measurements_16:17_wide_6valeurs_O3.png )

En passant par le moniteur du systeme (ainsi que la commande htop) on voit bien que les 4 coeurs (8 coeurs virtuelles) tournent à 90%  en meme temps, le probleme ne vient donc pas de la.
La raison la plus probable serait la facon dont le code est fait. Au vu des courbes, mon parallele suit la meme tendance que le sequentiel avec une perte de temps au début (création des threads). Ainsi, le code de base doit utiliser des verrous qui force tous mes threads à atteindre tant que un n'a pas fini ce qu'il doit faire. Cette version est donc extremement pas rentable sur mon ordinateur.

PS: je n'arrive pas à comprendre pourquoi les autres ne rencontre pas ce probleme?! 


_ETAPE 2: essayer de trouver la source du probleme dans le code et changer pour obtenir une version logique/normale du parallele_ :

Je n'arrive pas à trouver ...
