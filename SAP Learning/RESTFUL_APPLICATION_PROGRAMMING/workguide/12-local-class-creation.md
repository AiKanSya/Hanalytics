# 🌸 12 [LOCAL CLASS CREATION](https://learning.sap.com/learning-journeys/acquire-core-abap-skills/defining-a-local-class_d4f46591-157b-468f-b94a-8d484d5ddca9)

## 🌸 TASK: LOCAL CLASS CREATION

#### 💮 **Création d'une classe locale** :

![](./assets/Capture%20d’écran%202025-08-05%20162820.png)

![](./assets/Capture%20d’écran%202025-08-05%20162751.png)

1. Dans l'éditeur ABAP, saisissez lcl et appuyez sur [Ctrl] + [Espace].

![](./assets/Capture%20d’écran%202025-08-05%20162926.png)

![](./assets/Capture%20d’écran%202025-08-05%20163008.png)

![](./assets/Capture%20d’écran%202025-08-05%20165021.png)

```
*"* use this source file for the definition and implementation of
*"* local helper classes, interface definitions and type
*"* declarations
CLASS lcl_connection DEFINITION. "

*/ DEFINITION"
*
*   La partie DEFINITION d'une classe contient la DEFINITION et
*   la déclaration de tous ses éléments, c'est-à-dire les types,
*   les CONSTANTS, les attributs et les METHODS.
*
*/*

  PUBLIC SECTION.

* Public Section Process
**********************************************************************

    DATA carrier_id      TYPE char10.
    DATA connection_id   TYPE char10.
    DATA n_o_connections TYPE i.

    CLASS-DATA conn_counter TYPE i.

  PROTECTED SECTION.

* Protected Section Process
**********************************************************************

  PRIVATE SECTION.

* Private Section Process
**********************************************************************

ENDCLASS.

CLASS lcl_connection IMPLEMENTATION.

*/ IMPLEMENTATION
*
*   La partie IMPLEMENTATION d'une classe contient le code exécutable
*   de la classe, c'est-à-dire l'IMPLEMENTATION de ses METHODS.
*   L'IMPLEMENTATION d'une classe est facultative. Elle devient obligatoire
*   dès que la DEFINITION de la classe contient des METHODS exécutables.
*
*/*

ENDCLASS.
```

## 🌸 TASK: LOCAL CLASSES INSTANCIATION

#### 💮 **Classe globale** :

```
CLASS zcl_fgi_hello_world DEFINITION
  PUBLIC
  FINAL
  CREATE PUBLIC .

  PUBLIC SECTION.

    INTERFACES if_oo_adt_classrun .
  PROTECTED SECTION.
  PRIVATE SECTION.
ENDCLASS.



CLASS zcl_fgi_hello_world IMPLEMENTATION.

  METHOD if_oo_adt_classrun~main.


* Declarations
**********************************************************************

    " Déclaration de la <variable de référence> lcl_connection
    DATA: connection  TYPE REF TO lcl_connection.

    " Déclaration d'une <table d'instance> (optionnel)
    DATA connections TYPE TABLE OF REF TO lcl_connection.


* 1st Instance
**********************************************************************

    " Création de l'instance à partir de la <variable de référence>
    connection                = NEW #(  ).

    " Alimentation des attributs de la classe locale
    connection->carrier_id    = 'LH'.
    connection->connection_id = '0400'.

    " Ajout de l'instance dans la <table d'instance>  (optionnel)
    APPEND connection TO connections.


* 2nd INSTANCE
**********************************************************************

    " Création de l'instance à partir de la <variable de référence>
    connection                = NEW #(  ).

    " Alimentation des attributs de la classe locale
    connection->carrier_id    = 'AA'.
    connection->connection_id = '0017'.

    " Ajout de l'instance dans la <table d'instance>  (optionnel)
    APPEND connection TO connections.


* 3rd INSTANCE
**********************************************************************

    " Création de l'instance à partir de la <variable de référence>
    connection                = NEW #(  ).

    " Alimentation des attributs de la classe locale
    connection->carrier_id    = 'SQ'.
    connection->connection_id = '0001'.

    " Ajout de l'instance dans la <table d'instance>  (optionnel)
    APPEND connection TO connections.


* Output
**********************************************************************

    LOOP AT connections ASSIGNING FIELD-SYMBOL(<lfs_connection>).

        out->write( <lfs_connection> ).

    ENDLOOP.


  ENDMETHOD.

ENDCLASS.
```

```
->
LCL_CONNECTION
CARRIER_ID    CONNECTION_ID
LH            0400
->
LCL_CONNECTION
CARRIER_ID    CONNECTION_ID
AA            0017
->
LCL_CONNECTION
CARRIER_ID    CONNECTION_ID
SQ            0001
```
