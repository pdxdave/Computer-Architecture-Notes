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
