Code for one constructor can call another in the [[Constructor Initialization Lists|initialization list]]

Avoids duplicating code -> less bugs

```cpp
// no-args constructor
Player::Player()
	: Player {"None", 0, 0} {
}

// single arg constructor
Player::Player(std::string name_val)
	: Player {name_val, 0, 0} {
}
```
