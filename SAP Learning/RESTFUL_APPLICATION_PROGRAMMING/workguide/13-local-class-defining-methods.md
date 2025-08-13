# 🌸 13 [LOCAL CLASS DEFINING METHODS](https://learning.sap.com/learning-journeys/acquire-core-abap-skills/defining-and-calling-methods_bc2d0d2a-d7f4-41bf-84f2-65de61c408ed)

## 🌸 TASK: LOCAL CLASS METHOD CREATION

#### 💮 **1. Création de la définition des méthodes de la classe locale** :

```
*"* use this source file for the definition and implementation of
*"* local helper classes, interface definitions and type
*"* declarations
CLASS lcl_connection DEFINITION. "

*/ <ANY> SECTION>
*
*   Dans la partie DEFINITION d'une classe, vous utilisez
*   - METHODS pour définir une méthode d'instance
*   - CLASS-METHODS pour définir une méthode statique.
*
*   Le nom de la METHOD est suivi de sa signature, c'est-à-dire l'ensemble
*   - les PARAMETERS (valeurs échangées) par la METHOD avec son appelant
*   - les EXCEPTIONS qui peuvent survenir pendant l'exécution de la méthode.
*
*   METHODS <method_name>
*       IMPORTING       <input_1>  TYPE <type>                      " champ mandatory
*                       <input_2>  TYPE <type> OPTIONAL             " champ devient facultatif
*                       <input_3>  TYPE <type> DEFAULT <val>
*                       ...
*       EXPORTING       <output_1> TYPE <type>                      " champ facultatif
*                       <output_2> TYPE <type>                      " champ facultatif
*                       <output_3> TYPE <type>                      " champ facultatif
*                       ...
*       CHANGING        <inout_1>  TYPE <type>                      " mandatory
*                       <inout_2>  TYPE <type> OPTIONAL             " champ devient facultatif
*                       <inout_3>  TYPE <type>
*                       ...
*       RETURNING VALUE(<result>)  TYPE <type>                      " Unique
*       RAISING         <exception_1>
*                       <exception_2>
*                       ...          .
*
*/*

  PUBLIC SECTION.

* Public Section Process
**********************************************************************

    DATA carrier_id      TYPE char10.
    DATA connection_id   TYPE char10.
    DATA n_o_connections TYPE i.

    CLASS-DATA conn_counter TYPE i.

*/ METHODS DEFINITION (1. Création)
*
*   Création des METHODS :
*   Une méthode set_attributes( ) définit les valeurs des attributs
*   - i_carrier_id
*   - i_connection_id
*
*   Une méthode get_attributes( ) renvoie les valeurs de ces attributs.
*
*   Alors que set_attributes( ) nécessite deux paramètres d'importation,
*   un pour chaque attribut, la méthode get_attributes( ) nécessite deux
*   paramètres d'exportation.
*
*/*

    METHODS set_attributes
        IMPORTING
            i_carrier_id    TYPE char10 OPTIONAL
            i_connection_id TYPE char10.

    METHODS get_attributes
        EXPORTING
            e_carrier_id    TYPE char10
            e_connection_id TYPE char10.


  PROTECTED SECTION.

* Protected Section Process
**********************************************************************

  PRIVATE SECTION.

* Private Section Process
**********************************************************************

ENDCLASS.

CLASS lcl_connection IMPLEMENTATION.


ENDCLASS.
```

#### 💮 **2. Création de l'implémentation des méthodes de la classe locale** :

> #### 🍧 Hint
>
> ADT propose un correctif rapide pour ajouter l'implémentation manquante. Pour l'utiliser, procédez comme suit :
>
> 1. Positionnez le curseur sur une instruction METHODS présentant une erreur et appuyez sur [Ctrl] + [1].
>
>    ![](./assets/Capture%20d’écran%202025-08-06%20091437.png)
>
> 2. Dans la liste des correctifs rapides possibles, choisissez « Ajouter une implémentation pour… » et appuyez sur Entrée. Si l'implémentation est manquante pour plusieurs méthodes, le correctif rapide s'intitule « Ajouter… méthodes non implémentées ».

```
*"* use this source file for the definition and implementation of
*"* local helper classes, interface definitions and type
*"* declarations
CLASS lcl_connection DEFINITION. "

*/ <ANY> SECTION>
*
*   Dans la partie DEFINITION d'une classe, vous utilisez
*   - METHODS pour définir une méthode d'instance
*   - CLASS-METHODS pour définir une méthode statique.
*
*   Le nom de la METHOD est suivi de sa signature, c'est-à-dire l'ensemble
*   - les PARAMETERS (valeurs échangées) par la METHOD avec son appelant
*   - les EXCEPTIONS qui peuvent survenir pendant l'exécution de la méthode.
*
*   METHODS <method_name>
*       IMPORTING       <input_1>  TYPE <type>                      " champ mandatory
*                       <input_2>  TYPE <type> OPTIONAL             " champ devient facultatif
*                       <input_3>  TYPE <type> DEFAULT <val>
*                       ...
*       EXPORTING       <output_1> TYPE <type>                      " champ facultatif
*                       <output_2> TYPE <type>                      " champ facultatif
*                       <output_3> TYPE <type>                      " champ facultatif
*                       ...
*       CHANGING        <inout_1>  TYPE <type>                      " mandatory
*                       <inout_2>  TYPE <type> OPTIONAL             " champ devient facultatif
*                       <inout_3>  TYPE <type>
*                       ...
*       RETURNING VALUE(<result>)  TYPE <type>                      " Unique
*       RAISING         <exception_1>
*                       <exception_2>
*                       ...          .
*
*/*

  PUBLIC SECTION.

* Public Section Process
**********************************************************************

    DATA carrier_id      TYPE char10.
    DATA connection_id   TYPE char10.
    DATA n_o_connections TYPE i.

    CLASS-DATA conn_counter TYPE i.

*/ METHODS DEFINITION (1. Création)
*
*   Création des METHODS :
*   Une méthode set_attributes( ) définit les valeurs des attributs
*   - i_carrier_id
*   - i_connection_id
*
*   Une méthode get_attributes( ) renvoie les valeurs de ces attributs.
*
*   Alors que set_attributes( ) nécessite deux paramètres d'importation,
*   un pour chaque attribut, la méthode get_attributes( ) nécessite deux
*   paramètres d'exportation.
*
*/*

    METHODS set_attributes
        IMPORTING
            i_carrier_id    TYPE char10 OPTIONAL
            i_connection_id TYPE char10.

    METHODS get_attributes
        EXPORTING
            e_carrier_id    TYPE char10
            e_connection_id TYPE char10.


  PROTECTED SECTION.

* Protected Section Process
**********************************************************************

  PRIVATE SECTION.

* Private Section Process
**********************************************************************

ENDCLASS.

CLASS lcl_connection IMPLEMENTATION.

*/ METHODS IMPLEMENTATION (2. Implémentation de la METHOD)
*
*   Pour chaque méthode définie, vous devez également créer une implémentation
*   dans la partie implémentation de la classe. Tant que vous ne le faites pas,
*   des erreurs de syntaxe apparaissent dans votre classe ;
*   la vérification syntaxique indique que l'implémentation de la méthode est manquante.
*
*   1. Positionnez le curseur sur une instruction METHODS présentant une erreur et appuyez sur [Ctrl] + [1].
*
*   2. Dans la liste des correctifs rapides possibles, choisissez "Add X implemented methods".
*
*/*

  METHOD get_attributes.

  ENDMETHOD.

  METHOD set_attributes.

  ENDMETHOD.

ENDCLASS.
```

#### 💮 **3. Implémentation de la logique des méthodes de la classe locale** :

```
*"* use this source file for the definition and implementation of
*"* local helper classes, interface definitions and type
*"* declarations
CLASS lcl_connection DEFINITION. "

*/ <ANY> SECTION>
*
*   Dans la partie DEFINITION d'une classe, vous utilisez
*   - METHODS pour définir une méthode d'instance
*   - CLASS-METHODS pour définir une méthode statique.
*
*   Le nom de la METHOD est suivi de sa signature, c'est-à-dire l'ensemble
*   - les PARAMETERS (valeurs échangées) par la METHOD avec son appelant
*   - les EXCEPTIONS qui peuvent survenir pendant l'exécution de la méthode.
*
*   METHODS <method_name>
*       IMPORTING       <input_1>  TYPE <type>                        " champ mandatory
*                       <input_2>  TYPE <type> OPTIONAL               " champ devient facultatif
*                       <input_3>  TYPE <type> DEFAULT <val>
*                       ...
*       EXPORTING       <output_1> TYPE <type>                        " champ facultatif
*                       <output_2> TYPE <type>                        " champ facultatif
*                       <output_3> TYPE <type>                        " champ facultatif
*                       ...
*       CHANGING        <inout_1>  TYPE <type>                        " mandatory
*                       <inout_2>  TYPE <type> OPTIONAL               " champ devient facultatif
*                       <inout_3>  TYPE <type>
*                       ...
*       RETURNING VALUE(<result>)  TYPE <type>                        " Unique
*       RAISING         <exception_1>
*                       <exception_2>
*                       ...          .
*
*/*

  PUBLIC SECTION.

* Public Section Process
**********************************************************************

    DATA carrier_id      TYPE char10.
    DATA connection_id   TYPE char10.
    DATA n_o_connections TYPE i.

    CLASS-DATA conn_counter TYPE i.

*/ METHODS DEFINITION (1. Création)
*
*   Création des METHODS :
*   Une méthode set_attributes( ) définit les valeurs des attributs
*   - i_carrier_id
*   - i_connection_id
*
*   Une méthode get_attributes( ) renvoie les valeurs de ces attributs.
*
*   Alors que set_attributes( ) nécessite deux paramètres d'importation,
*   un pour chaque attribut, la méthode get_attributes( ) nécessite deux
*   paramètres d'exportation.
*
*/*

    METHODS set_attributes
        IMPORTING
            i_carrier_id    TYPE char10 OPTIONAL
            i_connection_id TYPE char10.

    METHODS get_attributes
        EXPORTING
            e_carrier_id    TYPE char10
            e_connection_id TYPE char10.


  PROTECTED SECTION.

* Protected Section Process
**********************************************************************

  PRIVATE SECTION.

* Private Section Process
**********************************************************************

ENDCLASS.

CLASS lcl_connection IMPLEMENTATION.

*/ METHODS IMPLEMENTATION (2. Implémentation de la METHOD)
*
*   Pour chaque méthode définie, vous devez également créer une
*   implémentation dans la partie implémentation de la classe. Tant
*   que vous ne le faites pas, des erreurs de syntaxe apparaissent
*   dans votre classe ; la vérification syntaxique indique que
*   l'implémentation de la méthode est manquante.
*
*   1. Positionnez le curseur sur une instruction METHODS présentant
*      une erreur et appuyez sur [Ctrl] + [1].
*
*   2. Dans la liste des correctifs rapides possibles, choisissez
*      "Add X implemented methods".
*
*/* METHODS IMPLEMENTATION (3. Implémentation de la logique)
*
*   L'implémentation de la méthode contient des instructions ABAP qui
*   peuvent accéder aux paramètres de la méthode (vous n'êtes pas
*   autorisé à modifier les paramètres d'importation)  ainsi qu'à tous
*   les types, attributs et constantes déclarés dans la classe, quelle
*   que soit leur visibilité.
*   Les méthodes d'instance peuvent accéder aux attributs d'instance et
*   aux attributs statiques.
*   Les méthodes statiques ne peuvent accéder qu'aux composants
*   statiques.
*
*   Dans la partie implémentation d'une classe, vous pouvez accéder aux
*   attributs de cette classe sans variable de référence et sans ->
*   (ou sans le nom de la classe et =>, dans le cas d'attributs
*   statiques).
*
*/*

  METHOD get_attributes.

    e_carrier_id    = carrier_id.
    e_connection_id = connection_id.
    n_o_connections = n_o_connections + 1.

  ENDMETHOD.

  METHOD set_attributes.

    carrier_id      = i_carrier_id.
    connection_id   = i_connection_id.

  ENDMETHOD.

ENDCLASS.
```
