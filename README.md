# Computer-Architecture-Notes
Computer Architecture Notes

### Day 1 - Basics, Number Bases

Numbers have value.  Assuming we have 12 apples, they can be represnted like so:
* 12 (decimal)
* 1100 apples (binary)
* c apples (hexadecimal)

#### Number bases
* Decimal has 10 digits (0,1,2,3,4,5,6,7,8,9)
* Binary has 2 digits (0,1)
* Hexadecimal has 16 digits (0,1,2,3,4,5,6,7,8,9,A,B,C,D,E,F)

#### Terminology
* Byte: 8 bits. Max value: 255 decimal, FF hex, min value 0
* Nibble: 4 bits. Max value: 15 decimal, F hex, min value 0
* Decimal: A base- 10 numbering system
* Hexadecimal: A base -16 numbering system
* Binary: A base -2 numbering system

### Conversions

Base 2 binary
```
  |  +--------- 64s
  || +----------32s
  ||| +---------16s
  |||| + ------- 8s
  ||||| + ------ 4s
  |||||| + ----- 2s
  ||||||| +----- 1s
  ||||||||
  01010110
```
```
 128 64 32 16 8 4 2 1
  0   1  0  1 0 1 0 1
```

Decimal to binary
Exmaple: 67
Would be: 01000011

------------ 

#### Convert Binary to Hexadecimal

First we'll split this up into Nibbles
```
1010      0011
 10    &    3 in decimal
```
Each Nibble can be converted into a Hexadecimal digit

In Hexadecimal 10 is A.  So the above would be A3, which is 10100011


#### Convert Hexadecimal to Binary

The Hexadecimal number will be C7

C in Hexidecimal is 1100.  Remember this is a Nibble that adds up to 12
7 in Hexidecimal is 0111.
C7 Hexadecimal == 11000111 in Binary


### How to identify to the compiler
* Decimal == 100        // value 100 decimal
* Hexadecimal == 0x100  // value 256 decimal
* Binary == 0b100       // value 4 decimal
* Hexadecimal == 0x47F

In Hex 47F would be 0100 0111 1111

#### Printing binary to other bases

This is using C language

```
int x = 0b11000101;

printf("%d decimal\n", x);  \\ 197 decimal
printf("%x hexl\n", x);     \\ c5 hex
printf("%X hex\n", x);      \\ C5 hex
```
```
int x = 255;

printf("%X\n", y);    \\ FF

```

### Day 2

#### Bitwise Operations

Boolean operations work on 1=T/0=F values.  We use operators like &&(AND), ||(OR), !(NOT)

Bitwise operations work on numeric values.

```
Truth table for bitwise NOT

A        NOT A
--------------
0         1(inverts it)
1         0

This works much like regular boolean. If A is set to False(0), then say A != False it checks for True
```
In C NOT looks like this
```
NOT operator is '~' (tilde)

    a = 1
    ~a == 0
    
    a = 0
    ~a == 1
```
AND and OR tables
```
A   B    A AND B            A   B    A OR B
--------------             -----------------
0    0     0                0    0      0
0    1     0                0    1      1
1    0     0                1    0      1
1    1     1                1    1      1


AND operator is '&'                    OR operator is '|' 

    a = 0                                     a = 0
    b = 0                                     b = 0
    
    a & b == 0                                a | b == 0
    
    a = 1                                     a = 1
    b = 0                                     b = 0
    a & b == 0                                a | b == 1
    
    a = 1                                     a = 1
    b = 1                                     b = 1
    a & b == 1                                a | b == 1
```
Relatives of AND and OR   ---   NAND and NOR
```
A    B   A AND B            A    B    A NAND B
--------------             -----------------
0    0     0                0    0      1
0    1     0                0    1      1
1    0     0                1    0      1
1    1     1                1    1      0

** NAND is inverted

```
```
A    B   A OR B            A    B    A NOR B
--------------             -----------------
0    0     0                0    0      1
0    1     1                0    1      0
1    0     1                1    0      0
1    1     1                1    1      0

NOR is an inverse of the OR table
```
XOR
Similar to NOR but is only true if one or the other is true, not both
```

A    B   A XOR B
-------------- 
0    0     1               
0    1     1               
1    0     1                
1    1     0 

```
### Multi-bit Numbers

```
  1 1 1 0 1 0 1 1
& 1 0 0 1 1 1 0 1
------------
  1 0 0 0 1 0 0 1


exclusive XOR
  1 1 0 1 1 0 1 0
^ 1 1 1 0 0 0 1 1
-------------------
  0 0 1 1 1 0 0 1
```

Class Notes - Why this project?  What's the big picture?

ls8 language
- machine code
- operations with two arguments
- linear, things must be next to each other

Logical operations and Truth Table

```
not (A and B) and not (not A or not B) === False
-- breakdown of above (A nand B) and (A and B)

for A in [False, True]:
  for B in [False, True]:
    print(f"{A}-{B})

```

MORE Bitwise operations
  - Logical Operations
  - Bit shift
  - Bit mask
  
0b 0101 0110    decimal value  0d86  /  hex value 0x56

```
01010110
11000011

Bitwise operator
86 & 195

   01010110
 & 11000011
 --------------
   01000010
   
 2 + 64 = 66
```

```
Bitshift
Why is this important?  Some commands take 2 or 3 arguments.  
How do we know how many arguments are in each command?
The first two bits will tell how many arguments there are.  
call 01  is one argument.  cmp has two artuments 10 
dec has 1 so 01.

Bitshift is used to calculate this.  
01010110 >> 6 is 00000001

01010110 >> 1
shifting to the left by one
00101011

01010110 << 1
shifting to the right by one
10101100

```
```
Bitmask

     01010110  original
and  00001110  the mask
-------------
     00000110

```
```
A + B Truth table

A     B     A + B          A + B / like AND and XOR
---------------------------------
0     0      0  or 00      0   0
0     1      1     01      0   1
1     0      1     01      0   1
1     1      2     10      1   0

```

Today's assignment

file i/o

ls8.py  file

create file called file.py

import sys  

if len(sys.arg) != 2:
  print("usage: file.py <filename>", file=sys.stderr)   // file then path
  sys.exit(1)
  
try:
  with open(sys.argv[1) as f:
    for line in f:
      print(line)
      
except FileNoFoundError:
    
    
```
