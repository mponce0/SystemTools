# Data Representation

At low level, computers can only store and manipulate information in binary format.
Sometimes this is actually done in bits, or collection of bits: bytes, either in plain binary format or equivalent representations such as hexadecimal (i.e. base-16 representation).

This is quite natural for computers as each bit can hold two possible values: a 0 or a 1, in other words, electricity flowing or not in electronic circuit.
Bits are grouped in set of 8 to form a *byte*. I.e. 1 byte is formed by 8 bits. 

As users we rarely interact with this form or representation, but we should still be aware of this in particular when considering aspects of the OS and the computer system.

For instance, when we consider characters (such as, the type `char` and its collections, e.g. strings)
these are represented using the so-called **"American Standard Code for Information Interchange"** (ASCII),
in which each character or symbol gets assign a value represented by a 1 byte long integer number.
The ASCII convention maps characters to these values.

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

> *Exercise:* Write a C program capable of generate this ASCII table.

For instance, the character 'M' is assigned the value 77 (in decimal representation, i.e. using base 10).


## Representations
A given numeical value can be represented differently given a different base to do so.
This is the same concept as we have in Linear Algbera, where a vector representation change coefficients depending on the basis used to expand it.
Similarly if we have numerical value in one basis, its representation will change in a different one.

For example, the number 77 in base-10 can be written as 01001101 in base-2.

As a general observation, a numerical representation in base-X, will have `0,...,X-1` possible digits.
E.g.
  - base-10: `0,1,2,3,4,5,6,7,8,9`
  - base-2: `0,1`
  - base-7: `0,1,2,3,4,5,6`
  - base-16: `0,1,2,3,4,5,6,7,8,9,A,B,C,D,E,F` (here `A`->10, `B`->11, `C`->12, `D`->13, `E`->14, and `F`->15).


In order to see how the binary representation "01001101" in base-2 corresponds to 77 in base-10, we can notice the following,

```
     0   1   0   0   1   1   0   1
     |   |   |   |   |   |   |   |
    2^7 2^6 2^5 2^4 2^3 2^2 2^1 2^0
   =128 =64 =32 =16  =8  =4  =2  =1
==> (0*128) + (1*64) + (0*32) + (0*16) + (1*8) + (1*4) + (0*2) + (1*1) = 64+8+4+1 = 77
```

> *Exercise:* write a program to convert representations between two given numerical bases.


## Representation Dependencies
In general, is conicbable that after indicating the basis for the representation of a numerical value this would be uniquely determined.
This is mostly true in the case of computer representations, but taking into consideration the following:

  * how many bytes are used to represent a particular data type, e.g. an `int`-type can be represented using 4 or 8 bytes depending on
    the hardware architecture and OS; 4 bytes is used by 32-bits architectures/OSes, 8 bytes is used by 64-bits architectures/OSes.

    > 32-bits = 4 bytes * 8 (bits/byte)
  
    > 64-bits = 8 bytes * 8 (bits/byte)   

 
  * the order in which we represent the data, i.e. whether we write first the least or most significant figure. This known as *endianness*.
    It turns out that different machines and OSes at some point were using different convensions and this has percolated until nowadays,
    seeing the most typical difference when communicating information between machines where the network protocols use big-endian vs most of our modern computer systems that use little-endian.
 
---

### Example 
Let's consider the value 10 (in base-10), and see how many digits are needed in different bases to represent such a value.

```
1 byte -> 8 bits: | | | | | | | | |  => 2^8 possible values = 256
             bit#  0 1 2 3 4 5 6 7

          2 hexadecimals: | | |  => 16^2 = 256


e.g.
      10 (base-10) ~ 01010000 (base-2) ~ 0A (base-16)

```

---
