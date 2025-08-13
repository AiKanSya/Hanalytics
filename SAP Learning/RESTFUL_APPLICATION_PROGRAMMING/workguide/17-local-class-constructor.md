# 🌸 17 [LOCAL CLASS CONSTRUCTOR](https://learning.sap.com/learning-journeys/acquire-core-abap-skills/defining-and-calling-methods_bc2d0d2a-d7f4-41bf-84f2-65de61c408ed)

## 🌸 TASK: LOCAL CLASS CONSTRUCTOR

#### 💮 **1. Création de l'INSTANCE CONSTRUCTOR** :

```
*"* use this source file for the definition and implementation of
*"* local helper classes, interface definitions and type
*"* declarations
CLASS lcl_connection DEFINITION.


  PUBLIC SECTION.

* Attributes

    DATA carrier_id     TYPE char10.
    DATA connection_id  TYPE char10.

    CLASS-DATA conn_counter TYPE i READ-ONLY.

* Methods

    METHODS constructor
      IMPORTING
        i_connection_id TYPE char10
        i_carrier_id    TYPE char10
      RAISING
        cx_ABAP_INVALID_VALUE.

    METHODS get_output
        RETURNING
            VALUE(r_output) TYPE string_table.


  PROTECTED SECTION.

  PRIVATE SECTION.


ENDCLASS.

CLASS lcl_connection IMPLEMENTATION.

  METHOD constructor.

    IF i_carrier_id IS INITIAL OR i_connection_id IS INITIAL.
      RAISE EXCEPTION TYPE cx_abap_invalid_value.
    ENDIF.

    me->connection_id = i_connection_id.
    me->carrier_id    = i_carrier_id.

    conn_counter = conn_counter + 1.

  ENDMETHOD.

  METHOD get_output.

    APPEND |------------------------------| TO r_output.
    APPEND |Carrier:     { carrier_id    }| TO r_output.
    APPEND |Connection:  { connection_id }| TO r_output.

  ENDMETHOD.

ENDCLASS.
```

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

    DATA connection TYPE REF TO lcl_connection.
    DATA connections TYPE TABLE OF REF TO lcl_connection.

* First Instance
**********************************************************************
    TRY.
        connection = NEW #(
                            i_carrier_id    = 'LH'
                            i_connection_id = '0400'
                          ).

        APPEND connection TO connections.

      CATCH cx_abap_invalid_value.
        out->write( `Method call failed` ).
    ENDTRY.

* Second instance
**********************************************************************
    TRY.
        connection = NEW #(
                            i_carrier_id    = 'AA'
                            i_connection_id = '0017'
                          ).
        APPEND connection TO connections.

      CATCH cx_abap_invalid_value.
        out->write( `Method call failed` ).
    ENDTRY.

* Third instance
**********************************************************************
    TRY.
        connection = NEW #(
                            i_carrier_id    = 'SQ'
                            i_connection_id = '0001'
                          ).
        APPEND connection TO connections.

      CATCH cx_abap_invalid_value.
        out->write( `Method call failed` ).
    ENDTRY.

* Output
**********************************************************************
    LOOP AT connections INTO connection.
      out->write( connection->get_output( ) ).
    ENDLOOP.
  ENDMETHOD.

ENDCLASS.
```
