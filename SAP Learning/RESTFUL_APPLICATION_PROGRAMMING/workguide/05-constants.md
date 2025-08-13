# 🌸 5 [CONSTANTS](https://learning.sap.com/learning-journeys/acquire-core-abap-skills/working-with-basic-data-objects-and-data-types_cf92dee2-85ec-4b9f-a778-1a7cfef70dad)

## 🌸 TASK: CONSTANTS

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


*     Example 1: Local Types
*    *********************************************************************

*     Comment/Uncomment the following lines to change the type of my_var
        TYPES my_type TYPE p LENGTH 3 DECIMALS 2.
*        TYPES my_type TYPE i .
*        TYPES my_type TYPE string.
*        TYPES my_type TYPE n length 10.

*     Variable based on local type
        DATA my_variable TYPE my_type.

        out->write(  `my_variable (TYPE my_type)` ).
        out->write(   my_variable ).
        out->write(  '---------' ).

*     Example 2: Constants
*    *********************************************************************

        CONSTANTS c_text   TYPE string VALUE `Hello World`.
        CONSTANTS c_number TYPE i      VALUE 12345.

        "Uncomment this line to see syntax error ( VALUE is mandatory)
*      constants c_text2   type string.

        out->write(  `c_text (TYPE STRING)` ).
        out->write(   c_text ).
        out->write(  '---------' ).

        out->write(  `c_number (TYPE I )` ).
        out->write(   c_number ).
        out->write(  `---------` ).

*     Example 3: Literals
*    *********************************************************************

        out->write(  '12345               ' ).    "Text Literal   (Type C)
        out->write(  `12345               ` ).    "String Literal (Type STRING)
        out->write(  12345                  ).    "Number Literal (Type I)

        "uncomment this line to see syntax error (no number literal with digits)
*        out->write(  12345.67                  ).

  ENDMETHOD.
ENDCLASS.
```

#### 💮 **Résultats** :

```
my_variable (TYPE my_type)
0.0
---------
c_text (TYPE STRING)
Hello World
---------
c_number (TYPE I )
12345
---------
12345
12345
12345
```

```
my_variable (TYPE my_type)
0
---------
c_text (TYPE STRING)
Hello World
---------
c_number (TYPE I )
12345
---------
12345
12345
12345
```

```
my_variable (TYPE my_type)
---------
c_text (TYPE STRING)
Hello World
---------
c_number (TYPE I )
12345
---------
12345
12345
12345
```

```
my_variable (TYPE my_type)
0000000000
---------
c_text (TYPE STRING)
Hello World
---------
c_number (TYPE I )
12345
---------
12345
12345
12345
```
