# 🌸 8 [CONDITIONAL BRANCHING](https://learning.sap.com/learning-journeys/acquire-core-abap-skills/using-control-structures-in-abap_a4d7803e-eac2-458e-acf9-8628289f3701)

## 🌸 TASK: CONDITIONAL BRANCHING

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

*     Declarations
*    *********************************************************************

        CONSTANTS c_number TYPE i VALUE 0.
*        CONSTANTS c_number TYPE i VALUE 1.
*        CONSTANTS c_number TYPE i VALUE 2.
*        CONSTANTS c_number TYPE i VALUE -1.
*        CONSTANTS c_number TYPE i VALUE -2.

*     Example 1: Simple IF ... ENDIF.
*    *********************************************************************

        out->write(  `--------------------------------` ).
        out->write(  `Example 1: Simple IF ... ENDIF.` ).
        out->write(  `-------------------------------` ).

        IF c_number = 0.
          out->write( `The value of C_NUMBER equals zero`   ).
        ELSE.
          out->write( `The value of C_NUMBER is NOT zero`   ).
        ENDIF.

*     Example 2: Optional Branches ELSEIF and ELSE
*    *********************************************************************

        out->write(  `--------------------------------------------` ).
        out->write(  `Example 2: Optional Branches ELSEIF and ELSE` ).
        out->write(  `--------------------------------------------` ).

        IF c_number = 0.
          out->write( `The value of C_NUMBER equals zero`            ).
        ELSEIF c_number > 0.
          out->write( `The value of C_NUMBER is greater than zero`   ).
        ELSE.
          out->write( `The value of C_NUMBER is less than zero`      ).
        ENDIF.

*     Example 3: CASE ... ENDCASE
*    *********************************************************************

        out->write(  `---------------------------` ).
        out->write(  `Example 3: CASE ... ENDCASE` ).
        out->write(  `---------------------------` ).

        CASE c_number.
          WHEN 0.
            out->write( `The value of C_NUMBER equals zero`             ).
          WHEN 1.
            out->write( `The value of C_NUMBER equals one`              ).
          WHEN 2.
            out->write( `The value of C_NUMBER equals two`              ).
          WHEN OTHERS.
            out->write( `The value of C_NUMBER equals non of the above` ).
        ENDCASE.

  ENDMETHOD.
ENDCLASS.
```

#### 💮 **Résultats** :

```
--------------------------------
Example 1: Simple IF ... ENDIF.
-------------------------------
The value of C_NUMBER equals zero
--------------------------------------------
Example 2: Optional Branches ELSEIF and ELSE
--------------------------------------------
The value of C_NUMBER equals zero
---------------------------
Example 3: CASE ... ENDCASE
---------------------------
The value of C_NUMBER equals zero
```

```
--------------------------------
Example 1: Simple IF ... ENDIF.
-------------------------------
The value of C_NUMBER is NOT zero
--------------------------------------------
Example 2: Optional Branches ELSEIF and ELSE
--------------------------------------------
The value of C_NUMBER is greater than zero
---------------------------
Example 3: CASE ... ENDCASE
---------------------------
The value of C_NUMBER equals one
```

```
--------------------------------
Example 1: Simple IF ... ENDIF.
-------------------------------
The value of C_NUMBER is NOT zero
--------------------------------------------
Example 2: Optional Branches ELSEIF and ELSE
--------------------------------------------
The value of C_NUMBER is greater than zero
---------------------------
Example 3: CASE ... ENDCASE
---------------------------
The value of C_NUMBER equals two
```

```
--------------------------------
Example 1: Simple IF ... ENDIF.
-------------------------------
The value of C_NUMBER is NOT zero
--------------------------------------------
Example 2: Optional Branches ELSEIF and ELSE
--------------------------------------------
The value of C_NUMBER is less than zero
---------------------------
Example 3: CASE ... ENDCASE
---------------------------
The value of C_NUMBER equals non of the above
```

```
--------------------------------
Example 1: Simple IF ... ENDIF.
-------------------------------
The value of C_NUMBER is NOT zero
--------------------------------------------
Example 2: Optional Branches ELSEIF and ELSE
--------------------------------------------
The value of C_NUMBER is less than zero
---------------------------
Example 3: CASE ... ENDCASE
---------------------------
The value of C_NUMBER equals non of the above
```
