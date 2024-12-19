# Simulation théorique

## **Introduction**  
L'étude repose sur **l'équation de la chaleur** avec les paramètres :  
**m** : masse | **Cp** : capacité thermique | **hc** : convection | **S** : surface | **T(t)** : température | **P(t)** : puissance | **Ta** : température ambiante.

La température est calculée via l'équation NTC :  
![Equation Chaleur](/images/equestion_chaleur.png)

Des tests de **chauffage** et de **refroidissement** sont effectués en mesurant la résistance de la thermistance à chaque instant pour en calculer la température avec l'équation suivante :  
![Equation Refroidissement](/images/equation_2.png)  
Pendant le chauffage, V = 12 V a été utilisé.

| ![Graphique 1](/images/graphe1.png) | ![Graphique 2](/images/graphe2.png) | ![Graphique 3](/images/graphe3.png) |
|-----------------------------|-----------------------------|-----------------------------|
| Graphique 1                 | Graphique 2                | Graphique 3                |

## **Estimation des paramètres**  
Nous avons utilisé l'équation de refroidissement, avec l'équation différentielle linéaire à coefficients constants, pour calculer les paramètres **m.Cp** et **hc.S**. Nous les regroupons en **a = m.Cp** et **b = hc.S** pour simplifier l'analyse.

L’équation simplifiée est :  
![Equation simplifiée](/images/equation_3.png)  
Sa solution est :  
![Equation solution](/images/equation_4.png)

Le facteur **a/b** représente la constante de temps **τ**, et avec **T(τ) = 0,63 Tfin**, nous obtenons **τ = 533.47s**.  


![Puissance](/images/graphe4.png)

Pendant le chauffage, la température tend vers 50°C, donc **δT/δt = 0**, et nous trouvons que **a = 46.67Ws/K**. Cette équation permet de modéliser la variation de température pour une puissance d'entrée fixe de 14 W et la variation de la résistance en fonction de la température.

| ![Graphique 1](/images/graphe5.png) | ![Graphique 2](/images/graphe6.png) |
|-----------------------------|-----------------------------|
| Graphique 1                 | Graphique 2                |

## **Contrôle PID**  
Une fois les paramètres obtenus, les valeurs de gain ont commencé à être testées pour effectuer un contrôle PID, obtenant finalement KP= 8.1785, KI = 0.14733 et KD = 0 (Nous avons confirmé l'obtention d'une bonne réponse sans contrôle dérivé). Le contrôle a été modélisé à partir de ces valeurs pour différentes températures de consigne.

| ![Graphique 1](/images/graphe7.png) | ![Graphique 2](/images/graphe8.png) |
|-----------------------------|-----------------------------|
| Graphique 1                 | Graphique 2                |
