# 🌸 16 [LOCAL CLASS RETURNING VALUE](https://learning.sap.com/learning-journeys/acquire-core-abap-skills/defining-and-calling-methods_bc2d0d2a-d7f4-41bf-84f2-65de61c408ed)

## 🌸 TASK: LOCAL CLASS RETURNING VALUE

#### 💮 **1. Création de l'exception handling** :

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

   DATA connection  TYPE REF TO lcl_connection.
   DATA connections TYPE TABLE OF REF TO lcl_connection.

* Create Instance
**********************************************************************

    connection = NEW #(  ).

    TRY.
        connection->set_attributes(
          EXPORTING
            i_carrier_id    = 'LH'
            i_connection_id = '0400'
        ).

        APPEND connection TO connections.

      CATCH cx_abap_invalid_value.

        out->write( `Method call failed` ).

    ENDTRY.


* Calling Functional Method
**********************************************************************

    " in a value assignment (with inline declaration for result)
    DATA(result) = connection->get_output( ).

    " in logical expression
    IF connection->get_output(  ) IS NOT INITIAL.

      " as operand in a statement
      LOOP AT connection->get_output(  ) INTO DATA(line).

        out->write( connection->get_output( ) ).

      ENDLOOP.

      "  to supply input parameter of another method
      out->write( data = connection->get_output( )
                  name = `  ` ).

    ENDIF.

  ENDMETHOD.

ENDCLASS.
```

```
*"* use this source file for the definition and implementation of
*"* local helper classes, interface definitions and type
*"* declarations
CLASS lcl_connection DEFINITION. "


  PUBLIC SECTION.

* Attributes
    DATA carrier_id     TYPE char10.
    DATA connection_id  TYPE char10.

    CLASS-DATA conn_counter TYPE i.


* Methods
    METHODS set_attributes
        IMPORTING
            i_carrier_id    TYPE char10 DEFAULT 'LH'
            i_Connection_id TYPE char10
        RAISING
            cx_abap_invalid_value.

    " Functional Method
    METHODS get_output
        RETURNING
            VALUE(r_output) TYPE string_table.


  PROTECTED SECTION.

  PRIVATE SECTION.


ENDCLASS.

CLASS lcl_connection IMPLEMENTATION.


    METHOD set_attributes.

      IF i_carrier_id IS INITIAL OR i_connection_id IS INITIAL.
        RAISE EXCEPTION TYPE cx_abap_invalid_value.
      ENDIF.

      carrier_id    = i_carrier_id.
      connection_id = i_connection_id.

    ENDMETHOD.


    METHOD get_output.

        APPEND |------------------------------| TO r_output.
        APPEND |Carrier:     { carrier_id    }| TO r_output.
        APPEND |Connection:  { connection_id }| TO r_output.

    ENDMETHOD.


ENDCLASS.
```
