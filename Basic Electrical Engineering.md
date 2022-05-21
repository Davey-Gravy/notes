# Definitions and Basic Concepts

## Introduction

- Basic field and circuit concepts

## Electric Charge and Coulomb's Law

[[Coulomb's Law]]

## [[Electric Current]]

- Symbol $I$
	- unit of *amperes* ($A$)

### Direct Current (DC)

- unidirectional transfer of electrons through a conductor

## [[Voltage]]

- Symbol $V$
	- unit of *volts* ($V$)

## [[Power and Energy]]

### Energy

$$ 
U = QV\quad(\text{J})
$$

### Power

$$ 
P = \frac{dU}{dt}=V\frac{dQ}{dt}=VI\quad(\text{W})
$$

## Units, Dimensions, and Constants

| Quantity                 | Symbol     | Dimensions                                                                                             | SI Unit                                   |
| ------------------------ | ---------- | ------------------------------------------------------------------------------------------------------ | ----------------------------------------- |
| Electric charge          | $Q$        | $\left[\text{A}\right]\left[\text{T}\right]$                                                           | coulomb, $\text{C}$                       |
| Electric potential       | $V$        | $\left[\text{M}\right]\left[\text{A}\right]^{-1}\left[\text{L}\right]^2\left[\text{T}\right]^{-3}$     | volt, $\text{V}$                          |
| Current                  | $I$        | $\left[\text{A}\right]$                                                                                | ampere, $\text{A}$                        |
| Electric field intensity | $E$        | $\left[\text{M}\right]\left[\text{A}\right]^{-1}\left[\text{L}\right]\left[\text{T}\right]^{-3}$       | volt/meter, $\text{V/m}$                  |
| Electric flux density    | $D$        | $\left[\text{A}\right]\left[\text{L}\right]^{-2}\left[\text{T}\right]$                                 | coulomb/meter<sup>2</sup>, $\text{V/m}^2$ |
| Permittivity             | $\epsilon$ | $\left[\text{M}\right]^{-1}\left[\text{A}\right]^2\left[\text{L}\right]^{-3}\left[\text{T}\right]^4$   | farad/meter, $\text{F/m}$                 |
| Resistance               | $R$        | $\left[\text{M}\right]\left[\text{A}\right]^{-2}]\left[\text{L}\right]^2\left[\text{T}^{-3}\right]$    | ohm, $\mathrm{\Omega}$                             |
| Capacitance              | $C$        | $\left[\text{M}\right]^{-1}\left[\text{A}\right]^{2}\left[\text{L}\right]^{-2}\left[\text{T}\right]^4$ | farad, $\text{F}$                                |
| Conductivity             | $\sigma$   | $\left[\text{M}\right]^{-1}\left[\text{A}\right]^{2}\left[\text{L}\right]^{-3}\left[\text{T}\right]^3$ | siemens/meter, $\text{S/m}$               | 


## Solved Problems

### 1.1

Two point charges of 50 $\mu\text{C}$ are held 1.5 $\text{m}$ apart in free space. What is the force of repulsion between the two charges?

> Using Coulomb's law:
> $$
> F=k\frac{Q_1Q_2}{r^2}=\boxed{9\times10^9\left(\frac{\left(50\times10^{-6}\right)^2}{1.5^2}\right)=10\text{ N}}
> $$

### 1.2

Find the electric field intensity 1.5 $\text{m}$ from a 50 $\mu\text{C}$ charge in free space

> Definition of electric field intensity:
> $$
> E=\lim_{Q_2\to0}\frac{F}{Q_2}
> $$
> Substitute into Coulomb's law:
> $$
> E=k\frac{Q_1}{r^2}=\boxed{9\times10^9\left(\frac{50\times10^{-6}}{1.5^2}\right)=200\text{ kN/C}=200\text{ kV/m}}
> $$

### 1.3

Two point charges $Q_1=50\mu\text{C}$, and $Q_2=25\mu\text{C}$ are separated by a distance of 1 $\text{m}$ in air. At what distance from $Q_1$ will the electric field intensity be zero?



# Circuit Elements and Laws

## Circuit Notions

Elements:
- Resistance
- Capacitance
- Inductance
- Voltage source
- Current source

Terminology:

- circuit/network
	- interconnection of circuit elements
- node
	- junction of two or more elements

## Element Voltage-Current Relationships

Resistors

> $$v=Ri\qquad i=Gv$$
> $$G=\frac{1}{R} \quad\left[\text{Siemens (S)}\right]\quad \text{conductance}$$

Capacitors

> $$C=\frac{Q}{V}=\frac{q}{v}$$
*Q* - steady state charge
*V* - steady state voltage
*q* - transient charge
*q* - transient voltage
$$i=\frac{dq}{dt}$$
$$v=\frac{1}{C}\int i\,dt\qquad\text{or}\qquad i=C\frac{dv}{dt}$$

Inductors

> $$v=L\frac{di}{dt}\qquad\text{or}\qquad i=\frac{1}{L}\int v\,dt$$

## Series and Parallel Circuits

Resistance:

> $$R_\text{series}=\sum_{k=1}^{n}R_k\qquad R_\text{parallel}=\sum_{k=1}^{n}\left(\frac{1}{R_k}\right)^{-1}$$

### [[Voltage Division]]

### [[Current Division]]
