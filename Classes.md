- Blueprints for [[OBjects|objects]]
- User-defined data type
- Has
	- Attributes (data)
	- Methods (functions)
- Provide public interface
- Can hide attributes and methods


# Declaring

```cpp
class Player
{
	// attributes
	std::string name;
	int health;
	int xp;
	
	// methods
	void talk(std::string text);
	bool is_dead();
};
```

```cpp
class Account
{
	// attributes
	std::string name;
	double balance;
	
	// methods
	bool withdraw(double amount);
	bool deposit(double amount);
};
```

# Instantiating

```cpp
Player frank;
Player hero;

Player *enemy = new Player()
delete enemy;
```
```cpp
Account frank_account;
Account jim_account;

Account *mary_account = new Account();
delete mary_account
```