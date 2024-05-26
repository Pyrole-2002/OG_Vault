# Binary Number
A binary number is a number expressed in the base-$2$ numeral system.
We say that a certain bit is **set** if it is $1$ and **cleared** if it is $0$.
The binary number $(a_ka_{k-1}\dots a_1a_0)_2$ represents the number:
$$(a_ka_{k-1}\dots a_1a_0)_2 = 2^ka_k+2^{k-1}a_{k-1}\cdots2^1a_1+2^0a_0$$
CPU's are very fast manipulating bits with specific operations.
```cpp
unsigned int unigned_number = 13;
assert(unsigned_number == 0b1101);

int positive_signed_number = 13; // 32-bit
assert(positive_signed_number == 0b1101);

short negative_signed_number = -13; // 16-bit
assert(negative_signed_number == 0b1111'1111'1111'0011); // Two's Complement
```
### Bitwise Operators
