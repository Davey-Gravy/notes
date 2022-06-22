# C++ Constructors

```cpp
class Player 
{
private:
	std::string name;
	int health;
	int xp;
public:
	// Overloaded constructors
	Player();
	Player(std::string name);
	Player(std::string name, int health, int xp);
}
```

[[Constructor Initialization Lists]]
[[Default Constructor]]
[[Delegating Constructors]]