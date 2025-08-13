# 🌸 9 [USING INTEGRATION PATTERNS](https://learning.sap.com/learning-journeys/developing-with-sap-integration-suite/using-adapter-inbound-security_cae0d690-8bda-4fc5-a45f-7b24b2134d26)

> 🌺 Objectifs
>
> - [ ] Use integration patterns

## 🌸 INTEGRATION PATTERNS

### SHOW INTEGRATION PATTERNS

- [Aggregator](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/5f5e01bfa534465eab55c8751f72a5bc.html?locale=en-US)

- [Composed Message Processor](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/353a11956dbc43d8a6146330e16680e4.html?locale=en-US)

- [Content-Based Routing](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/90f35f3d4fa740a28c49ab2b85940609.html?locale=en-US)

- [Content Enricher](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/0e7ba7fc4d4b4f47ab84ad6ce0d1a8ec.html?locale=en-US)

- [Content Filter](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/6fd4a865c9f3456ea452e6b3da4715f6.html?locale=en-US)

- [Message Filter](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/bd523460894744a8be6b7bbe3351f795.html?locale=en-US)

- [Recipient List](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/06594b982e86462ab371993fb66c3a37.html?locale=en-US)

- [Resequencer](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/068cfc7cdaf54d71a51726dff203da5b.html?locale=en-US)

- [Scatter-Gather](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/987eef23b2544f79b500b4e6e3bb4616.html?locale=en-US)

- [Splitter](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/4b475eaac3de4ef1a9f434fd13cbb709.html?locale=en-US)

- [Quality of Service Exactly Once](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/f96cf276c37d424f9a5b3e63778cf0ae.html?locale=en-US)

### THE INTEGRATION PATTERNS IN DETAIL:

#### 💮 Aggregator :

Pour traiter les **related individual messages in bulk** (messages individuels associés en masse), vous pouvez utiliser un **Aggregator pattern** (modèle d'agrégateur). Ce **pattern** implique la collecte et le stockage de messages individuels jusqu'à ce qu'un **set** complet de messages associés soit reçu. Le message agrégé est ensuite envoyé au **receiver** prévu.

![](./RESSOURCES/CLD900_20_U5L9_001_scr.png)

#### 💮 Composed Message Processor :

Le **Composed Message Processor pattern** (modèle Composed Message Processor) est utile lorsque vous devez traiter un message contenant plusieurs éléments, chacun nécessitant un traitement différent. Le **pattern** implique de diviser le message en **submessage** , de **routing** (acheminer) chaque **submessage** vers une destination différente, puis de **reaggregating** les **responses** en un seul message.

![](./RESSOURCES/CLD900_20_U5L9_002_scr.png)

#### 💮 Content-Based Routing :

En supposant que vous disposez d'un **order process** (processus de commande) dans lequel l'**inventory system** qui traite l'**order** dépend du **shipping address** (l'adresse de livraison), vous pouvez utiliser le **content-based routing** (routage basé sur le contenu) pour diriger le message vers le **recipient** approprié en fonction de son contenu. Dans cet exercice, nous utilisons un **content-based router** (routeur basé sur le contenu).

Lire la suite ici :

- [Variant: Send to Default Receiver](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/7ba1864526814e72adef9c96f79d319f.html?locale=en-US)

- [Variant: Ignore](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/4998bd8aaed349c188a170e8d4eb7b63.html?locale=en-US)

- [Variant: Raise an Error](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/b1148e9eeb724c9aafa6ca25bc3c03f4.html?locale=en-US)

#### 💮 Content Enricher :

Supposons que vous deviez envoyer un **order** à un **supplier** (fournisseur), mais que vous ne disposiez pas de toutes les informations requises pour que le **receiver system** (système récepteur) puisse la traiter. Par exemple, les **product items** (articles du produit) n'ont qu'un **category code** et le nom de la **category name** est manquant. Dans ce cas, vous pouvez utiliser un **Content Enricher pattern** qui lit les données de manière **synchrone** à partir d'un système externe et ajoute les informations manquantes au message d'origine avant de le transmettre au **recipient** .

![](./RESSOURCES/CLD900_20_U5L9_003_scr.png)

#### 💮 Content Filter :

Supposons que vous receviez un **order** d'un **partner** dans un format standardisé avec de nombreux champs, mais que votre système backend n'en a besoin que d'une petite fraction. Vous disposez de deux options pour mettre en œuvre ce scénario :

- Using a **Filter step**.

- Using **Message Mapping**.

Lire la suite ici :

- [Variant: Content Filter Step](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/239d8f86f2e64a3c998b4c2d8ede52ce.html?locale=en-US)

- [Variant: Message Mapping](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/85571e200d514723a9e4b552db2ccf7a.html?locale=en-US)

#### 💮 Message Filter :

Vous pouvez implémenter le **Message Filter pattern** (modèle de filtre de messages) pour supprimer les données indésirables d'un canal. Par exemple, si vous devez envoyer des informations sur les produits à un **inventory system** (système d'inventaire), mais que l'**inventory system** ne gère qu'une **specific range** de produits en fonction de la **product category**, vous pouvez appliquer un **Message Filter** pour supprimer toutes les données non pertinentes. Le **Message Filter** est un **subtype** du **Message Router pattern** (modèle Message Router), avec un seul **receiver channel** (canal de réception). Il évalue les **incoming messages** et les achemine vers le **receiver channel** (canal récepteur) uniquement s'ils répondent aux** specified criteria** (critères spécifiés) ; sinon, ils sont **discarded** (rejetés).

![](./RESSOURCES/CLD900_20_U5L9_004_scr.png)

#### 💮 Recipient List :

Supposons que vous souhaitiez trouver le **best quote** (meilleur devis) pour un **order** en l’envoyant à plusieurs **suppliers**, mais que tous les **suppliers** ne soient pas pertinents pour chaque produit de la commande. Dans ce cas, les **suppliers** qui doivent recevoir la commande sont déterminés dynamiquement en fonction des produits spécifiques commandés. Pour y parvenir, vous pouvez utiliser le **Dynamic Router pattern** (modèle Dynamic Router), qui envoie une copie du message à plusieurs **receivers** en fonction des **dynamically determined criteria**. Contrairement au **content-based router** (routeur basé sur le contenu), qui transmet le message original à un seul **receiver**, le **dynamic router** envoie une copie du message à plusieurs **receivers**.

Lire la suite ici :

- [Variant: Static Routing](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/b71529f0cf714cc4abda84bf607277b5.html?locale=en-US)

- [Variant: Dynamic Routing](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/d241c776e0e84368b4e37546377c5ec6.html?locale=en-US)

- [Variant: Dynamic Routing Using JMS Message Queues](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/27c247e016184cee97581fbaa53359f7.html?locale=en-US)

#### 💮 Resequencer :

Si vous devez réorganiser les messages reçus par le **Cloud Integration** dans un ordre incorrect, vous pouvez utiliser le **Aggregator pattern** (modèle Agrégateur). Ce **pattern** vous permet de rassembler des messages individuels en **batches** triés par **sequence number**. Pour transformer les **message batches** en messages séparés, vous pouvez utiliser le **Splitter pattern** et envoyer les messages individuels au **receiver** prévu.

![](./RESSOURCES/CLD900_20_U5L9_005_scr.png)

#### 💮 Scatter-Gather :

Le **Scatter-Gather pattern** vous permet d'envoyer un message à plusieurs **receivers** et de collecter leurs **replies**. En diffusant un message à plusieurs **receivers**, le **pattern** permet un **parallel processing** (traitement parallèle) du message par tous les **receivers**. Après avoir reçu les **replies**, le **pattern** les réagrège en un seul message.

![](./RESSOURCES/CLD900_20_U5L9_006_scr.png)

#### 💮 Splitter :

Le **Splitter pattern** peut être utilisé lorsqu'un message contient plusieurs éléments nécessitant un traitement différent. Le **pattern** peut **break up** (diviser) le message en messages individuels en fonction du nombre d'éléments. Cependant, dans l’exercice donné, le **Splitter pattern** n’est pas utilisé.

Une distinction est faite entre les cas d'utilisation suivants :

- **Splitting a bulk order message** (Diviser un message de commande groupée) en plusieurs commandes.

- Fractionner une seule commande avec plusieurs articles.

Lire la suite ici :

- [Variant with Iterating Splitter](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/24f9f29ad45849af978c17de4789842a.html?locale=en-US)

- [Variant with General Splitter](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/cba1ecb0f88a4a3c862c3cadd0403f6e.html?locale=en-US)

- [Variant with Message Mapping](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/f6bb2b7d6860418bbe4c0c40e5cacecd.html?locale=en-US)

### QUALITY OF SERVICE EXACTLY ONCE

Vous voulez garantir qu'un message est **delivered** et **processed** par le **receiver** une seule fois. Cette exigence peut être satisfaite en combinant les deux **enterprise integration patterns** (modèles d'intégration d'entreprise) suivants :

#### 💮 Guaranteed Delivery :

Le **Guaranteed Delivery pattern** garantit qu'un message sera finalement **delivered** à un **receiver**, même en cas de **failures** temporaires dans le **messaging system**. Cependant, en raison de la possibilité de **redeliveries** (redistributions), ce **pattern** peut entraîner la transmission d'un message plusieurs fois.

#### 💮 Idempotent[^1] Receiver :

Le **Duplicate Message Suppression pattern** (modèle de suppression des messages en double) résout le problème de la gestion des **duplicate messages** et garantit que si un composant reçoit le même message plusieurs fois, il ne le traite qu'une seule fois.

En savoir plus ici : [Qualité de service exactement une fois](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/f96cf276c37d424f9a5b3e63778cf0ae.html?locale=en-US)

### SUMMARY

> Cette leçon décrit divers **integration patterns** (modèles d'intégration), notamment l'**Aggregator**, **Composed Message Processor**,** Content-Based Routing**, **Content Enricher**, **Content Filter**, **Message Filter**, **Recipient List**, **Resequencer**, **Scatter-Gather**, **Splitter** et le **Quality of Service Exactly Once**.

## 🌸 INSTALL EXAMPLE INTEGRATION FLOWS

[Exercices](https://learning.sap.com/learning-journeys/developing-with-sap-integration-suite/using-integration-patterns_fdd8f683-da3d-4abe-a29d-a6f6fd06cc14)

[^1]: Une méthode HTTP est idempotente si une requête identique peut être faite une ou plusieurs fois de suite avec le même effet, tout en laissant le serveur dans le même état. En d'autres termes, une méthode idempotente ne doit pas avoir d'effets secondaires (sauf dans la tenue de statistiques).
