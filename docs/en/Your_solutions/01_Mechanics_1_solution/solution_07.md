# Task 07 - Elimination of Time and Interpretation of Acceleration

## Problem Statement

A motion is given parametrically by

$$
x(t) = 2t^2, \qquad y(t) = 3t^3
$$

Required:

1. Eliminate the parameter $t$.
2. Describe the trajectory.
3. Calculate $\vec{v}(t)$ and $|\vec{v}(t)|$.
4. Calculate $\vec{a}(t)$ and $|\vec{a}(t)|$.
5. Determine whether the acceleration is constant.

## Theory

A parametric curve can often be rewritten in Cartesian form by eliminating the parameter. The velocity and acceleration vectors are obtained by differentiation:

$$
\vec{v}(t) = \left( \frac{dx}{dt}, \frac{dy}{dt} \right)
$$

$$
\vec{a}(t) = \left( \frac{d^2x}{dt^2}, \frac{d^2y}{dt^2} \right)
$$

The magnitudes are

$$
|\vec{v}(t)| = \sqrt{\left( \frac{dx}{dt} \right)^2 + \left( \frac{dy}{dt} \right)^2}
$$

$$
|\vec{a}(t)| = \sqrt{\left( \frac{d^2x}{dt^2} \right)^2 + \left( \frac{d^2y}{dt^2} \right)^2}
$$

## Step-by-Step Solution

### 1. Eliminate the parameter

From

$$
x = 2t^2
$$

it follows that

$$
t^2 = \frac{x}{2}
$$

Since

$$
y = 3t^3
$$

square both sides to eliminate the sign of $t$:

$$
y^2 = 9t^6
$$

But

$$
t^6 = (t^2)^3 = \left( \frac{x}{2} \right)^3
$$

Therefore,

$$
y^2 = 9 \left( \frac{x}{2} \right)^3
$$

$$
y^2 = \frac{9}{8}x^3
$$

This is the Cartesian equation of the trajectory.

Equivalently, the two branches can be written as

$$
y = \pm \frac{3}{2\sqrt{2}} x^{3/2}, \qquad x \geq 0
$$

### 2. Description of the trajectory

Because

$$
x = 2t^2 \geq 0
$$

the motion is confined to the right half-plane. The curve has a cusp at the origin. For positive $t$, the point lies on the upper branch with $y>0$. For negative $t$, it lies on the lower branch with $y<0$.

Thus the trajectory is a semicubical parabola.

### 3. Velocity vector and speed

Differentiate the coordinate functions:

$$
\frac{dx}{dt} = 4t
$$

$$
\frac{dy}{dt} = 9t^2
$$

Hence,

$$
\vec{v}(t) = \langle 4t, 9t^2 \rangle
$$

The speed is

$$
|\vec{v}(t)| = \sqrt{(4t)^2 + (9t^2)^2}
$$

$$
|\vec{v}(t)| = \sqrt{16t^2 + 81t^4}
$$

Factor out $t^2$:

$$
|\vec{v}(t)| = \sqrt{t^2(16 + 81t^2)}
$$

$$
|\vec{v}(t)| = |t|\sqrt{16 + 81t^2}
$$

### 4. Acceleration vector and magnitude

Differentiate the velocity components:

$$
\frac{d^2x}{dt^2} = 4
$$

$$
\frac{d^2y}{dt^2} = 18t
$$

Therefore,

$$
\vec{a}(t) = \langle 4, 18t \rangle
$$

Its magnitude is

$$
|\vec{a}(t)| = \sqrt{4^2 + (18t)^2}
$$

$$
|\vec{a}(t)| = \sqrt{16 + 324t^2}
$$

### 5. Is the acceleration constant?

The vector acceleration is

$$
\vec{a}(t) = \langle 4, 18t \rangle
$$

Its $x$-component is constant, but its $y$-component depends on time. Therefore the acceleration vector is not constant.

Also, its magnitude

$$
|\vec{a}(t)| = \sqrt{16 + 324t^2}
$$

depends on $t$, so the magnitude is not constant either.

## Final Result

The parameter-free equation of the trajectory is

$$
y^2 = \frac{9}{8}x^3
$$

The velocity vector and speed are

$$
\vec{v}(t) = \langle 4t, 9t^2 \rangle
$$

$$
|\vec{v}(t)| = |t|\sqrt{16 + 81t^2}
$$

The acceleration vector and its magnitude are

$$
\vec{a}(t) = \langle 4, 18t \rangle
$$

$$
|\vec{a}(t)| = \sqrt{16 + 324t^2}
$$

The acceleration is **not constant**.

## Interpretation

The trajectory has a cusp at the origin, where the motion changes branch. The point moves in the fourth quadrant for $t<0$, passes through the origin at $t=0$, and then moves into the first quadrant for $t>0$. The acceleration is time-dependent because the vertical component grows linearly with $t$. Therefore the motion is not uniformly accelerated in the plane.
