# 🌸 EVENT-DRIVEN ARCHITECTURE

## EN RESUME

> 🌺 L’architecture événementielle permet de construire des systèmes découplés, réactifs et scalables, où les applications interagissent en écoutant et en réagissant aux événements. Dans le contexte de SAP, des outils comme SAP Event Mesh et SAP CPI facilitent l’implémentation de cette architecture, notamment dans des environnements complexes intégrant des systèmes SAP et non-SAP.

## DEFINITION

> #### 🍧 `Event-Driven Architecture`
>
> L’Event-Driven Architecture (EDA), ou architecture orientée événements, est un style d’architecture où les systèmes et applications communiquent et réagissent en fonction des événements. Un événement est une modification d’état ou une action détectée dans un système, par exemple :
>
> - Une commande est passée.
>
> - Un produit est expédié.
>
> - Une alerte de panne est générée.
>
> Dans une architecture événementielle, les systèmes ne s’interrogent pas constamment pour vérifier si une action s’est produite ; ils écoutent et réagissent uniquement lorsqu’un événement se produit.

## COMMENT FONCTIONNE UNE ARCHITECTURE ORIENTÉE ÉVÉNEMENTS ?

Une architecture événementielle repose sur trois composants clés :

### 💮 Les Émetteurs d’événements (Event Producers) :

Ce sont les systèmes ou services qui détectent les événements et les publient. Par exemple :

- Une application de commerce électronique qui envoie un événement "Commande passée" lorsqu’un client effectue un achat.

### 💮 Les Intermédiaires d’événements (Event Brokers) :

Ils agissent comme des canaux ou des médiateurs pour transmettre les événements aux systèmes intéressés. Les intermédiaires les plus courants sont :

- Kafka,

- RabbitMQ,

- SAP Event Mesh.

### 💮 Les Consommateurs d’événements (Event Consumers) :

Ce sont les systèmes ou services qui réagissent aux événements. Par exemple :

- Un service de gestion des stocks qui réduit les quantités disponibles lorsqu’il reçoit l’événement "Commande passée".

Exemple de flux :

1. L’émetteur génère un événement : "Commande passée".

2. L’intermédiaire relaie l’événement à tous les consommateurs abonnés.

3. Les consommateurs (gestion des stocks, facturation, expédition) réagissent en conséquence.

## AVANTAGES D’UNE ARCHITECTURE ORIENTÉE ÉVÉNEMENTS

### 💮 Découplage des systèmes :

Les producteurs et les consommateurs d’événements sont indépendants. Cela signifie qu’un producteur peut publier des événements sans se soucier de savoir qui les consomme.

### 💮 Réactivité en temps réel :

Les systèmes peuvent répondre immédiatement aux événements, ce qui est idéal pour des cas d’utilisation comme :

- Les notifications en temps réel.

- Le suivi des commandes ou des livraisons.

### 💮 Scalabilité :

Avec un intermédiaire d’événements performant (comme Kafka ou SAP Event Mesh), les systèmes peuvent gérer des millions d’événements par seconde.

### 💮 Flexibilité :

Les consommateurs peuvent être ajoutés ou retirés sans perturber les producteurs. Cela facilite l’évolution des systèmes.

### 💮 Fiabilité :

Les intermédiaires d’événements garantissent souvent que les événements sont livrés de manière fiable, même en cas de panne.

## LIMITATIONS D’UNE ARCHITECTURE ORIENTÉE ÉVÉNEMENTS

### 💮 Complexité :

Une architecture événementielle est plus complexe à concevoir et à maintenir qu’une architecture traditionnelle.

### 💮 Débogage difficile :

Il peut être difficile de retracer les flux d’événements, surtout lorsque plusieurs systèmes y participent.

### 💮 Dépendance à l'intermédiaire :

Le bon fonctionnement repose fortement sur l’intermédiaire d’événements, qui devient un point critique.

## ARCHITECTURE ÉVÉNEMENTIELLE DANS LE CONTEXTE DE SAP

SAP intègre l’architecture événementielle dans plusieurs de ses solutions, notamment à travers SAP Event Mesh, un service dans SAP BTP.

### 💮 SAP Event MESH :

C’est un intermédiaire d’événements conçu pour faciliter la gestion et la diffusion des événements dans un paysage SAP et non-SAP.

- Il permet aux applications SAP S/4HANA, SAP CPI, ou même des systèmes tiers de publier et consommer des événements de manière fiable.

### 💮 Exemple avec SAP CPI :

1. Un événement "Nouvelle commande" est émis par SAP S/4HANA.

2. SAP Event Mesh relaie cet événement.

3. SAP CPI consomme cet événement pour déclencher une intégration, par exemple :

   - Envoyer la commande à un partenaire logistique.

   - Mettre à jour un système CRM.

## CAS D’UTILISATION COURANTS

### 💮 E-Commerce :

Lorsqu’un client passe une commande, un événement est envoyé pour déclencher des processus : validation de paiement, mise à jour des stocks, expédition.

### 💮 Gestion des stocks :

Les capteurs IoT envoient des événements en cas de diminution des stocks, déclenchant automatiquement une commande de réapprovisionnement.

### 💮 Finance :

Un événement "Facture générée" peut être utilisé pour notifier un client ou démarrer un processus de recouvrement.

## OUTILS COURANTS POUR UNE ARCHITECTURE ÉVÉNEMENTIELLE

### 💮 Intermédiaires open-source :

- Apache Kafka,

- RabbitMQ,

- ActiveMQ.

### 💮 Solutions cloud :

- SAP Event Mesh,

- Amazon EventBridge,

- Google Pub/Sub.

### 💮 Intégrations SAP :

SAP CPI (Cloud Platform Integration) et SAP BTP Extension Suite pour consommer ou émettre des événements.
