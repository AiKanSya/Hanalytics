# 🌸 15 [LOCAL CLASS METHOD CALL](https://learning.sap.com/learning-journeys/acquire-core-abap-skills/defining-and-calling-methods_bc2d0d2a-d7f4-41bf-84f2-65de61c408ed)

## 🌸 TASK: LOCAL CLASS METHOD CALL

#### 💮 **1. Création de L'appel** :

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


*/ METHOD CALL
*
*   L'appel d'une méthode d'instance s'effectue à l'aide d'une
*   variable de référence et du sélecteur de composant d'instance ->.
*   Le sélecteur de composant est suivi du nom de la méthode à
*   appeler. Pour les méthodes statiques, utilisez le nom de la
*   classe et le sélecteur de composant statique =>.
*
*   Dans les deux cas, le passage des paramètres s'effectue entre
*   parenthèses. Ces parenthèses sont obligatoires dans tous les cas.
*   Elles restent vides si aucun paramètre n'est passé.
*
*
*   INSTANCE METHOD (->( )) :
*
*   <reference_variable>-><instance_method_name>(
*       EXPORTING       <output_1> TYPE <type>
*                       <output_2> TYPE <type>
*                       <output_3> TYPE <type>
*                       ...
*       IMPORTING       <input_1>  TYPE <type>
*                       <input_2>  TYPE <type> OPTIONAL
*                       <input_3>  TYPE <type> DEFAULT <val>
*                       ...
*       CHANGING        <inout_1>  TYPE <type>
*                       <inout_2>  TYPE <type> OPTIONAL
*                       <inout_3>  TYPE <type>
*                       ...
*       RETURNING VALUE(<result>)  TYPE <type>
*       RAISING         <exception_1>
*                       <exception_2>
*                       ...          ).
*
*   STATIC METHOD (=>( )) :
*
*   <reference_variable>=><static_method_name>(
*       EXPORTING       <output_1> TYPE <type>
*                       <output_2> TYPE <type>
*                       <output_3> TYPE <type>
*                       ...
*       IMPORTING       <input_1>  TYPE <type>
*                       <input_2>  TYPE <type> OPTIONAL
*                       <input_3>  TYPE <type> DEFAULT <val>
*                       ...
*       CHANGING        <inout_1>  TYPE <type>
*                       <inout_2>  TYPE <type> OPTIONAL
*                       <inout_3>  TYPE <type>
*                       ...
*       RETURNING VALUE(<result>)  TYPE <type>
*       RAISING         <exception_1>
*                       <exception_2>
*                       ...          ).
*
*/*


* Declarations
**********************************************************************

    CONSTANTS c_carrier_id    TYPE char10 VALUE 'LH'.
    CONSTANTS c_connection_id TYPE char10 VALUE '0400'.

    DATA connection  TYPE REF TO lcl_connection.
    DATA connections TYPE TABLE OF REF TO lcl_connection.

* Create Instance
**********************************************************************

    connection = NEW #(  ).

  ENDMETHOD.

ENDCLASS.
```

![](./assets/Capture%20d’écran%202025-08-06%20100650.png)

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


*/ METHOD CALL
*
*   L'appel d'une méthode d'instance s'effectue à l'aide d'une
*   variable de référence et du sélecteur de composant d'instance ->.
*   Le sélecteur de composant est suivi du nom de la méthode à
*   appeler. Pour les méthodes statiques, utilisez le nom de la
*   classe et le sélecteur de composant statique =>.
*
*   Dans les deux cas, le passage des paramètres s'effectue entre
*   parenthèses. Ces parenthèses sont obligatoires dans tous les cas.
*   Elles restent vides si aucun paramètre n'est passé.
*
*
*   INSTANCE METHOD (->( )) :
*
*   <reference_variable>-><instance_method_name>(
*       EXPORTING       <output_1> TYPE <type>
*                       <output_2> TYPE <type>
*                       <output_3> TYPE <type>
*                       ...
*       IMPORTING       <input_1>  TYPE <type>
*                       <input_2>  TYPE <type> OPTIONAL
*                       <input_3>  TYPE <type> DEFAULT <val>
*                       ...
*       CHANGING        <inout_1>  TYPE <type>
*                       <inout_2>  TYPE <type> OPTIONAL
*                       <inout_3>  TYPE <type>
*                       ...
*       RETURNING VALUE(<result>)  TYPE <type>
*       RAISING         <exception_1>
*                       <exception_2>
*                       ...          ).
*
*   STATIC METHOD (=>( )) :
*
*   <reference_variable>=><static_method_name>(
*       EXPORTING       <output_1> TYPE <type>
*                       <output_2> TYPE <type>
*                       <output_3> TYPE <type>
*                       ...
*       IMPORTING       <input_1>  TYPE <type>
*                       <input_2>  TYPE <type> OPTIONAL
*                       <input_3>  TYPE <type> DEFAULT <val>
*                       ...
*       CHANGING        <inout_1>  TYPE <type>
*                       <inout_2>  TYPE <type> OPTIONAL
*                       <inout_3>  TYPE <type>
*                       ...
*       RETURNING VALUE(<result>)  TYPE <type>
*       RAISING         <exception_1>
*                       <exception_2>
*                       ...          ).
*
*/*


* Declarations
**********************************************************************

    CONSTANTS c_carrier_id    TYPE char10 VALUE 'LH'.
    CONSTANTS c_connection_id TYPE char10 VALUE '0400'.

    DATA connection  TYPE REF TO lcl_connection.
    DATA connections TYPE TABLE OF REF TO lcl_connection.

* Create Instance
**********************************************************************

    connection = NEW #(  ).

* Call Method and Handle Exception
**********************************************************************
    out->write(  |i_carrier_id    = '{ c_carrier_id }' | ).
    out->write(  |i_connection_id = '{ c_connection_id }'| ).

    TRY.
        connection->set_attributes(
            EXPORTING
                i_carrier_id    = c_carrier_id
                i_connection_id = c_connection_id ).

        APPEND connection TO connections.

        out->write( `Method call successful` ).

      CATCH cx_abap_invalid_value.

        out->write( `Method call failed`     ).

    ENDTRY.

  ENDMETHOD.

ENDCLASS.
```
