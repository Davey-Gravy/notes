
 Container in the C++ Standard Library
 
- Dynamic array
	- can grow/shrink in size at execution
- Similar syntax to arrays
- Bounds checking
- Helpful functions
	- sort, reverse, find, etc.

# Declaration

```cpp
#include <vector>
using namespace std;

// vector <type> vector_name (size, init_value) {elements};
vector <char> vowels {'a','e','i','o','u'};

vector <int> test_scores {100, 98, 89, 85, 94};

vector <double> hi_temps (365, 80.0);
```