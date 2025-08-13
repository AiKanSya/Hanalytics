# 🌸 5 [DESCRIBING OPERATING MODES OF API ARCHITECTURES](https://learning.sap.com/learning-journeys/developing-with-sap-integration-suite/describing-operating-modes-of-api-architectures_b47895bf-cd5c-45f0-8bef-11384e978629)

> 🌺 Objectifs
>
> - [ ] Describe operating modes of API architectures

## 🌸 OPERATING MODES OF API ARCHITECTURES

### WHAT IS A REQUEST-DRIVEN ARCHITECTURE ?

> #### 🍧 [Request-Driven Architecture](../☼%20UNIT%200%20-%20Lexicon/♠%20Request-Driven%20Architecture.md)
>
> Un [Request-Driven Architecture](../☼%20UNIT%200%20-%20Lexicon/♠%20Request-Driven%20Architecture.md) est basée sur une communication directe entre un **service provider** et un **service consumer**. Cette communication est **synchrone**.

![](./assets/CLD900_U1_L5_01.png)

#### 💮 **Sample Request** :

Un exemple de **SOAP request** peut ressembler à ceci :

![](./assets/CLD900_20_U1L3_001_scr.png)

#### 💮 Sample Response :

Un exemple de **SOAP response** peut ressembler à ce qui suit :

![](./assets/CLD900_20_U1L3_002_scr.png)

### EVENT-DRIVEN ARCHITECTURE

#### 💮 **What are Events** ?

> #### 🍧 Event
>
> D'un point de vue technique, un **Event** est un petit message qui fournit des informations sur un **Event commercial**. Un Event peut être, par exemple, la création d'une commande dans un système SAP S/4HANA. L'Event est déclenché via **push** de manière **asynchrone** vers un **broker**[^1].
>
> Un Event peut ressembler à ceci :
>
> ![](./assets/CLD900_20_U1L3_003_scr.png)

### EVENT PRODUCER AT SAP

SAP propose le module complémentaire _Event Enablement add-on_ dans **ECC** et **SAP S/4HANA** (**Cloud** et **On-Premise**) pour vous aider.

#### 💮 **What is an Event-Driven Architecture** ?

> #### 🍧 [Event-Driven architecture (EDA)](../☼%20UNIT%200%20-%20Lexicon/♠%20Event-Driven%20Architecture.md)
>
> Event-driven architecture (EDA) ou architecture basée sur les **Events** est un **software design pattern** (modèle de conception logicielle) dans lequel des **decoupled applications** peuvent **publish** et **subscribe** de manière **asynchrone** à des **events** via un **event broker**[^1].

> #### 🍧 [Event Broker]()
>
> Un **event broker**[^1] est un **middleware**[^2] moderne orienté **message**, par exemple **Service Mesh** chez SAP.

Pour en savoir plus, cliquez ici : [Qu'est-ce que l'EDA (Event-Driven Architecture)](https://aws.amazon.com/what-is/eda/) ?

### PULL VARIANT

![](./assets/CLD900_20_U1L3_005.png)

L'**event provider** (fournisseur d'Events) (n° 1) déclenche un **Event** (n° 2) avec une désignation appelée **Topic** (n° 3). Un **Topic** peut être, par exemple, **BusinessPartner_Changed**. Il s'agit d'une communication **asynchrone**.

Le **Topic** est abonné via une file d'attente (**subscribe** to topic). Dans ce cas, depuis la file d'attente A (n°4). Le message peut désormais être activement récupéré par l'**event consumer** (n° 5). À cet effet, l'[Event Mesh](../☼%20UNIT%200%20-%20Lexicon/♠%20Event%20Mesh.md) fournit une [API](../☼%20UNIT%200%20-%20Lexicon/♠%20API.md). La communication provient de l'**event consumer**, déclenchée par un **pull on the queue**. Il s'agit d'une communication **synchrone**.

### PUSH VARIANT

![](./assets/CLD900_20_U1L3_006.png)

L'**event provider** (n° 1) déclenche un **Event** (n° 2) avec une désignation appelée **Topic** (n° 3). Un **Topic** peut être, par exemple, **BusinessPartner_Changed**. Il s'agit d'une communication **asynchrone**.

Le **Topic** est abonné via une file d'attente (**subscribe** to topic). Dans ce cas, depuis la file d'attente B (n°4). Un **webhook**[^3] est désormais attribué à cette file d'attente. (N°5). Si un **Event** avec un **Topic** arrive dans la file d'attente correspondante, le **webhook**[^3] est appelé et l'**Event** est envoyé directement a l'**event consumer** (n°6) via **push**. La communication provient de l'[Event Mesh](../☼%20UNIT%200%20-%20Lexicon/♠%20Event%20Mesh.md), déclenchée par un **Event entrant**. Il s'agit également d'une communication **asynchrone**.

### WEBHOOKS

> #### 🍧 Webhook
>
> Un webhook est un rappel HTTP : un HTTP POST qui se produit lorsqu'un changement d'état est effectué, c'est-à-dire une notification d'Event via HTTP POST. Les webhooks sont utilisés pour les notifications en temps réel, afin que votre système puisse être mis à jour directement au moment de l'Event. En principe, un webhook est une simple URL que vous pouvez également appeler régulièrement dans le navigateur. Dans le cadre de SAP Service Mesh, l'URL du webhook est utilisée lors du subscribing (de l'abonnement). Cela permet au service de savoir où envoyer le message avec le topic to a queue.

En combinaison avec l'[Event Mesh](../☼%20UNIT%200%20-%20Lexicon/♠%20Event%20Mesh.md), une URL de **webhook**[^3] est incluse dans l'abonnement d'un **Topic** à une file d'attente.

### COMBINATION OF REQUEST-DRIVEN AND EVENT-BASED ARCHITECTURE

En réalité, les **classic requests and events** se combinent.

![](./assets/CLD900_20_U1L3_007.png)

Les numéros 1 à 6 fonctionnent comme décrit dans une section précédente, mais ce qui est nouveau, c'est que l'**event consumer** (n° 7) soumet une request à l'**event provider** (n° 1). Par exemple, pour lire les données du produit qui ont été modifiées. L'**event consumer** peut ensuite traiter l'ensemble de données.

### SUMMARY

> Il existe deux types d’exploitation de l’[approche API First](../☼%20UNIT%200%20-%20Lexicon/♠%20API%20First%20Approach.md).
>
> Le request-driven est basé sur une communication synchrone des partenaires impliqués.
>
> L'event-driven, fonctionne de manière asynchrone et découple l'émetteur (transmitter) du récepteur (receiver) en termes de temps et de contenu. Cet loose coupling (accouplement libre) offre de nombreux avantages. Les deux types sont souvent utilisés l’un après l’autre.

---

[^1]: un broker est une composante clé qui joue le rôle d'intermédiaire dans le traitement, le routage et la distribution des événements entre les différents provider et consumer. Il s'agit généralement d'une infrastructure de messagerie qui facilite la communication asynchrone et découple les parties d'un système pour améliorer sa modularité, sa résilience et sa scalabilité.
[^2]: Un middleware est une couche intermédiaire qui agit comme un "pont" ou un "filtre" entre deux parties d'une application ou entre une application et une requête entrante. Son rôle est de traiter, modifier ou contrôler les données qui passent à travers lui, avant qu'elles n'atteignent leur destination.
[^3]: Un webhook est un mécanisme qui permet à une application d'envoyer automatiquement des informations à une autre application dès qu'un événement spécifique se produit. Plutôt que de demander régulièrement des mises à jour (comme une "question-réponse"), le webhook agit comme un "post-it" envoyé spontanément quand quelque chose d'important arrive.
