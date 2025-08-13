# 🌸 14 [LOCAL CLASS EXCEPTION HANDLING](https://learning.sap.com/learning-journeys/acquire-core-abap-skills/defining-and-calling-methods_bc2d0d2a-d7f4-41bf-84f2-65de61c408ed)

## 🌸 TASK: LOCAL CLASS EXCEPTION HANDLING

#### 💮 **1. Création de l'exception handling** :

```
*"* use this source file for the definition and implementation of
*"* local helper classes, interface definitions and type
*"* declarations
CLASS lcl_connection DEFINITION. "


  PUBLIC SECTION.

* Public Section Process
**********************************************************************

    DATA carrier_id      TYPE char10.
    DATA connection_id   TYPE char10.
    DATA n_o_connections TYPE i.

    CLASS-DATA conn_counter TYPE i.


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


*/* EXCEPTION HANDLING (1. Implémentation de la logique)
*
*   Si une erreur survient lors de l'exécution d'une méthode, celle-ci
*   peut déclencher une exception à l'aide de l'instruction
*   RAISE EXCEPTION TYPE, suivie du nom de l'exception.
*
*/*


  METHOD get_attributes.

    e_carrier_id    = carrier_id.
    e_connection_id = connection_id.
    n_o_connections = n_o_connections + 1.

  ENDMETHOD.

  METHOD set_attributes.

    IF carrier_id IS INITIAL OR connection_id IS INITIAL.

      " Techniquement, les noms d'exception sont ceux de classes ABAP
      " spécifiques et l'instruction RAISE EXCEPTION TYPE crée une
      " instance de la classe référencée. Cette instance est appelée
      " objet exception et les classes ABAP spécifiques sont appelées
      " classes d'exception.

      RAISE EXCEPTION TYPE cx_abap_invalid_value.

    ENDIF.

    carrier_id      = i_carrier_id.
    connection_id   = i_connection_id.

  ENDMETHOD.


ENDCLASS.
```

#### 💮 **2. Ajout de l'esception dans la définition** :

![](./assets/Capture%20d’écran%202025-08-06%20094643.png)

```
*"* use this source file for the definition and implementation of
*"* local helper classes, interface definitions and type
*"* declarations
CLASS lcl_connection DEFINITION. "


  PUBLIC SECTION.

* Public Section Process
**********************************************************************

    DATA carrier_id      TYPE char10.
    DATA connection_id   TYPE char10.
    DATA n_o_connections TYPE i.

    CLASS-DATA conn_counter TYPE i.

    " L'exception levée est déclarée dans la clause RAISING de la signature de la méthode.

    METHODS set_attributes
      IMPORTING
        i_carrier_id    TYPE char10 OPTIONAL
        i_connection_id TYPE char10
      RAISING
        cx_abap_invalid_value.

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


*/* EXCEPTION HANDLING (1. Implémentation de la logique)
*
*   Si une erreur survient lors de l'exécution d'une méthode, celle-ci
*   peut déclencher une exception à l'aide de l'instruction
*   RAISE EXCEPTION TYPE, suivie du nom de l'exception.
*
*/*


  METHOD get_attributes.

    e_carrier_id    = carrier_id.
    e_connection_id = connection_id.
    n_o_connections = n_o_connections + 1.

  ENDMETHOD.

  METHOD set_attributes.

    IF carrier_id IS INITIAL OR connection_id IS INITIAL.

      " Techniquement, les noms d'exception sont ceux de classes ABAP
      " spécifiques et l'instruction RAISE EXCEPTION TYPE crée une
      " instance de la classe référencée. Cette instance est appelée
      " objet exception et les classes ABAP spécifiques sont appelées
      " classes d'exception.

      RAISE EXCEPTION TYPE cx_abap_invalid_value.

    ENDIF.

    carrier_id      = i_carrier_id.
    connection_id   = i_connection_id.

  ENDMETHOD.


ENDCLASS.
```

#### 💮 **3. Ajout du TRY...CATCH...** :

```
*"* use this source file for the definition and implementation of
*"* local helper classes, interface definitions and type
*"* declarations
CLASS lcl_connection DEFINITION. "


  PUBLIC SECTION.

* Public Section Process
**********************************************************************

    DATA carrier_id      TYPE char10.
    DATA connection_id   TYPE char10.
    DATA n_o_connections TYPE i.

    CLASS-DATA conn_counter TYPE i.


    METHODS set_attributes
      IMPORTING
        i_carrier_id    TYPE char10 OPTIONAL
        i_connection_id TYPE char10
      RAISING
        cx_abap_invalid_value.

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


*/* EXCEPTION HANDLING (1. Implémentation de la logique)
*
*   Si une erreur survient lors de l'exécution d'une méthode, celle-ci
*   peut déclencher une exception à l'aide de l'instruction
*   RAISE EXCEPTION TYPE, suivie du nom de l'exception.
*
*/*


  METHOD get_attributes.

    e_carrier_id    = carrier_id.
    e_connection_id = connection_id.
    n_o_connections = n_o_connections + 1.

  ENDMETHOD.

  METHOD set_attributes.

    IF carrier_id IS INITIAL OR connection_id IS INITIAL.

      " Techniquement, les noms d'exception sont ceux de classes ABAP
      " spécifiques et l'instruction RAISE EXCEPTION TYPE crée une
      " instance de la classe référencée. Cette instance est appelée
      " objet exception et les classes ABAP spécifiques sont appelées
      " classes d'exception.

      " L'appel de la méthode est entouré d'une structure de contrôle TRY … ENDTRY.
      " La structure de contrôle TRY … ENDTRY contient un bloc CATCH pour l'exception.

      TRY.
        RAISE EXCEPTION TYPE cx_abap_invalid_value.
        CATCH cx_abap_invalid_value.
          "handle exception
      ENDTRY.

    ENDIF.

    carrier_id      = i_carrier_id.
    connection_id   = i_connection_id.

  ENDMETHOD.


ENDCLASS.
```
