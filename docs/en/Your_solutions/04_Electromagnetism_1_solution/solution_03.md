# Task 03 - Electrostatic Equilibrium

## Problem Statement

Two positive charges, $q_1 = +4\ \text{C}$ and $q_2 = +9\ \text{C}$, are fixed on a straight line and separated by a distance of $2\ \text{m}$.

Find the equilibrium position of a third charge $q_3 = +1\ \text{C}$ placed on the line between them.

## Theory

A charge is in electrostatic equilibrium when the net electric force acting on it is zero:

$$
\vec{F}_{\text{net}} = \vec{0}
$$

The force magnitude between two point charges is given by Coulomb's law:

$$
F = k \frac{|q_i q_j|}{r^2}
$$

Since $q_1$ and $q_2$ are both positive, they repel the positive test charge $q_3$. If $q_3$ is placed between them, the force from $q_1$ acts away from $q_1$, and the force from $q_2$ acts away from $q_2$. These two forces are opposite in direction, so equilibrium is possible at one point between the charges.

## Step-by-Step Solution

Let the distance from $q_1$ to $q_3$ be $x$.

Then the distance from $q_3$ to $q_2$ is

$$
2 - x
$$

The magnitude of the force on $q_3$ due to $q_1$ is

$$
F_{13} = k \frac{q_1 q_3}{x^2}
$$

The magnitude of the force on $q_3$ due to $q_2$ is

$$
F_{23} = k \frac{q_2 q_3}{(2-x)^2}
$$

At equilibrium,

$$
F_{13} = F_{23}
$$

Substituting the values $q_1 = 4$, $q_2 = 9$, and $q_3 = 1$ gives

$$
k \frac{4 \cdot 1}{x^2} = k \frac{9 \cdot 1}{(2-x)^2}
$$

Cancel $k$ and $q_3$:

$$
\frac{4}{x^2} = \frac{9}{(2-x)^2}
$$

Take the positive square root of both sides:

$$
\frac{2}{x} = \frac{3}{2-x}
$$

Now solve for $x$:

$$
2(2-x) = 3x
$$

$$
4 - 2x = 3x
$$

$$
4 = 5x
$$

$$
x = \frac{4}{5} = 0.8\ \text{m}
$$

Thus the equilibrium point is $0.8\ \text{m}$ from $q_1$.

The distance from $q_2$ is

$$
2 - 0.8 = 1.2\ \text{m}
$$

## Final Result

The equilibrium position is

$$
x = 0.8\ \text{m}
$$

from the charge $q_1 = +4\ \text{C}$, or equivalently

$$
1.2\ \text{m}
$$

from the charge $q_2 = +9\ \text{C}$.

## Interpretation

The equilibrium point lies closer to the smaller charge.

This result is physically consistent: the stronger charge $q_2 = +9\ \text{C}$ produces a larger repulsive force, so the test charge must be farther from it and closer to the weaker charge $q_1 = +4\ \text{C}$ in order for the forces to balance.

The equilibrium exists only between the two charges, where the two repulsive forces act in opposite directions.
