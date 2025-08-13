# 🌸 4 [USING CONDITIONS TO CONTROL THE PROCESS FLOW](https://learning.sap.com/learning-journeys/create-processes-and-automations-with-sap-build-process-automation/using-conditions-to-control-the-process-flow_df45b353-142d-42a3-91e4-4c8d13a1aace)

> 🌺 Objectifs
>
> - [ ] Créer et configurer les conditions du processus
>
> - [ ] Créer une condition de processus et ajuster le flux de processus

## 🌸 USING CONDITIONS TO CONTROL THE FLOW IN AN OVERVIEW

### INTRODUCTION

Parfois, un processus n'est pas seulement un flux séquentiel d'étapes, mais il se ramifie selon la situation métier.

Dans cette leçon, vous apprendrez à ajouter une **condition de processus** qui oriente le processus métier selon certains critères. Ces conditions appliquent une **règle « Si/Sinon »**, et le processus métier répond selon les règles définies dans les paramètres de condition du processus. Ainsi, lorsque l'expression « Si » définit une condition, l'expression « Sinon » contient les instructions concernant la marche à suivre si la condition n'est pas remplie.

Avec `SAP Build Process Automation`, vous pouvez automatiser votre processus pour emprunter différents **chemins conditionnels** sans écrire une seule ligne de code. Vous utiliserez des conditions de processus pour supprimer les approbations inutiles en acheminant le processus vers l'approbation automatique, ou vers un flux d'approbation en une seule étape, en fonction des critères de la commande client. Par exemple, une commande client inférieure à une certaine valeur, comme 50 000, ne nécessite pas d'approbation, et toutes les autres commandes client seront soumises à une approbation à un seul niveau.

### CREATING AND CONFIGURING A PROCESS CONDITION

[Référence - Link Video](https://learning.sap.com/learning-journeys/create-processes-and-automations-with-sap-build-process-automation/using-conditions-to-control-the-process-flow_df45b353-142d-42a3-91e4-4c8d13a1aace)

Maintenant que vous avez conçu un processus avec des formulaires et une automatisation, définissons quel flux de processus doit s'exécuter en fonction des conditions If/Else qui déterminent quel flux de processus est exécuté et s'il y aura une approbation automatique ou un itinéraire d'approbation en une étape.

## 🌸 CREATE A PROCESS CONDITION AND ADJUST THE PROCESS FLOW

### BUSINESS SCENARIO

Vous apprendrez à utiliser les conditions de processus dans un processus métier pour éliminer les approbations inutiles lorsque le processus est acheminé vers un flux d'approbation automatique ou en une étape, en fonction des critères de la commande client.

Une condition de processus achemine le processus métier selon certains critères. Ces conditions appliquent une règle « Si/Sinon » au contenu du processus et répondent selon les règles définies dans les paramètres du générateur de processus.

Pour en savoir plus sur la création d'une condition de processus et l'ajustement du flux de processus, suivez ce tutoriel interactif.

### EXERCISE OPTIONS

Pour démarrer l'exercice, sélectionnez « Démarrer l'exercice » dans la figure ci-dessous.

Une fenêtre contextuelle s'ouvre. Vous disposez des options suivantes :

- Choisir « Démarrer » : la simulation démarre. Suivez la simulation pour apprendre à activer le contenu d'automatisation des processus.

- Choisir « Ouvrir un document PDF » : un PDF s'ouvre. En suivant les étapes décrites dans ce document, vous pouvez réaliser l'exercice dans votre environnement système.

[Exercise](https://learnsap.enable-now.cloud.sap/pub/mmcp/index.html?show=project!PR_EE19FFBA4850E7B4:uebung)

[PDF](<./assets/hands_on%20(4).pdf>)

### STEPS

1. Créez une condition de processus et ajustez son déroulement.

2. Choisissez « Ajouter une étape de processus ».

3. Choisissez « Contrôles et événements ».

4. Choisissez « Condition ».

5. Choisissez « Ouvrir l'éditeur de conditions ».

6. Choisissez « Contenu du processus ».

7. Dans la liste déroulante « Contenu du processus », choisissez « Montant de la commande ».

8. Ouvrez la liste « Est égal à ».

9. Choisissez « Est inférieur à ».

10. Dans le champ « Montant de la commande », saisissez « 100 000 KM SERVICE ».

11. Choisissez « Appliquer ».

12. Choisissez « Ouvrir l'éditeur de conditions ».

13. Choisissez « Ajouter un groupe ».

14. Choisissez « N'importe lequel ».

15. Choisissez « Contenu du processus ».

16. Sélectionnez la barre de défilement pour faire défiler vers le bas.

17. Dans la liste « Contenu du processus », choisissez « Pays d'expédition ».

18. Dans le champ « Valeur », saisissez « Inde ».

19. Sélectionnez à nouveau « Contenu du processus ».

20. Sélectionnez la barre de défilement pour faire défiler vers le bas.

21. Dans la liste « Contenu du processus », choisissez « Pays d'expédition ».

22. Dans le champ « Valeur », saisissez « Allemagne ».

23. Sélectionnez la barre de défilement pour faire défiler vers le bas.

24. Pour développer le panneau, sélectionnez la flèche.

25. Sélectionnez la barre de défilement pour faire défiler vers le bas.

26. Choisissez Appliquer.

27. Choisissez Fermer le panneau latéral.

28. Choisissez Ajouter une étape de processus.

29. Choisissez Formulaire.

30. Choisissez Formulaire vierge.

31. Dans le champ Nom, saisissez Notification d'approbation automatique.

32. Dans le champ Description, saisissez Formulaire de notification pour l'approbation automatique de la commande client.

33. Choisissez Créer.

34. Choisissez Plus d'options.

35. Sélectionnez Ouvrir l'éditeur.

36. Choisissez Titre.

37. Dans le champ Nouveau titre, saisissez Confirmation automatique de commande.

38. Choisissez Paragraphe.

39. Dans le champ Nouveau paragraphe, saisissez « Votre commande a été reçue » et nous vous enverrons les détails dès son expédition. Vous trouverez les détails de votre commande ci-dessous. Veuillez vérifier votre demande :

40. Choisissez Paragraphe.

41. Dans le champ Nouveau paragraphe, saisissez les détails de votre commande :

42. Choisissez Texte.

43. Dans le champ Nouveau texte, saisissez Numéro de commande.

44. Sélectionnez Lecture seule.

45. Choisissez Numéro.

46. Dans le champ Nouveau numéro, saisissez Montant de la commande.

47. Sélectionnez Lecture seule.

48. Choisissez Date.

49. Dans le champ « Nouvelle date », saisissez la date de livraison prévue.

50. Sélectionnez « Lecture seule ».

51. Choisissez « Paragraphe ».

52. Dans le champ « Nouveau paragraphe », saisissez « Veuillez appuyer sur le bouton « Soumettre » pour confirmer l'état de la commande. ».

53. Choisissez « Enregistrer ».

54. Sélectionnez Traitement des commandes.

55. Choisissez Notification d'approbation automatique.

56. Dans le champ Objet, saisissez « Votre commande a bien été reçue ».

57. Choisissez Numéro de commande.

58. sélectionnez la barre de défilement pour faire défiler vers le bas.

59. Choisissez Utilisateurs.

60. Dans le volet Contenu du processus, choisissez « Processus démarré par ».

61. Choisissez Entrées.

62. Dans le volet Notification d'approbation automatique, choisissez « Date de livraison prévue ».

63. Dans le volet Contenu du processus, choisissez « Date de livraison prévue ».

64. Dans le volet Notification d'approbation automatique, choisissez « Montant de la commande ».

65. Dans le volet Contenu du processus, choisissez « Montant de la commande ».

66. Dans le volet Notification d'approbation automatique, choisissez « Numéro de commande ».

67. Dans le volet Contenu du processus, choisissez « Numéro de commande ».

68. Choisissez « Fermer le panneau latéral ».

69. Choisissez « Ajouter une étape de processus » (icône +).

70. Choisissez « Contrôles et événements ».

71. Choisissez « Fin ».

72. Choisissez « Zoom arrière ... Choisissez à nouveau « Zoom arrière ».

73. Choisissez « Enregistrer ».

### RESULT

Vous avez maintenant créé avec succès une condition de processus et ajusté le flux de processus.
