- memberwise copy
- each data member copied from source object
- if data member is a pointer
	- pointer is copied, not what pointer points to
	- if destructor called, can leave memory location empty

```cpp
Player::Player(const Player &source)
	: name{source.name},
	  health{source.health},
	  xp{source.xp} {
}
```