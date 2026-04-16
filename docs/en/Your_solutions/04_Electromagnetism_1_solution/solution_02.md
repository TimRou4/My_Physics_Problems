# Task 02 - Electric Potential

## Problem Statement

Point charges of $+1\ \text{C}$, $-2\ \text{C}$, $+3\ \text{C}$, and $-4\ \text{C}$ are placed at the corners of a square of side length $a = 1.0\ \text{m}$, in order.

Determine the electric potential at the center of the square.

## Theory

The electric potential due to a point charge is

$$
V = k \frac{q}{r}
$$

where $q$ is the charge and $r$ is the distance from the charge to the observation point.

Electric potential is a scalar quantity, so the total potential is obtained by simple algebraic addition:

$$
V_{\text{net}} = \sum_i V_i = k \sum_i \frac{q_i}{r_i}
$$

At the center of a square, all four corners are at the same distance from the center.

## Step-by-Step Solution

The distance from the center of the square to any corner is

$$
r = \frac{a\sqrt{2}}{2}
$$

For $a = 1.0\ \text{m}$,

$$
r = \frac{1}{\sqrt{2}}\ \text{m}
$$

The total electric potential at the center is

$$
V_{\text{net}} = k \left( \frac{+1}{r} + \frac{-2}{r} + \frac{+3}{r} + \frac{-4}{r} \right)
$$

Since all denominators are the same, factor out $k/r$:

$$
V_{\text{net}} = \frac{k}{r} \left( 1 - 2 + 3 - 4 \right)
$$

The algebraic sum of the charges is

$$
1 - 2 + 3 - 4 = -2
$$

Therefore,

$$
V_{\text{net}} = \frac{k}{r}(-2)
$$

Substitute $r = 1/\sqrt{2}$:

$$
V_{\text{net}} = -2k \sqrt{2}
$$

Using $k = 8.99 \times 10^9\ \text{N m}^2/\text{C}^2$,

$$
V_{\text{net}} = -2(8.99 \times 10^9)\sqrt{2}
$$

$$
V_{\text{net}} \approx -2.54 \times 10^{10}\ \text{V}
$$

## Final Result

$$
V_{\text{center}} = -2k\sqrt{2} \approx -2.54 \times 10^{10}\ \text{V}
$$

## Interpretation

The electric potential at the center is negative because the total contribution of the negative charges is larger in magnitude than the total contribution of the positive charges.

Since electric potential is a scalar, the spatial directions of the charges do not affect the addition directly. Only the signs of the charges and their equal distances from the center determine the result.
