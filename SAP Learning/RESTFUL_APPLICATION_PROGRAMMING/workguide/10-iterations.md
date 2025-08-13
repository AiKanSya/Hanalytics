# 🌸 10 [ITARATIONS](https://learning.sap.com/learning-journeys/acquire-core-abap-skills/using-control-structures-in-abap_a4d7803e-eac2-458e-acf9-8628289f3701)

## 🌸 TASK: EXCEPTION HANDLING

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

        CONSTANTS c_number TYPE i VALUE 3.
*        CONSTANTS c_number TYPE i VALUE 5.
*        CONSTANTS c_number TYPE i VALUE 10.

        DATA number TYPE i.

*     Example 1: DO ... ENDDO with TIMES
*    *********************************************************************

        out->write(  `----------------------------------` ).
        out->write(  `Example 1: DO ... ENDDO with TIMES` ).
        out->write(  `----------------------------------` ).

        DO c_number TIMES.
          out->write(  `Hello World` ).
        ENDDO.

*     Example 2: DO ... ENDDO with Abort Condition
*    *********************************************************************

        out->write(  `-------------------------------` ).
        out->write(  `Example 2: With Abort Condition` ).
        out->write(  `-------------------------------` ).

        number = c_number * c_number.

        " count backwards from number to c_number.
        DO.

          out->write( |{ sy-index }: Value of number: {  number }| ).
          number = number - 1.

          "abort condition
          IF number <= c_number.
            EXIT.
          ENDIF.

        ENDDO.

  ENDMETHOD.
ENDCLASS.
```

#### 💮 **Résultats** :

```
----------------------------------
Example 1: DO ... ENDDO with TIMES
----------------------------------
Hello World
Hello World
Hello World
-------------------------------
Example 2: With Abort Condition
-------------------------------
1: Value of number: 9
2: Value of number: 8
3: Value of number: 7
4: Value of number: 6
5: Value of number: 5
6: Value of number: 4
```

```
----------------------------------
Example 1: DO ... ENDDO with TIMES
----------------------------------
Hello World
Hello World
Hello World
Hello World
Hello World
-------------------------------
Example 2: With Abort Condition
-------------------------------
1: Value of number: 25
2: Value of number: 24
3: Value of number: 23
4: Value of number: 22
5: Value of number: 21
6: Value of number: 20
7: Value of number: 19
8: Value of number: 18
9: Value of number: 17
10: Value of number: 16
11: Value of number: 15
12: Value of number: 14
13: Value of number: 13
14: Value of number: 12
15: Value of number: 11
16: Value of number: 10
17: Value of number: 9
18: Value of number: 8
19: Value of number: 7
20: Value of number: 6
```

```
----------------------------------
Example 1: DO ... ENDDO with TIMES
----------------------------------
Hello World
Hello World
Hello World
Hello World
Hello World
Hello World
Hello World
Hello World
Hello World
Hello World
-------------------------------
Example 2: With Abort Condition
-------------------------------
1: Value of number: 100
2: Value of number: 99
3: Value of number: 98
4: Value of number: 97
5: Value of number: 96
6: Value of number: 95
7: Value of number: 94
8: Value of number: 93
9: Value of number: 92
10: Value of number: 91
11: Value of number: 90
12: Value of number: 89
13: Value of number: 88
14: Value of number: 87
15: Value of number: 86
16: Value of number: 85
17: Value of number: 84
18: Value of number: 83
19: Value of number: 82
20: Value of number: 81
21: Value of number: 80
22: Value of number: 79
23: Value of number: 78
24: Value of number: 77
25: Value of number: 76
26: Value of number: 75
27: Value of number: 74
28: Value of number: 73
29: Value of number: 72
30: Value of number: 71
31: Value of number: 70
32: Value of number: 69
33: Value of number: 68
34: Value of number: 67
35: Value of number: 66
36: Value of number: 65
37: Value of number: 64
38: Value of number: 63
39: Value of number: 62
40: Value of number: 61
41: Value of number: 60
42: Value of number: 59
43: Value of number: 58
44: Value of number: 57
45: Value of number: 56
46: Value of number: 55
47: Value of number: 54
48: Value of number: 53
49: Value of number: 52
50: Value of number: 51
51: Value of number: 50
52: Value of number: 49
53: Value of number: 48
54: Value of number: 47
55: Value of number: 46
56: Value of number: 45
57: Value of number: 44
58: Value of number: 43
59: Value of number: 42
60: Value of number: 41
61: Value of number: 40
62: Value of number: 39
63: Value of number: 38
64: Value of number: 37
65: Value of number: 36
66: Value of number: 35
67: Value of number: 34
68: Value of number: 33
69: Value of number: 32
70: Value of number: 31
71: Value of number: 30
72: Value of number: 29
73: Value of number: 28
74: Value of number: 27
75: Value of number: 26
76: Value of number: 25
77: Value of number: 24
78: Value of number: 23
79: Value of number: 22
80: Value of number: 21
81: Value of number: 20
82: Value of number: 19
83: Value of number: 18
84: Value of number: 17
85: Value of number: 16
86: Value of number: 15
87: Value of number: 14
88: Value of number: 13
89: Value of number: 12
90: Value of number: 11
```
