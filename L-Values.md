Values that have names and are addressable

Modifiable if not set as `const`

L-values:

```cpp
// has name
int x {100};
// is modifiable
x = 1000;
x = 1000 + 20;

// has name
string name;
// is modifiable
name = "Frank";
```