<<<<<<< HEAD
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
=======
```cpp
Player::Player(const Player &source)
	: name{source.name},
	  health{source.health},
	  xp{source.xp} {
}
>>>>>>> 1d72f0fd62d46b0a7639d8c9cd2b528709e045c3
```