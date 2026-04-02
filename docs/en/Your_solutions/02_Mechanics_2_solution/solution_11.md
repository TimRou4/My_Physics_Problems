# Task 11 - Dynamics with a Time-Dependent Force

## Problem Statement

A particle of mass $m = 3 \, \mathrm{kg}$ moves under the time-dependent force

$$
\vec F(t) = (15t,\; 3t - 12,\; -6t^2) \, \mathrm{N}
$$

The initial conditions are

$$
\vec r(0) = (5,\; 2,\; -3) \, \mathrm{m}
$$

and

$$
\vec v(0) = (2,\; 0,\; 1) \, \mathrm{m/s}
$$

Determine the time dependence of the velocity and position.

## Theory

Newton's second law gives

$$
\vec a(t) = \frac{\vec F(t)}{m}
$$

Velocity is obtained by integrating acceleration:

$$
\vec v(t) = \vec v(0) + \int_0^t \vec a(\tau)\,d\tau
$$

Position is obtained by integrating velocity:

$$
\vec r(t) = \vec r(0) + \int_0^t \vec v(\tau)\,d\tau
$$

Because the motion is given in Cartesian components, each component can be treated independently.

## Step-by-Step Solution

### 1. Acceleration

Divide the force by the mass $m = 3$:

$$
\vec a(t) = \frac{1}{3}(15t,\; 3t - 12,\; -6t^2)
$$

Thus,

$$
\vec a(t) = (5t,\; t - 4,\; -2t^2)
$$

### 2. Velocity

Integrate each component and apply the initial velocity.

#### $x$ component

$$
a_x = 5t
$$

Integrate:

$$
v_x(t) = \int 5t\,dt = \frac{5}{2}t^2 + C_x
$$

Use $v_x(0) = 2$:

$$
C_x = 2
$$

Hence,

$$
v_x(t) = 2 + \frac{5}{2}t^2
$$

#### $y$ component

$$
a_y = t - 4
$$

Integrate:

$$
v_y(t) = \int (t - 4)\,dt = \frac{1}{2}t^2 - 4t + C_y
$$

Use $v_y(0) = 0$:

$$
C_y = 0
$$

So,

$$
v_y(t) = \frac{1}{2}t^2 - 4t
$$

#### $z$ component

$$
a_z = -2t^2
$$

Integrate:

$$
v_z(t) = \int -2t^2\,dt = -\frac{2}{3}t^3 + C_z
$$

Use $v_z(0) = 1$:

$$
C_z = 1
$$

Thus,

$$
v_z(t) = 1 - \frac{2}{3}t^3
$$

Therefore,

$$
\vec v(t) = \left(2 + \frac{5}{2}t^2,\; \frac{1}{2}t^2 - 4t,\; 1 - \frac{2}{3}t^3\right)
$$

### 3. Position

Integrate each velocity component and apply the initial position.

#### $x$ component

$$
x(t) = \int \left(2 + \frac{5}{2}t^2\right) dt
$$

$$
x(t) = 2t + \frac{5}{6}t^3 + C_1
$$

Use $x(0) = 5$:

$$
C_1 = 5
$$

Hence,

$$
x(t) = 5 + 2t + \frac{5}{6}t^3
$$

#### $y$ component

$$
y(t) = \int \left(\frac{1}{2}t^2 - 4t\right) dt
$$

$$
y(t) = \frac{1}{6}t^3 - 2t^2 + C_2
$$

Use $y(0) = 2$:

$$
C_2 = 2
$$

So,

$$
y(t) = 2 + \frac{1}{6}t^3 - 2t^2
$$

#### $z$ component

$$
z(t) = \int \left(1 - \frac{2}{3}t^3\right) dt
$$

$$
z(t) = t - \frac{1}{6}t^4 + C_3
$$

Use $z(0) = -3$:

$$
C_3 = -3
$$

Thus,

$$
z(t) = -3 + t - \frac{1}{6}t^4
$$

Therefore,

$$
\vec r(t) = \left(5 + 2t + \frac{5}{6}t^3,\; 2 + \frac{1}{6}t^3 - 2t^2,\; -3 + t - \frac{1}{6}t^4\right)
$$

## Final Result

The velocity is

$$
\vec v(t) = \left(2 + \frac{5}{2}t^2,\; \frac{1}{2}t^2 - 4t,\; 1 - \frac{2}{3}t^3\right)
$$

The position is

$$
\vec r(t) = \left(5 + 2t + \frac{5}{6}t^3,\; 2 + \frac{1}{6}t^3 - 2t^2,\; -3 + t - \frac{1}{6}t^4\right)
$$

## Interpretation

Because the force depends explicitly on time, the acceleration also changes with time. The resulting motion is polynomial in $t$, with different behavior in each coordinate direction. The $x$ motion accelerates positively, the $y$ motion initially trends downward because of the constant negative term in the force, and the $z$ motion eventually decreases strongly because of the cubic term in velocity.
