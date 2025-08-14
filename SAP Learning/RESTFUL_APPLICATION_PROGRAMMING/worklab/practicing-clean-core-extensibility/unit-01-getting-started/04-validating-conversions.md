# 🌸 4 [VALIDATING THE STEPS FOR SYSTEM CONVERSIONS](https://learning.sap.com/learning-journeys/practicing-clean-core-extensibility-for-sap-s-4hana-cloud/validating-the-steps-for-system-conversions_a3d85f14-de46-4475-9b54-ab042e2d6b62)

> 🌺 Objectifs
>
> - [ ] Vous serez en mesure d'évaluer les étapes nécessaires à la réussite des conversions de systèmes

## 🌸 CONVERSION SCENARIOS

Lors d'une conversion de système, un client convertit son système SAP ERP existant en un système SAP S/4HANA sur site. Les étapes spécifiques varient selon les spécificités du système SAP ERP converti. En gros, on distingue deux scénarios :

- SAP ERP fonctionnant sur n'importe quelle base de données

- SAP ERP fonctionnant sur SAP HANA (v 1.0 ou v 2.0)

### SAP ERP RUNNING ON ANY DATABASE

Dans le premier scénario, la base de données non SAP HANA actuelle est remplacée par une base de données SAP HANA (v2.0). Ensuite, le modèle de base de données est converti de SAP ERP vers SAP S/4HANA. Enfin, une mise à niveau du code est effectuée. Le code SAP S/4HANA est installé et remplace le code SAP ERP.

### SAP ERP RUNNING ON SAP HANA (EITHER V1.0 OR 2.0)

Pour le deuxième scénario, le système SAP ERP utilisant déjà une base de données SAP HANA, la première étape consiste à vérifier si la version est SAP HANA v1.0. Si c'est le cas, la mise à niveau vers SAP HANA v2.0 est effectuée. Ensuite, la conversion du modèle de données et la mise à niveau du code sont effectuées, comme pour le premier scénario.

Il est important de noter que pour les deux scénarios, la base de données, les données et le logiciel sont convertis selon le même processus technique. Par conséquent, une seule interruption du système est nécessaire.

La vidéo suivante présente les activités pertinentes lors des phases de préparation et de réalisation :

[Référence - Link Vidéo](https://learning.sap.com/learning-journeys/practicing-clean-core-extensibility-for-sap-s-4hana-cloud/validating-the-steps-for-system-conversions_a3d85f14-de46-4475-9b54-ab042e2d6b62)
