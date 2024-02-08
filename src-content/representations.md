## Data Representation

At low level, computers can only store and manipulate information in binary format.
Sometimes this is actually done in bits, or collection of bits: bytes, either in plain binary format or equivalent representations such as hexadecimal (i.e. base-16 representation).

As users we rarely interact with this form or representation, but we should still be aware of this in particular when considering aspects of the OS and the computer system.

For instance, when we consider characters this are represented using the so-called "American Standard Code for Information Interchange", in which each character or symbol gets assign a value represented by a 1 byte long integer number.
The ASCII convention mps characters to this values.
For instance,
```sh
30      31      32      33 !    34 "    35 #    36 $    37 %    38 &    39 '
40 (    41 )    42 *    43 +    44 ,    45 -    46 .    47 /    48 0    49 1
50 2    51 3    52 4    53 5    54 6    55 7    56 8    57 9    58 :    59 ;
60 <    61 =    62 >    63 ?    64 @    65 A    66 B    67 C    68 D    69 E
70 F    71 G    72 H    73 I    74 J    75 K    76 L    77 M    78 N    79 O
80 P    81 Q    82 R    83 S    84 T    85 U    86 V    87 W    88 X    89 Y
90 Z    91 [    92 \    93 ]    94 ^    95 _    96 `    97 a    98 b    99 c
100 d   101 e   102 f   103 g   104 h   105 i   106 j   107 k   108 l   109 m
110 n   111 o   112 p   113 q   114 r   115 s   116 t   117 u   118 v   119 w
120 x   121 y   122 z   123 {   124 |   125 }   126 ~   127    ⏎
```

> Exercise: Write a C program capable of generate this ASCII table.

For instance, the character 'M' is assigned the value 77 (in decimal representation, i.e. using base 10).


## Representations
A given numeical value can be represented differently given a different base to do so.
This is the same concept as we have in Linear Algbera, where a vector representation change coefficients depending on the basis used to expand it.
Similarly if we have numerical value in one basis, its representation will change in a different one.

For example, the number 77 in base-10 can be written as 01001101 in base-2.

As a general observation, a numerical represntation in base-X, will have 0...X-1 possible digits.
E.g.
  - base-10: 0,1,2,3,4,5,6,7,8,9
  - base-2: 0,1
  - base-7: 0,1,2,3,4,5,6
  - base-16: 0,1,2,3,4,5,6,7,8,9,A,B,C,D,E,F (here A->10, B->11, C->12, D->13, E->14, and F->15).

