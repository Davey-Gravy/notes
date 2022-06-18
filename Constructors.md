Similar to `__init__` in Python?

- Useful for initialization of [[Objects|objects]]
- Have same name as the class
- Don't specify a return type
- Can be [[Function Overloading|overloaded]]

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

[[Default Constructor]]