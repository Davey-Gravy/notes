Assignment, not initialization

```cpp
Player::PLayer() {
	name = "None";
	health = 0;
	xp = 0;
}
```

Initialization list

Interaction with overloaded constructors

No-args

```cpp
Player::Player()
	: name{"None"}, health{0}, xp{0} {
}
```

Multiple args

```cpp
Player::Player(std::string name_val)
	: name{name_val}, health{0}, xp{0} {
}
```