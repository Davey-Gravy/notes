Operators in programming language that compares data bit-by-bit, or *bitwise*

# [[C++]] 

## AND (`&`)

- Binary operator
- Returns 1 if both bits are 1

```cpp
  0111 (7)
& 0100 (4)
  ----
  0100 (4)
	  
7 & 4 = 4

0111 & 0100 = 0100
```

## OR (`|`)

- Binary operator
- Returns 0 when both bits are 0

```cpp
  0111 (7)
& 0100 (4)
  ----
  0111 (7)
	  
7 | 4 = 7
0111 | 0100 = 0111
```

## NOT (`~`)

- Unary operator
- Returns 0 when bit is 1, 1 when bit is 0