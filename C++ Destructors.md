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
	// Destructor
	~Player();
}
```
- Destructors called FILO (First In Last Out)
	- imagine stack