# STM32

Avant de commencer les tâches spécifiques à notre projet, il est essentiel de configurer les broches, récupérer les tensions via l'ADC et utiliser les minuteries. Ces bases sont indispensables pour les tâches à venir dans le cadre du module IPS.

## Tâche 1 : Programmation d'une tâche périodique (1 seconde)

Nous devons configurer des minuteries pour créer des tâches périodiques sur la carte STM32.

**Objectifs :**
- **Configurer un timer** pour générer des interruptions périodiques.
- **Vérifier les périodes** avec un oscilloscope.

**Pourquoi c'est important pour le projet :**  
Cela permettra de gérer les actions périodiques et synchroniser le traitement des données.

![Tâche 1](/images/tache_1.png)

## Tâche 2 : Acquisition d'une donnée analogique via l'ADC

Nous utiliserons l'ADC pour lire une valeur analogique, puis la convertir en une tension numérique.

**Objectifs :**
- **Configurer l'ADC** pour lire la donnée analogique.
- **Convertir et afficher** la tension correspondante.

**Pourquoi c'est important pour le projet :**  
Cela permet d'acquérir des données analogiques provenant des capteurs.

![Tâche 2](/images/tache_2.png)

## Tâche 3 : Envoi des données vers le PC via UART (USB)

Nous enverrons les données acquises de la STM32 vers un PC via UART.

**Objectifs :**
- **Configurer UART** pour envoyer les données vers le PC.
- **Vérifier la transmission** avec un terminal comme PuTTY.

**Pourquoi c'est important pour le projet :**  
Cela permet de visualiser et analyser les données collectées.

![Tâche 3](/images/tache_3.png)


# Processus Expérimental du Projet STM32

Une fois les tâches de configuration de la carte STM32 terminées, nous démarrons le processus expérimental global du projet.

## 1. Câblage du Système Global

Après avoir finalisé les tâches de configuration sur la carte STM32, nous passons à l'étape suivante qui consiste à câbler l'ensemble du système.

![Câblage du système](/images/cablage.jpg)


### Étapes :
- **Câblage de la broche PA0** : Cette broche est utilisée pour récupérer la tension en sortie de l'AOP.
- **Vérification du signal** : À l'aide d'un multimètre, nous vérifions que la tension récupérée sur PA0 correspond à la tension attendue sortie de l'AOP.


## 2. Ajout d'une Broche pour la Récupération de la Sortie du Capteur de Courant

Une fois le câblage vérifié, nous ajoutons une autre broche, **PA1**, pour récupérer la sortie du capteur de courant. Cette étape est cruciale pour l'acquisition des données nécessaires à l'asservissement du système.

- **PA1** : Récupère la sortie du capteur de courant.


## 3. Mise en Place de la Tâche Périodique pour la Récupération des Données

Pour récupérer les données de manière régulière, nous configurons un timer afin de lancer la mesure périodiquement.

- **Timer périodique** : Permet de récupérer les mesures des capteurs à intervalles réguliers pour le traitement ultérieur.

## 4. Traitement des Données pour l'Asservissement

Une fois les données récupérées, nous passons à leur traitement pour calculer la température et déterminer le courant, afin de procéder à l'asservissement du système.

- **Calcul de la température** : À partir des données récupérées, la température est calculée.
- **Calcul du courant** : La mesure du courant est utilisée pour ajuster l'asservissement.

## 5. Contrôle du Signal PWM

Le traitement des données permet de déterminer le **duty cycle** du signal PWM, qui sera ensuite envoyé pour réguler la température et le courant dans l'élément chauffant.

- **PWM** : En fonction des calculs, un signal PWM est généré pour contrôler l'élément chauffant en fonction de la température et du courant mesurés.

## 6. Phase 3 : Récupération de la Consigne via USART

Dans cette phase, nous ajoutons la capacité de recevoir une consigne de température via la communication USART. Cette consigne permettra d'ajuster le comportement du système en fonction des demandes externes.

### Étapes :
- **Récupération de la consigne via USART** : Le système reçoit la consigne de température via un terminal ou une autre source, en utilisant la communication USART.
- **Modification de la consigne dans l'asservissement** : La consigne reçue via USART est utilisée pour ajuster la température cible, et donc le calcul du PWM.

## 7. Ajustement du PWM en fonction de la Consigne

Une fois la consigne reçue, le système adapte le calcul du signal PWM pour réguler la puissance envoyée à l'élément chauffant et atteindre la température cible spécifiée par la consigne.

- **Contrôle dynamique de la température** : La consigne via USART permet un contrôle dynamique et à distance de la température de l'élément chauffant, en ajustant le signal PWM en conséquence.


![Données récupérées](/images/donnees.jpg)
