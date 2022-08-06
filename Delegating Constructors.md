Code for one constructor can call another in the [[Constructor Initialization Lists|initialization list]]

Avoids duplicating code -> less bugs

Less detailed constructors can delegate to most verbosely defined constructor

```cpp
class Player() 
{
private:
	std::string name;
	int health;
	int xp;
public:
	Player();
	Player(std::string name_val);
	Player(std::string name_Val, int health_val, int xp_val);
}

// no-args constructor
Player::Player()
	: Player {"None", 0, 0} {
}

// single arg constructor
Player::Player(std::string name_val)
	: Player {name_val, 0, 0} {
}

// delegate to three arg constructor
Player::Player(std::string name_val, int health_val, int xp_val)
	: name{name_val}, health{health_val}, xp{xp_val} {
}
```
