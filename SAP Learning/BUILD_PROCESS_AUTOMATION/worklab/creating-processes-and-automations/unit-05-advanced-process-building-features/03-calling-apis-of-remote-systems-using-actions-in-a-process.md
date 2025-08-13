# 🌸 3 [CALLING APIS OF REMOTE SYSTEMS USING ACTIONS IN A PROCESS](https://learning.sap.com/learning-journeys/create-processes-and-automations-with-sap-build-process-automation/calling-apis-of-remote-systems-using-actions-in-a-process_e33106b5-2c6e-445a-8cc6-4dc9839c1cd5)

> 🌺 Objectifs
>
> - [ ] Call remote systems APIs using actions in a process

## 🌸 CALL REMOTE SYSTEMS APIS USING ACTIONS IN A PROCESS

### BUSINESS SCENARIO

Vous et vos collègues développez un processus qui doit lire les données des commandes clients depuis votre `système SAP S/4HANA` et, ultérieurement, les réécrire dans le système. Vous êtes maintenant confronté au défi d'interagir avec ce `système SAP S/4HANA`.

Pour résoudre ce problème, `SAP Build Process Automation` propose des **projets Actions**. Vous avez déjà créé un **projet Actions** qui **encapsule** le **point de terminaison** de l'**API** « Lire les commandes clients » de l'**API SAP S/4HANA**. Vous souhaitez maintenant utiliser l'**action** dans un **processus**. Pour cela, vous utiliserez le **type d'étape Action**. Comme le processus doit également pouvoir atteindre le `système SAP S/4HANA`, une **destination** est également requise.

Lors de la connexion de systèmes distants à votre environnement SAP BTP, il est essentiel de leur créer une destination. Cette destination fait office d'adresse technique du système à connecter. Les destinations peuvent inclure des informations supplémentaires, telles que les identifiants d'authentification et d'autorisation d'accès.

Dans cet exemple, vous souhaitez utiliser l'environnement API Sandbox de SAP Business Accelerator Hub comme proxy pour un `système SAP S/4HANA` Cloud.

Pour en savoir plus sur l'appel d'API de systèmes distants à l'aide d'actions dans un processus, suivez ce tutoriel interactif.

### EXERCISE OPTIONS

Pour démarrer l'exercice, sélectionnez « Démarrer l'exercice » dans la figure ci-dessous.

Une fenêtre contextuelle s'ouvre. Vous disposez des options suivantes :

Choisir « Démarrer » : la simulation démarre. Suivez la simulation pour apprendre à créer et configurer la logique de décision.
Choisir « Ouvrir un document PDF » : un PDF s'ouvre. En suivant les étapes décrites dans ce document, vous pouvez réaliser l'exercice dans votre environnement système.

[Exercise](https://learnsap.enable-now.cloud.sap/pub/mmcp/index.html?show=project!PR_C544C8F47B0B9DB5:uebung)

[PDF](<./assets/hands_on%20(5).pdf>)

[Steps](https://learning.sap.com/learning-journeys/create-processes-and-automations-with-sap-build-process-automation/encapsulating-the-apis-of-remote-systems-using-actions-projects_d102638b-94d7-4c2e-9547-bb344e9aa9de)

### PREREQUISITES

Vous avez effectué l'exercice Encapsuler les API des systèmes distants à l'aide de projets d'actions.

### TASK 1: PREPARE THE REMOTE SYSTEM AND CREATE A DESTINATION

(N/A)

### TASK 2: CREATE A NEW PROCESS AND A TRIGGER FORM FOR IT

[Exercise](https://learnsap.enable-now.cloud.sap/pub/mmcp/index.html?show=project!PR_144F8C2F6AE567A0:uebung)

[PDF](<./assets/hands_on%20(6).pdf>)

### TASK 3: USE ACTIONS

[Exercise](https://learnsap.enable-now.cloud.sap/pub/mmcp/index.html?show=project!PR_144F8C2F6AE567A0:uebung)

[PDF](<./assets/hands_on%20(6).pdf>)

### TASK 4: RELEASE, DEPLOY AND TEST THE PROCESS

(N/A)
