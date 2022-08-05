# [[C++]]

## `public`

Accessible throughout the program

```cpp
class Class_name
{
public:
	// declarations
}
```

## `private`

Accessible to members or friends of the class

```cpp
class Class_Name
{
private:
	// declarations
}
```

## `protected`

Used with inheritance

## Example

```cpp
// class definition
class Player
{
private:
	std::string name;
	int health;
	int xp;
public:
	void talk(std::string text);
	bool is_dead
};

Player frank;
frank.name = "Frank";	// compiler error
frank.health = 1000;	// compiler error
frank.talk("Ready to battle"); // OK

Player *enemy = new Player();
enemy->xp = 100; 	// compiler error
enemy->talk("I will hunt you down"); //OK

delete enemy;
```

Allows certain attributes or methods to not be publicly accessible