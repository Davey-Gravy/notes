# Declaration

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
	bool withdraw(double amount) {
		balance -= val;
		cout << "In withdraw"
	};
	
	bool deposit(double amount) {
		balace += val; 
		cout << "In deposit";
	};
}; 
```

# Instantiation

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

# Access

```cpp
int main() {
	Account frank_account;
	frank_account.name = "Frank's account";
	frank_account.balance = 5000.0;
	
	frank_account.deposit(1000.0);
	frank_account.withdraw(500.0);
	
	Player frank;
	frank.name = "Frank";
	frank.health = 100;
	frank.xp = 12;
	frank.talk("Hi there");
	
	Player *enemy = new Player;
	(*enemy).name = "Enemy";
	(*enemy).health = 100;
	enemy -> xp = 15;
	enemy->talk("I will destroy you!")
}
```