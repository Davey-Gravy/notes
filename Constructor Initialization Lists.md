Assignment, not initialization

```cpp
Player::PLayer() {
	name = "None";
	health = 0;
	xp = 0;
}
```

Initialization list

```cpp
Player::Player()
	: name{"None"}, health{0}, xp{0} {
}
```