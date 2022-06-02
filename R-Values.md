Anything that is not an [[L-Values|L-value]] is an R-value

- Right hand side of assignment expression
- Literal
- Temporary intended to be non-modifiable

```cpp
int x {100};		// 100 is R-value
int y = x + 200;	// (x+200) is R-value

string name;
name = "Frank";		// "Frank" is R-value

int max_num = max (20, 30);	// max(20, 30) is R-value
```

References can be made to [[L-Values|L-values]], not R-values
- also applies to [[Pass by Reference|pass by reference]]