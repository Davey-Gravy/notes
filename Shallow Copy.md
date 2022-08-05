```cpp
Player::Player(const Player &source)
	: name{source.name},
	  health{source.health},
	  xp{source.xp} {
}
```