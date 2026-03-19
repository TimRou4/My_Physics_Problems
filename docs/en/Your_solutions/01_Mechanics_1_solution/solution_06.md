# Task 06 - Position from a Variable Velocity Function

## Problem Statement

An object's velocity is given by

$$
v(t) = t^2 + 2t - 5
$$

The object is at position

$$
x(0) = 4
$$

Determine:

1. The position function $x(t)$.
2. The position at time $t=3$.
3. The acceleration at time $t=3$.

## Theory

Velocity is the derivative of position:

$$
v(t) = \frac{dx}{dt}
$$

Therefore the position function is found by integration. The acceleration is the derivative of velocity:

$$
a(t) = \frac{dv}{dt}
$$

## Step-by-Step Solution

### 1. Find the position function

Since

$$
\frac{dx}{dt} = t^2 + 2t - 5
$$

integrate with respect to $t$:

$$
x(t) = \int (t^2 + 2t - 5)\,dt
$$

$$
x(t) = \frac{t^3}{3} + t^2 - 5t + C
$$

Use the initial condition $x(0)=4$:

$$
x(0) = \frac{0^3}{3} + 0^2 - 5 \cdot 0 + C = 4
$$

Thus,

$$
C = 4
$$

So the position function is

$$
x(t) = \frac{t^3}{3} + t^2 - 5t + 4
$$

### 2. Position at $t=3$

Substitute $t=3$:

$$
x(3) = \frac{3^3}{3} + 3^2 - 5 \cdot 3 + 4
$$

$$
x(3) = \frac{27}{3} + 9 - 15 + 4
$$

$$
x(3) = 9 + 9 - 15 + 4
$$

$$
x(3) = 7
$$

### 3. Acceleration

Differentiate the velocity:

$$
a(t) = \frac{dv}{dt} = \frac{d}{dt}(t^2 + 2t - 5)
$$

$$
a(t) = 2t + 2
$$

Now evaluate at $t=3$:

$$
a(3) = 2 \cdot 3 + 2 = 8
$$

## Final Result

The position function is

$$
x(t) = \frac{t^3}{3} + t^2 - 5t + 4
$$

The position at $t=3$ is

$$
x(3) = 7
$$

The acceleration at $t=3$ is

$$
a(3) = 8
$$

## Interpretation

The velocity is a quadratic function, so the acceleration is linear in time. Although the object starts at position $4$, its velocity is initially negative because $v(0) = -5$. By $t=3$, the object has position $7$ and a positive acceleration of $8$, meaning its velocity is increasing at that instant.
