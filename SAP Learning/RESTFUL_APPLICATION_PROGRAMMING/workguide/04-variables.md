# 🌸 4 [VARIABLES](https://learning.sap.com/learning-journeys/acquire-core-abap-skills/working-with-basic-data-objects-and-data-types_cf92dee2-85ec-4b9f-a778-1a7cfef70dad)

## 🌸 TASK: VARIABLES

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


*     Data Objects with Built-in Types
*    *********************************************************************

        " comment/uncomment the following declarations and check the output
        DATA variable TYPE string.
*        DATA variable TYPE i.
*        DATA variable TYPE d.
*        DATA variable TYPE c LENGTH 10.
*        DATA variable TYPE n LENGTH 10.
*        DATA variable TYPE p LENGTH 8 DECIMALS 2.

*     Output
*    *********************************************************************

        out->write(  'Result with Initial Value)' ).
        out->write(   variable ).
        out->write(  '---------' ).

        variable = '19891109'.

        out->write(  'Result with Value 19891109' ).
        out->write(   variable ).
        out->write(  '---------' ).

  ENDMETHOD.
ENDCLASS.
```

#### 💮 **Résultats** :

```
Result with Initial Value)
---------
Result with Value 19891109
19891109
---------
```

```
Result with Initial Value)
0
---------
Result with Value 19891109
19891109
---------
```

```
Result with Initial Value)
0000-00-00
---------
Result with Value 19891109
1989-11-09
---------
```

```
Result with Initial Value)
---------
Result with Value 19891109
19891109
---------
```

```
Result with Initial Value)
0000000000
---------
Result with Value 19891109
0019891109
---------
```

```
Result with Initial Value)
0.0
---------
Result with Value 19891109
19891109.0
---------
```
