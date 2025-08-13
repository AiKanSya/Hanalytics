# 🌸 7 [STRING PROCESSING](https://learning.sap.com/learning-journeys/acquire-core-abap-skills/processing-data_b025c9e3-697d-423f-977a-43b9051a7c15)

## 🌸 TASK: STRING PROCESSING

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
    TYPES t_amount TYPE  p LENGTH 8 DECIMALS 2.

    DATA amount   TYPE t_amount VALUE '3.30'.
    DATA amount1  TYPE t_amount VALUE '1.20'.
    DATA amount2  TYPE t_amount VALUE '2.10'.

    DATA the_date  TYPE d                     VALUE '19891109'.
    DATA my_number TYPE p LENGTH 3 DECIMALS 2 VALUE '-273.15'.

    DATA part1 TYPE string VALUE `Hello`.
    DATA part2 TYPE string VALUE `World`.

* String Templates
**********************************************************************

    DATA(text1) = |Hello World|.
        out->write( text1 ).
        out->write(  '---------' ).

    DATA(text2) = |Total: { amount } EUR|.
        out->write( text2 ).
        out->write(  '---------' ).

    DATA(text3) = |Total: { amount1 + amount2 } EUR|.
        out->write( text3 ).
        out->write(  '---------' ).

* Format Options
**********************************************************************

    "Date
    DATA(textDate1) = |Raw Date: { the_date             }|.
        out->write( textDate1 ).
        out->write(  '---------' ).

    DATA(textDate2) = |ISO Date: { the_date Date = ISO  }|.
        out->write( textDate2 ).
        out->write(  '---------' ).

    DATA(textDate3) = |USER Date:{ the_date Date = USER }|.
        out->write( textDate3 ).
        out->write(  '---------' ).

    "Number
    DATA(textNumber1) = |Raw Number { my_number                    }|.
        out->write( textNumber1 ).
        out->write(  '---------' ).

    DATA(textNumber2) = |User Format{ my_number NUMBER = USER      }|.
        out->write( textNumber2 ).
        out->write(  '---------' ).

    DATA(textNumber3) = |Sign Right { my_number SIGN = RIGHT       }|.
        out->write( textNumber3 ).
        out->write(  '---------' ).

    DATA(textNumber4) = |Scientific { my_number STYLE = SCIENTIFIC }|.
        out->write( textNumber4 ).
        out->write(  '---------' ).

* String expression (concatenation Operator)
**********************************************************************

    DATA(textString1) = part1 && part2.
        out->write( textString1 ).
        out->write(  '---------' ).

    DATA(textString2) = part1 && | | && part2.
        out->write( textString2 ).
        out->write(  '---------' ).

    DATA(textString3) = |{ amount1 } + { amount2 }| &&
                        | = | &&
                        |{ amount1 + amount2 }|.
        out->write( textString3 ).
        out->write(  '---------' ).

  ENDMETHOD.
ENDCLASS.
```

#### 💮 **Résultats** :

```
USER Date:11/09/1989
---------
Raw Number -273.15
---------
User Format-273.15
---------
Sign Right 273.15-
---------
Scientific -2.7315E+02
---------
HelloWorld
---------
Hello World
---------
1.20 + 2.10 = 3.30
---------
```
