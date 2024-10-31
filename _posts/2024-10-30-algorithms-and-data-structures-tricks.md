---
tags:
  - "Coding"
---

# Algorithms and Data Structures Tricks 

### Create a binary representation of a number

Combine bitshifting with the bitwise AND operator to compute whether bit
`k` of number is a `0` or `1`. The logical result of this computation 
determines whether the bit is a `0` or `1`. For example, to compute the bits 
of the number `4`, which is `100` in base 2.

```python
>>> 4 & (1 << 0)
0
>>> 4 & (1 << 1)
0
>>> 4 & (1 << 2)
4
```

The following code computes the entire binary string.
```python
number = 42
binaryString = ""
for bitIdx in range(number.bit_length()):
    currentBit = '1' if number & (1 << bitIdx) else '0'
    binaryString = currentBit + binaryString
```

For convenience, just use the `bin()` function.
```python
>>> bin(42)
'0b101010'
>>> bin(42)[2:]
'101010'
```
