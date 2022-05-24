Functions can be defined such that if an argument is not passed into the function, a default parameter may be used

# [[C++]]
- Best practice -> define in [[C++ Functions#Prototypes| function prototype]]

```c
// without default arguments
double calc_cost (double base_cost, double tax_rate);

double calc_cost (double base_Cost ,double tax_rate) {
	return base_cost += (base_cost * tax_rate);
}

int main() {
	double cost {0};
	cost = calc_cost(100.0, 0.06);
	return 0;
}
```

```c
// with default arguments
double calc_cost (double base_cost, double tax_rate==0.06);

double calc_cost (double base_Cost ,double tax_rate) {
	return base_cost += (base_cost * tax_rate);
}

int main() {
	double cost {0};
	cost = calc_cost(200.0);		// uses default argument
	cost = calc_cost(100.0, 0.08);	// does not
	return 0;
}
```