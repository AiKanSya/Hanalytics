# 🌸 6 [ARITHMETIC PROCESSING](https://learning.sap.com/learning-journeys/acquire-core-abap-skills/processing-data_b025c9e3-697d-423f-977a-43b9051a7c15)

## 🌸 TASK: ARITHMETIC CALCULATIONS

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

        " comment/uncomment these line for different result types
        TYPES t_result TYPE p LENGTH 8 DECIMALS 2.
*        TYPES t_result TYPE p LENGTH 8 DECIMALS 0.
*        TYPES t_result TYPE i.

        DATA result TYPE t_result.

        DATA number1 TYPE i.
        DATA number2 TYPE i.

        number1 = -8.
        number2 =  3.

*     Calculations
*    *********************************************************************

        result = 2 + 3.
        out->write( result ).
        out->write(  '---------' ).

        result = 2 - 3.
        out->write( result ).
        out->write(  '---------' ).

        result = 2 * 3.
        out->write( result ).
        out->write(  '---------' ).

        result = 2 / 3.
        out->write( result ).
        out->write(  '---------' ).

        result = sqrt( 2 ).
        out->write( result ).
        out->write(  '---------' ).

        result = ipow( base = 2 exp = 3 ).
        out->write( result ).
        out->write(  '---------' ).

        result = ( 8 * 7 - 6 ) / ( 5 + 4 ).
        out->write( result ).
        out->write(  '---------' ).

       result = 8 * 7 - 6 / 5 + 4.
        out->write( result ).
        out->write(  '---------' ).


       DATA(output) = |{ number1 } / { number2 } = { result }|.
        out->write( output ).
        out->write(  '---------' ).

  ENDMETHOD.
ENDCLASS.
```

#### 💮 **Résultats** :

```
5.0
---------
-1.0
---------
6.0
---------
0.67
---------
1.41
---------
8.0
---------
5.56
---------
58.8
---------
-8 / 3 = 58.80
---------
```

```
5
---------
-1
---------
6
---------
1
---------
1
---------
8
---------
6
---------
59
---------
-8 / 3 = 58.80
---------
```

```
5
---------
-1
---------
6
---------
1
---------
1
---------
8
---------
6
---------
59
---------
-8 / 3 = 58.80
---------
```
