# 🌸 6 [EDITING APIS](https://learning.sap.com/learning-journeys/developing-with-sap-integration-suite/editing-apis_c1f6b231-83bf-47aa-bf2d-06b633ba1e4b)

> 🌺 Objectifs
>
> - [ ] Edit APIs

## 🌸 EDIT AN API

### EXPLORE THE API VIEW

Lorsque vous créez et déployez une [API](../☼%20UNIT%200%20-%20Lexicon/♠%20API.md), elle s'affiche dans l'**API view**. Voici l'exemple de l'API _GWSAMPLE_BASIC_.

![](./assets/CLD900_U3_L6_01.png)

Les domaines suivants sont marked pour être examinés plus en détail dans la liste suivante :

N°1 : _URL API_ – _Proxy URL_

N°2 : _Navigation Tabs_

N°3 : _Notification area_

### EXPLORE THE NOTIFICATION AREA (N°3)

Sur le panneau de droite, vous trouvez l'**API Health**, les **active calls** effectués et les informations d'utilisation associées à l'API.

Comme nous n’avons pas encore utilisé cette [API](../☼%20UNIT%200%20-%20Lexicon/♠%20API.md), aucune information d’utilisation n’est disponible.

![](./assets/CLD900_U3_L6_02.png)

### API URL - PROXY URL (N°1)

Au n°1, vous pouvez voir la nouvelle **URL** (_URL proxy_) avec laquelle vous pouvez désormais appeler l'**original source API**. L'**URL** est composée des éléments suivants :

- *URL de l'API* : https://group-cld900-d052537.prod01.apimanagement.eu10.hana.ondemand.com:443/GWSAMPLE_BASIC

- _Application protocol_: https

- _Virtual Host_: group-cld900-d052537

- _API Host_: prod01.apimanagement.eu10.hana.ondemand.com

- _API Port_: 443

- _API Name_: GWSAMPLE_BASIC

#### 💮 **Virtual Host** :

Le **Virtual Host** a été créé lors du **provisioning of API management** et peut être modifié à tout moment en utilisant [Settings] → [API]. Vérifiez et voyez votre _Host Alias name_.

![](./assets/CLD900_U3_L6_03.png)

#### 💮 **API Host** :

Cela dépend de votre **subaccount**. Il peut également s'agir de votre propre **nom de domaine** personnalisé.

### NAVIGATION TAB (N° 2)

Il existe cinq onglets portant les noms suivants :

- _Overview_

- _Proxy Endpoint_[^1]

- _Target EndPoint_[^2]

- _Resources_

- _Revisions_

![](./assets/CLD900_U3_L6_04.png)

#### 💮 TAB 1: **Overview** :

Dans cet onglet **Overview**, vous trouverez toutes les informations importantes sur votre **API**.

Ceux-ci sont les suivants :

- _Title_

- _Host Alias_, that is the _host_ from your _Proxy URL_ on top of this page

- _API Base Path_

- _API State_ (Active, Alpha, Beta, Deprecated, Decommissioned)

- _Description_

![](./assets/CLD900_U3_L6_05.png)

Au bas de l'interface, il y a une **Product Associated area**. Plus tard, nous créons un **product** basé sur notre [API](../☼%20UNIT%200%20-%20Lexicon/♠%20API.md). Chaque entrée peut être modifiée.

#### 💮 TAB 2 : **Proxy EndPoint** :

Ici, vous pouvez ajouter des **Proxy Endpoint Properties** et des **Route Rules**.

En savoir plus ici : [Structure du proxy API](https://help.sap.com/docs/SAP_CLOUD_PLATFORM_API_MANAGEMENT/66d066d903c2473f81ec33acfe2ccdb4/4dfd54a7546c42cfb8dd157ab1355011.html?locale=en-US)

#### 💮 TAB 3 : **Target EndPoint** :

![](./assets/CLD900_U3_L6_06.png)

Ici, vous trouvez l'[API Provider](../☼%20UNIT%200%20-%20Lexicon/♠%20API%20Provider.md) configuré ou l'**URL**.

Dans ce cas, nous voyons le _SAPGatewayDemoSystemES5_Provider_. Il est également possible d’utiliser le **Load Balancing**[^3].

#### 💮 TAB 4 : **Resources** :

C'est le domaine le plus important d'une [API](../☼%20UNIT%200%20-%20Lexicon/♠%20API.md). Il montre avec une interface utilisateur **Swagger** tous les **resource paths** possibles et les actions **REST** (GET, PUT, DELETE..) avec tous les **paramètres** nécessaires.

La figure suivante nous donne l'exemple d'un **resource path**, _/ProductSet_, et de l'action _REST GET_ avec des paramètres de requête prédéfinis.

![](./assets/CLD900_U3_L6_07.png)

### WHERE DO THESE ENTRIES IN THIS TAB COME FROM?

Lors de la création d'[API](../☼%20UNIT%200%20-%20Lexicon/♠%20API.md) pour **SOAP** et **REST**, les **API resources** ne sont pas générées automatiquement ; vous devez les ajouter manuellement.

Lors de la création de l'[API](../☼%20UNIT%200%20-%20Lexicon/♠%20API.md) pour **ODataAPI**, la **génération automatique de ressources** peut être **possible** dans **certains cas**.
C'est le cas si vous utilisez un [API Provider](../☼%20UNIT%200%20-%20Lexicon/♠%20API%20Provider.md) de **type On-Premise** avec **backend SAP** ou de **type Open Connectors**.

La visualisation des **ressources** est réalisée par l'implémentation de **Swagger UI**. Il interprète la spécification **openAPI** de cette [API](../☼%20UNIT%200%20-%20Lexicon/♠%20API.md).

#### 💮 TAB 5 : **Revisions** :

Avec l'**API revisions**, vous pouvez apporter des **incremental changes** à un [API proxy](../☼%20UNIT%200%20-%20Lexicon/♠%20API%20Proxy.md) sans perturber l'[API](../☼%20UNIT%200%20-%20Lexicon/♠%20API.md) déployée. Vous pouvez accéder aux modifications précédentes apportées a l'[API proxy](../☼%20UNIT%200%20-%20Lexicon/♠%20API%20Proxy.md) et même restaurer l'[API](../☼%20UNIT%200%20-%20Lexicon/♠%20API.md) à l'un de ses **earlier states**.

Les **révisions** consistent généralement en de **petites modifications incremental** et **compatibles**, telles que l'**ajout d'une propriété**, d'une **nouvelle ressource** ou d'une **stratégie** à un [API proxy](../☼%20UNIT%200%20-%20Lexicon/♠%20API%20Proxy.md).

Des **révisions** sont créées lorsque les changements ne perturbent pas les **consumption flows existants**. Ils sont **indépendants de l’URL réelle utilisée** pour **consuming** the API. Étant donné que la révision déployée est celle qui est consommée, il n'est pas nécessaire d'y accéder séparément. L'**URL** de l'[API proxy](../☼%20UNIT%200%20-%20Lexicon/♠%20API%20Proxy.md) reste cohérente dans les différentes révisions.

Une seule révision d'un [API proxy](../☼%20UNIT%200%20-%20Lexicon/♠%20API%20Proxy.md) existe dans **runtime environment** (l'environnement d'exécution). Lors de la **phase de design**, vous pouvez **visualiser** et **comparer** le contenu des différentes **révisions**.

Pour plus d'informations sur la **création d'API Revisions**, visitez le site Web help.sap.com : [Création de révisions d'API | Portail d'aide SAP](https://help.sap.com/docs/sap-api-management/sap-api-management-for-neo-environment/creating-api-revisions?version=Cloud&q=Resivions%20APi%20proxy)

![](./assets/CLD900_U3_L6_08.png)

### CREATE OR EDIT AN API FROM THE API DESIGNER

Puisqu'il n'est **pas toujours possible de générer** automatiquement les **ressources**, **SAP API Management** vous offre également la possibilité de le faire **manuellement**. Les **ressources** visualisent la spécification **openAPI** créée dans [API Designer](../☼%20UNIT%200%20-%20Lexicon/♠%20API%20Designer.md).

### PROCEDURE FOR CREATING AN API

Dans la [Configure view] de vos [API](../☼%20UNIT%200%20-%20Lexicon/♠%20API.md), choisissez le lien [Create in API Designer] pour ouvrir [API Designer]. Vous trouverez un modèle de démarrage simple en **YAML**.

![](./assets/CLD900_20_U3L6_008_scr.png)

Vous pouvez maintenant commencer à écrire votre propre **spécification openAPI**.

Pour modifier une **spécification openAPI**, vous utilisez le même éditeur. Vous pouvez également utiliser d'autres éditeurs, tels que des IDE, Visual Code et autres, et y copier le résultat.

### RESOURCES

Vous trouvez toute la documentation openAPI ici :

- [Spécification OpenAPI](https://github.com/OAI/OpenAPI-Specification/blob/main/versions/2.0.md#schemaObject)

- [Créer une API à partir d'[API Designer](../☼%20UNIT%200%20-%20Lexicon/♠%20API%20Designer.md)](https://help.sap.com/docs/SAP_CLOUD_PLATFORM_API_MANAGEMENT/66d066d903c2473f81ec33acfe2ccdb4/26e1bbd2f3864b53a288e25786eb94e0.html?locale=en-US)

- https://swagger.io/docs/spécification/about/

- Portail d'aide : [Modifier un proxy d'API](https://help.sap.com/docs/SAP_CLOUD_PLATFORM_API_MANAGEMENT/66d066d903c2473f81ec33acfe2ccdb4/a64b952578f84161829439c3ee6e967b.html?locale=en-US)

### SUMMARY

> L'**URL du proxy** est la **nouvelle URL** qui **ultimately consume the resource API**.
>
> Le nom de **Virtual Host** est défini par vous. Il est utilisé comme **API host** (_URL proxy API_) dans le **subaccount**.
>
> Il peut également y avoir un **custom domain** ici. **SAP API Management** propose différents onglets avec différentes fonctionnalités dans [View API]. L'onglet [Ressources] est le plus important. Les **ressources** décrivent les **fonctionnalités REST** (GET, POST, etc.) et les **paths** aux données réelles (/ProductSet, /BusinessPartnerSet...).
>
> La **description** est basée sur la **spécification openAPI**.
>
> La **visualisation** de la **spécification openAPI** est réalisée avec l'**interface utilisateur Swagger**. L'interface utilisateur Swagger est un **framework JavaScript open source** permettant de rendre les **API tangibles**.

## 🌸 EXPLORE THE [API DESIGNER](../☼%20UNIT%200%20-%20Lexicon/♠%20API%20Designer.md)

[Exercices](https://learning.sap.com/learning-journeys/developing-with-sap-integration-suite/editing-apis_c1f6b231-83bf-47aa-bf2d-06b633ba1e4b)

---

[^1]: Un Proxy Endpoint dans le contexte de SAP Cloud Platform Integration (CPI) fait référence à un point d'entrée d'API qui permet de recevoir les requêtes externes (de clients ou d'autres systèmes) et de les acheminer vers des processus d'intégration en arrière-plan. C'est essentiellement une interface d'API exposée qui agit comme un intermédiaire entre le client et les services internes ou les systèmes backend.
[^2]: Un Target Endpoint dans le contexte de SAP Cloud Platform Integration (CPI) fait référence à un point de sortie ou un point d'accès vers un service backend auquel une requête est dirigée après avoir été traitée par le Proxy Endpoint.
[^3]: Le Load Balancing (répartition de charge en français) est une technique utilisée pour répartir de manière équitable le trafic réseau ou les charges de travail entre plusieurs serveurs, ressources ou services, afin d'optimiser la performance, la disponibilité et la scalabilité d'un système. Cette approche permet de s'assurer qu'aucun serveur ou ressource individuelle ne soit surchargé, garantissant ainsi des performances optimales et une meilleure fiabilité du système. Dans le contexte de SAP Cloud Platform Integration (CPI), Load Balancing est utilisé pour assurer la distribution équitable des requêtes ou des transactions entre différents serveurs ou points de terminaison. Cela peut être particulièrement important dans des environnements cloud où les charges peuvent fluctuer en fonction du nombre d'utilisateurs ou des appels d'API.
