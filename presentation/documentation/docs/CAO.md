# Carte Électronique
## **Conception et Tests**

Après avoir testé individuellement chaque composant de la carte, nous avons constaté que les valeurs fournies par la thermistance sont faibles et perturbées.

Pour résoudre ce problème et garantir une précision optimale, nous utilisons un amplificateur différentiel AD623, qui ajuste, amplifie et stabilise le signal avant son envoi vers la carte STM32 pour traitement.

Dans un premier temps, le câblage a été réalisé sur une **plaque Labdec** pour vérifier la fonctionnalité de chaque composant. Une fois les tests validés, nous avons procédé à la **conception assistée par ordinateur (CAO)** du circuit électronique en utilisant un logiciel dédié, ce qui a permis de finaliser la carte PCB présentée en image ci-dessous.

## **Schéma PCB**
![brd final](/images/brd_final.png) 

## Description du Circuit

La carte électronique exploite plusieurs composants essentiels pour la réalisation du projet d’asservissement de température :

### 1. **Pont de Wheatstone**  
Le circuit utilise une configuration en **pont de Wheatstone** pour mesurer les faibles variations de résistance de la thermistance. La sortie du pont fournit une tension proportionnelle à la variation de température, exprimée par la relation suivante :  

Vm = (ΔR / R) * Ve

Cependant, la tension obtenue est faible et sensible aux perturbations.

### 2. **Amplification du Signal**  
Afin d'améliorer la précision des mesures et réduire l'impact du bruit observé lors des tests initiaux, nous utilisons un **amplificateur différentiel AD623**. Cet amplificateur permet d’ajuster, stabiliser et amplifier le signal provenant du pont de Wheatstone avant son envoi vers la carte **STM32** pour traitement numérique.

### 3. **Connectivité et Contrôle**  
- **STM32** : La carte STM32 joue un rôle central dans l'acquisition et le traitement des données.  
- **Connectique** : La carte intègre une connectivité facilitant l’interaction avec d’autres composants, tels que le ventilateur pour la convection forcée.

## Réalisation Finale

L’image présentée illustre la carte PCB finale, incluant :  
- Les connexions avec les jauges de déformation et la thermistance,  
- Le pont de Wheatstone pour la mesure des résistances,  
- L’amplificateur **AD623** pour la stabilisation et l’amplification du signal,  
- Les ports de connexion **STM32** pour le traitement numérique et les actions correctives.

Cette carte représente une solution optimisée pour le projet d’asservissement de température, permettant d'obtenir des résultats précis tout en minimisant le bruit et les perturbations.  

