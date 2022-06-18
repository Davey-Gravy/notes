- Has same name as [[Classes|class]]
	- preceded by tilde 
- Invoked automatically when [[Objects|object]] destroyed
	- Pointer deleted
	- Objects become out of scope
- No return type, parameters
- Cannot be [[Function Overloading|overloaded]]

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