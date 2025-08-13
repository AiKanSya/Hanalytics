# ♠ 🌸 [LEARNING THE BASICS](https://learning.sap.com/learning-journeys/developing-with-sap-integration-suite/learning-the-basics_ccfb5535-54c2-40d2-8249-6e3102987d30)

> 🌺 Objectifs
>
> - [ ] Create and configure a content modifier

## 🌸 HANDLE ATTACHMENTS

Dans cette leçon, vous n'utiliserez pas de **attachments**, mais vous apprendrez à les gérer efficacement dans les **integration flows**, où un fichier est spécifié dans un format tel que des fichiers texte et joint en tant que **exchange parameter**.

### READ MORE HERE:

- [Create Attachments](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/d1f16dbf415a449690bdc2452df7c3f4.html?locale=en-US)

- [Replace Body with Content of Attachment (Remplacer le corps par le contenu de la pièce jointe)](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/14e68101f5984d8a8f3ac565ba320509.html?locale=en-US)

- [Read Multiple Attachments](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/4b2f07f59590414eb597f29959c06248.html?locale=en-US)

- [Read Attachment Based on Filter Criteria](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/f7f513f915044435a269157ffa325c2c.html?locale=en-US)

- [Read Multiple Attachments Based on Filter Criteria](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/b9c2354da3bd4b029af109a0413c9be9.html?locale=en-US)

### FILE TRANSFERT

Cette leçon couvre le transfert de fichiers depuis un **serveur**, bien qu'elle n'implique pas l'utilisation de **attachments**.

### READ MORE HERE:

- [Poll File by Done File (Fichier d'interrogation par fichier terminé)](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/800de6e5bbf7422abd071e9b80016296.html?locale=en-US)

- [Poll Folder by Fixed Done File (Dossier d'interrogation par fichier terminé corrigé)](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/0041751c99dc45269597d0d1ef1e2182.html?locale=en-US)

- [Concatenating Files via Poll Enrich (Concaténation de fichiers via Poll Enrich)](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/694a60b0252d4285ad36dfcc0fabed82.html?locale=en-US)

- [Combine XML Files via Poll Enrich (Combiner des fichiers XML via Poll Enrich)](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/7b971052e46e4a1084eb5bf434a4df1e.html?locale=en-US)

- [Poll and Merge Folder (Sonder et fusionner le dossier)](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/497bf08e0bdb43018e8e861256f4e803.html?locale=en-US)

### DECOUPLE INTEGRATION FLOWS

Dans cette leçon, vous découvrirez le traitement de **decoupling** , qui implique l'**asynchronous decoupling** (découplage asynchrone) du traitement des **integration scenarios** entre l'expéditeur et l'**integration flows**.

### READ MORE HERE:

- [Decouple Sender and Flows Without Persistence (Découpler l'expéditeur et les flux sans persistance)](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/31d4dec814724e2b8b9fb7161c2c5adb.html?locale=en-US)

- [Decouple Sender and Flows Using Persistence (Découpler l'expéditeur et les flux à l'aide de la persistance)](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/c5591df1388b4cf08aa3ff9527806b70.html?locale=en-US) (en utilisant le magasin de données ou les files d'attente de messages JMS)

### DECOUPLE WITH SOAP ADAPTER

Cette leçon utilise une configuration spécifique pour le **SOAP adapter**, qui appelle l'**integration flows** de manière **asynchrone**. La configuration est la suivante :

- **Message Exchange Pattern: One-Way**.

- **Process Settings: WS Standard**.

![](./RESSOURCES/CLD900_20_U5L2_001_scr.png)

### USE CONVERTERS

Cette leçon fournit des conseils sur la façon d'effectuer une **file format conversion**, mais il est important de noter que des **convertisseurs** sont nécessaires car il n'existe pas d'**internal message format** (format de message interne) comme dans l'intégration de **processus avec le XI Message Protocol** (protocole de message XI). **XML** est le format le plus couramment utilisé car il est requis pour les **Message Mapping and XPATH operations** (opérations de mappage de messages et XPATH), ainsi que pour le **format JSON**.

### READ MORE HERE:

- [Use the CSV to XML Converter](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/7ad518d41b2f438c9696908c7e0208f9.html?locale=en-US)

- [Use the XML to CSV Converter](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/cf0acacd0d9140b3a261f86afcacbc3e.html?locale=en-US)

- [Use the JSON to XML and XML to JSON Converter](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/7c5e114c0f6d4690a2a8c25b163520d8.html?locale=en-US)

### SUMMARY

> Les **attachments** peuvent être **créées**, **modifiées** et **combinées**, tandis que les fichiers peuvent être récupérés à l'aide du **SFTP adapter** de différentes manières. Le **découplage asynchrone** des **integration flows** sépare le **call time** (temps d'appel) du **processing time** (temps de traitement). Il est également important de noter que les **formats XML ou JSON** sont nécessaires pour le **message mapping and XPATH operations** (mappage des messages et les opérations XPATH).

## 🌸 CREATE AND CONFIGURE A CONTENT MODIFIER

[Exercices](https://learning.sap.com/learning-journeys/developing-with-sap-integration-suite/learning-the-basics_ccfb5535-54c2-40d2-8249-6e3102987d30)
