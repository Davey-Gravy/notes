## Inside Class Declaration

```cpp
class Account {
	
	private:
		double balance;
	public:
		void set_balance(double bal) {
			balance = bal;
		} 
		double get_balance() {
			return balance;
		}
}
```

- `balance` is private
	- public methods needed to access `balance`

## Outside Class Declaration

```cpp
void Account::set_balance(double bal) {
	balance = bal;
}

double Account::get_balance() {
	return balance;
}
```

- recommended practice as programs get larger

## Separating Declaration from Implementation

Create `.h` file

```cpp
class Account {

private:
	double balance;
public:
	void set_balance(double bal);
	double get_balance();
};
```

- class, methods, and attributes declared without being implemented

Good idea to use [[Include Guard]]

```cpp
#ifndef _ACCOUNT_H_
#define _ACCOUNT_H_

class Account {

private:
	double balance;
public:
	void set_balance(double bal);
	double get_balance();
};
```
Only include `.h` files, never `.cpp` files
