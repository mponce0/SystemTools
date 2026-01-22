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
A given numerical value can be represented differently given a different base to do so.
This is the same concept as we have in Linear Algebra, where a vector representation change coefficients depending on the basis used to expand it.
Similarly if we have numerical value in one basis, its representation will change in a different one.

For example, the number 77 in base-10 can be written as 01001101 in base-2.

As a general observation, a numerical representation in base-X, will have `0,...,X-1` possible digits.
E.g.
  - base-10 (decimal): `0,1,2,3,4,5,6,7,8,9`
  - base-2 (binary): `0,1`
  - base-7 (septenary): `0,1,2,3,4,5,6`
  - base-8 (octal): `0,1,2,3,4,5,6,7`
  - base-16 (hexadecimal): `0,1,2,3,4,5,6,7,8,9,A,B,C,D,E,F` (here `A`->10, `B`->11, `C`->12, `D`->13, `E`->14, and `F`->15).


In order to see how the binary representation "01001101" in base-2 corresponds to 77 in base-10, we can notice the following,

```
     0   1   0   0   1   1   0   1
     |   |   |   |   |   |   |   |
    2^7 2^6 2^5 2^4 2^3 2^2 2^1 2^0
   =128 =64 =32 =16  =8  =4  =2  =1
==> (0*128) + (1*64) + (0*32) + (0*16) + (1*8) + (1*4) + (0*2) + (1*1) = 64+8+4+1 = 77
```

> *Exercise:*
    write a program to convert representations between two given numerical bases.


> *Exercise:*
    Assuming a 32-bits architecture, show why `int`s in C can taken values between

```C
    INT_MIN        = -2147483648
    INT_MAX        = +2147483647
```
and

```C
    UINT_MAX       = 4294967295
```

in the case of unsigned ints.


## Representation Dependencies
In general, is concibable that after indicating the basis for the representation of a numerical value this would be uniquely determined.
This is mostly true in the case of computer representations, but taking into consideration the following:

  * how many bytes are used to represent a particular data type, e.g. an `int`-type can be represented using 4 or 8 bytes depending on
    the hardware architecture and OS; 4 bytes is used by 32-bits architectures/OSes, 8 bytes is used by 64-bits architectures/OSes.

    > 32-bits = 4 bytes * 8 (bits/byte)
  
    > 64-bits = 8 bytes * 8 (bits/byte)   

 
  * the order in which we represent the data, i.e. whether we write first the least or most significant figure. This known as *endianness*.
    It turns out that different machines and OSes at some point were using different conventions and this has percolated until nowadays,
    seeing the most typical difference when communicating information between machines where the network protocols use big-endian vs most of our modern computer systems that use little-endian.
 
---

### Example 
Let's consider the value 10 (in base-10), and see how many digits are needed in different bases to represent such a value.

```
1 byte -> 8 bits: | | | | | | | | |  => 2^8 possible values = 256
             bit#  0 1 2 3 4 5 6 7

       -> 2 hexadecimals: | | |  => 16^2 = 256

e.g.
      10 (base-10) ~ 01010000 (base-2) ~ 0A (base-16)

```

If we also consider the order in which we want to represent the "digits" for this one byte, then we can see that,
```
* little-endian:  10 (base-10) ~ ~ 01010000 (base-2) ~ 0A (base-16)

* big-endian: ~ 01 (base-10) ~ 00001010 (base-2) ~ A0 (base-16)
```
---

A more "complete" ASCII table is shown below, where in addittion to the decimal and corresponding
character, is included the respective octal (base-8) and hexadecimal (base-16) values

```sh
ASCII Table:
------------
Char | Dec | Hex | Oct          Char | Dec | Hex | Oct          Char | Dec | Hex | Oct          Char | Dec | Hex | Oct
-----|-----|-----|-----         -----|-----|-----|-----         -----|-----|-----|-----         -----|-----|-----|-----
  !  |  33 |  21 |  41            "  |  34 |  22 |  42            #  |  35 |  23 |  43            $  |  36 |  24 |  44
  %  |  37 |  25 |  45            &  |  38 |  26 |  46            '  |  39 |  27 |  47            (  |  40 |  28 |  50
  )  |  41 |  29 |  51            *  |  42 |  2A |  52            +  |  43 |  2B |  53            ,  |  44 |  2C |  54
  -  |  45 |  2D |  55            .  |  46 |  2E |  56            /  |  47 |  2F |  57            0  |  48 |  30 |  60
  1  |  49 |  31 |  61            2  |  50 |  32 |  62            3  |  51 |  33 |  63            4  |  52 |  34 |  64
  5  |  53 |  35 |  65            6  |  54 |  36 |  66            7  |  55 |  37 |  67            8  |  56 |  38 |  70
  9  |  57 |  39 |  71            :  |  58 |  3A |  72            ;  |  59 |  3B |  73            <  |  60 |  3C |  74
  =  |  61 |  3D |  75            >  |  62 |  3E |  76            ?  |  63 |  3F |  77            @  |  64 |  40 | 100
  A  |  65 |  41 | 101            B  |  66 |  42 | 102            C  |  67 |  43 | 103            D  |  68 |  44 | 104
  E  |  69 |  45 | 105            F  |  70 |  46 | 106            G  |  71 |  47 | 107            H  |  72 |  48 | 110
  I  |  73 |  49 | 111            J  |  74 |  4A | 112            K  |  75 |  4B | 113            L  |  76 |  4C | 114
  M  |  77 |  4D | 115            N  |  78 |  4E | 116            O  |  79 |  4F | 117            P  |  80 |  50 | 120
  Q  |  81 |  51 | 121            R  |  82 |  52 | 122            S  |  83 |  53 | 123            T  |  84 |  54 | 124
  U  |  85 |  55 | 125            V  |  86 |  56 | 126            W  |  87 |  57 | 127            X  |  88 |  58 | 130
  Y  |  89 |  59 | 131            Z  |  90 |  5A | 132            [  |  91 |  5B | 133            \  |  92 |  5C | 134
  ]  |  93 |  5D | 135            ^  |  94 |  5E | 136            _  |  95 |  5F | 137            `  |  96 |  60 | 140
  a  |  97 |  61 | 141            b  |  98 |  62 | 142            c  |  99 |  63 | 143            d  | 100 |  64 | 144
  e  | 101 |  65 | 145            f  | 102 |  66 | 146            g  | 103 |  67 | 147            h  | 104 |  68 | 150
  i  | 105 |  69 | 151            j  | 106 |  6A | 152            k  | 107 |  6B | 153            l  | 108 |  6C | 154
  m  | 109 |  6D | 155            n  | 110 |  6E | 156            o  | 111 |  6F | 157            p  | 112 |  70 | 160
  q  | 113 |  71 | 161            r  | 114 |  72 | 162            s  | 115 |  73 | 163            t  | 116 |  74 | 164
  u  | 117 |  75 | 165            v  | 118 |  76 | 166            w  | 119 |  77 | 167            x  | 120 |  78 | 170
  y  | 121 |  79 | 171            z  | 122 |  7A | 172            {  | 123 |  7B | 173            |  | 124 |  7C | 174
  }  | 125 |  7D | 175            ~  | 126 |  7E | 176
```

> *Exercise:*
    write a C program that would genereate an output exactly like the table shown above.

---

### Example: long/unsigned ints

long is a integer type but "larger", i.e. it has more bytes assigned to be able to represent larger numbers.
Typically (this depends on the actual architecture), an int uses 4 bytes, and a long uses 8 bytes... which means that a int would cover a range of 2^(4*8) =2 ^32 possible values, if you consider positive and negative values, then it will be 2^32/2 - 1.
Same thing applies for long ints... now you may notice the "unsigned" type, and in this case the whole range of values can be used to represent just "positive" numbers, i.e. 2^32 (-1) for a typical unsigned int.

> *Exercise:*
    write a C program that finds how many bytes each major representation uses in the machine where it's been run:
        int, long, unsigned, float, double, ...

  Hint: check the use of the `sizeof()` function; also there is an interesting library `limits.h`.

---
