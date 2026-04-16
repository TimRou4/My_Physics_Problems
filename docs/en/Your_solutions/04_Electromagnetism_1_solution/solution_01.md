# Task 01 - Coulomb's Law

## Problem Statement

Four point charges of $+1.0\ \text{C}$ are placed at the corners of a square of side length $a = 1.0\ \text{m}$. A charge of $-2.0\ \text{C}$ is placed at the center of the square.

Determine the magnitude and direction of the net electric force acting on the central charge.

## Theory

The magnitude of the electrostatic force between two point charges is given by Coulomb's law:

$$
F = k \frac{|q_1 q_2|}{r^2}
$$

where

$$
k = 8.99 \times 10^9\ \text{N m}^2/\text{C}^2
$$

is Coulomb's constant, $q_1$ and $q_2$ are the interacting charges, and $r$ is the distance between them.

Because force is a vector quantity, the total force on the charge at the center must be found by vector addition of the four individual forces.

## Step-by-Step Solution

The distance from the center of a square to any corner is half of the diagonal:

$$
r = \frac{a\sqrt{2}}{2}
$$

For $a = 1.0\ \text{m}$,

$$
r = \frac{1.0\sqrt{2}}{2} = \frac{1}{\sqrt{2}}\ \text{m}
$$

The magnitude of the force exerted by one corner charge on the central charge is

$$
F_1 = k \frac{|(+1.0)(-2.0)|}{r^2}
$$

Since

$$
r^2 = \left(\frac{1}{\sqrt{2}}\right)^2 = \frac{1}{2}
$$

it follows that

$$
F_1 = k \frac{2}{1/2} = 4k
$$

Thus,

$$
F_1 = 4(8.99 \times 10^9) = 3.596 \times 10^{10}\ \text{N}
$$

Each individual force is directed from the center toward a corner, because the central charge is negative and each corner charge is positive, so the interaction is attractive.

However, the four corner charges are arranged symmetrically. For every force directed toward one corner, there is an equal force directed toward the opposite corner. These opposite forces cancel pairwise.

This can be expressed as

$$
\vec{F}_{\text{net}} = \vec{F}_1 + \vec{F}_2 + \vec{F}_3 + \vec{F}_4 = \vec{0}
$$

Therefore, the net force on the central charge is zero.

## Final Result

$$
|\vec{F}_{\text{net}}| = 0\ \text{N}
$$

The direction is undefined, because the net force vector is zero.

## Interpretation

Although each corner charge exerts a large attractive force on the charge at the center, the square geometry is perfectly symmetric. The vector sum of the four forces cancels exactly.

The charge at the center is therefore in mechanical equilibrium under the action of these four electrostatic forces.
