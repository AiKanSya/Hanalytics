# 🌸 API CONSUMER

## EN RESUME

> 🌺 Un API Consumer est une application ou un système qui consomme les services ou données exposés par une API. Dans SAP CPI, il peut s'agir d'une intégration consommant des APIs externes ou d'applications externes consommant des APIs exposées par CPI. L’API Consumer est une composante essentielle pour établir des connexions dans une architecture distribuée.

## DEFINITION

> #### 🍧 `API Consumer`
>
> Un API Consumer est une application, un système ou un service qui envoie des requêtes à une API pour accéder à des données ou exécuter des opérations sur un autre système. Contrairement à l’[API Provider](../☼%20UNIT%200%20-%20Lexicon/♠%20API%20Provider.md) (qui expose l’API), l’API Consumer est l'entité qui consomme les services ou les données fournis par cette API.
>
> Exemple concret :
>
> - Une application mobile qui affiche des informations météorologiques agit comme un API Consumer lorsqu’elle interroge une API pour obtenir les prévisions.
>
> - Dans le cadre de SAP CPI, un système externe pourrait consommer une API REST exposée par CPI pour obtenir des informations sur les commandes ou les clients.

## ROLE ET RESPONSABILITES D'UN D'UN API CONSUMER

### 💮 Envoyer des requêtes API :

L’API Consumer envoie des requêtes HTTP ou SOAP aux endpoints de l’[API Provider](../☼%20UNIT%200%20-%20Lexicon/♠%20API%20Provider.md), en spécifiant l’action désirée (récupération de données, mise à jour, suppression, etc.).

### 💮 Traiter les réponses API :

L’API Consumer interprète et utilise les données ou statuts reçus en réponse aux requêtes API (souvent au format JSON ou XML).

### 💮 Respecter les contrats API :

L’API Consumer doit se conformer à la documentation et aux spécifications de l’API, comme les paramètres requis, les formats de données attendus, et les règles de sécurité.

### 💮 Gérer les erreurs :

Il doit être capable de gérer les codes d’erreur ou d’exception retournés par l’API (par exemple, 404 pour une ressource introuvable ou 500 pour une erreur serveur).

### 💮 Authentification et sécurité :

L'API Consumer doit fournir les informations d'authentification requises par l’[API Provider](../☼%20UNIT%200%20-%20Lexicon/♠%20API%20Provider.md) (par exemple, des jetons OAuth2, des clés API ou des certificats).

## API CONSUMER DANS LE CONTEXTE DE SAP CPI

Dans SAP CPI, un API Consumer peut être :

- Une application ou un système externe qui consomme les APIs exposées par SAP CPI.

- Une intégration ou un processus CPI qui consomme une API externe pour exécuter des opérations ou récupérer des données.

Exemple d’utilisation :

- Consommation d’APIs externes : Un processus SAP CPI peut agir en tant qu’API Consumer pour appeler une API tierce, comme une API de livraison (par exemple, DHL ou FedEx), afin de suivre un colis.

- Consommation des APIs SAP : Une application mobile ou un système CRM externe peut consommer une API exposée par SAP CPI pour interagir avec SAP S/4HANA ou d’autres systèmes SAP.

## EXEMPLE DE FLUX AVEC UN API CONSUMER

Scénario :

Un système CRM externe consomme une API SAP CPI pour récupérer des informations clients.

1. Requête envoyée par l’API Consumer :

   Le CRM envoie une requête GET à l’API exposée par SAP CPI avec un endpoint comme :
   https://sap-cpi.example.com/api/customers/{id}.

2. Authentification et autorisation :

   Le CRM fournit un jeton OAuth2 pour s'authentifier auprès de SAP CPI.

3. Traitement de la requête dans SAP CPI :

   SAP CPI reçoit la requête, l’interprète, et interagit avec SAP S/4HANA pour récupérer les données du client correspondant.

4. Réponse de l’API :

   SAP CPI retourne une réponse JSON avec les informations du client que le CRM peut afficher ou utiliser.

## COMPOSANTS CLES POUR UN API CONSUMER

### 💮 Endpoints API :

L’API Consumer doit connaître les endpoints de l’API à interroger.

### 💮 Méthodes HTTP :

Les requêtes peuvent inclure :

- GET : Pour récupérer des données.

- POST : Pour créer une nouvelle ressource.

- PUT : Pour mettre à jour une ressource existante.

- DELETE : Pour supprimer une ressource.

### 💮 Authentification :

Les [API Providers](../☼%20UNIT%200%20-%20Lexicon/♠%20API%20Provider.md) exigent souvent une authentification. Les API Consumers doivent fournir :

- Des clés API.

- Des jetons OAuth2.

- Des certificats SSL/TLS.

### 💮 Gestion des erreurs :

Les API Consumers doivent gérer les erreurs, comme :

- 401 Unauthorized : Mauvaise authentification.

- 404 Not Found : Endpoint incorrect ou ressource introuvable.

- 500 Internal Server Error : Erreur côté [API Provider](../☼%20UNIT%200%20-%20Lexicon/♠%20API%20Provider.md).

### 💮 Transformation des données :

Les données reçues d’une API doivent parfois être transformées pour être intégrées dans le système consommateur.

## AVANTAGES POUR L'API CONSUMER

### 💮 Accès aux données :

L’API Consumer peut accéder à des ressources ou des fonctionnalités sans connaître les détails internes du système sous-jacent.

### 💮 Interopérabilité :

Il permet de connecter des systèmes hétérogènes via des standards comme REST, SOAP, ou OData.

### 💮 Automatisation des processus :

Les API Consumers automatisent l’échange de données entre les systèmes, réduisant ainsi les tâches manuelles.

### 💮 Flexibilité et évolutivité :

Les API Consumers peuvent consommer de nouvelles APIs ou ajouter des fonctionnalités en fonction des besoins métiers.

## EXEMPLE PRATIQUE

Etapes de configuration d’un API Consumer dans SAP CPI :

1. Créer un artefact d'intégration dans SAP CPI :

   Par exemple, un artefact de type "HTTP Receiver" pour appeler une API externe.

2. Configurer l'endpoint API :

   Spécifier l'URL de l'API à consommer (endpoint de l’[API Provider](../☼%20UNIT%200%20-%20Lexicon/♠%20API%20Provider.md)).

3. Configurer l'authentification :

   Ajouter les informations d’authentification (jeton OAuth2, clé API, etc.).

4. Ajouter une logique d’intégration :

   Configurer les mappings ou transformations nécessaires entre les données source et cible.

5. Tester et déployer :

   Exécuter des tests pour vérifier que l’API Consumer interagit correctement avec l’[API Provider](../☼%20UNIT%200%20-%20Lexicon/♠%20API%20Provider.md).
