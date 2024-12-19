# Objectifs du Projet

Notre mission lors de ce projet d'Instrumentation et Puissance des Systèmes (IPS) a été de concevoir un système d'asservissement de température pour une résistance chauffante. L'objectif principal est de mesurer et réguler précisément la température à l'aide d'une thermistance et d'un capteur de courant.

## **Objectifs Détaillés**

À partir du cahier des charges, nous nous sommes répartis les différentes tâches. L'objectif final est de :

- Concevoir un système de mesure complet permettant de relever des données telles que la température et le courant consommé par la résistance.
- Réguler la température en ajustant la puissance appliquée à la résistance chauffante via un MOSFET, en fonction des mesures effectuées.
- La mise en œuvre d’un **capteur de courant ACS712** pour surveiller la puissance consommée par la résistance chauffante.  
- Analyser les résultats obtenus pour les comparer avec les prévisions théoriques issues de l'équation de la chaleur.
- Étudier l'influence de la convection forcée en utilisant un ventilateur pour améliorer la dissipation thermique.

## **Schéma Fonctionnel**

Pour atteindre nos objectifs, nous avons établi un schéma fonctionnel décrivant le fonctionnement global du système. Ce schéma comprend :

![Schéma Fonctionnel](/images/schema_fonctionnel.png)  
