# Task 12 - Work and Energy with a Constant Force

## Problem Statement

A constant force acts on a body of mass $m = 2 \, \mathrm{kg}$:

$$
\vec F = (6,\; 2) \, \mathrm{N}
$$

The initial conditions are

$$
\vec v(0) = (1,\; -1) \, \mathrm{m/s}
$$

and

$$
\vec r(0) = (0,\; 0) \, \mathrm{m}
$$

Required:
1. Determine $\vec a(t)$.
2. Determine $\vec v(t)$.
3. Determine $\vec r(t)$.
4. Draw the trajectory.
5. Calculate the work done by the force at $t = 3 \, \mathrm{s}$.
6. Verify the work-energy theorem.

## Theory

For a constant force, the acceleration is constant:

$$
\vec a = \frac{\vec F}{m}
$$

Velocity is obtained from

$$
\vec v(t) = \vec v_0 + \vec a t
$$

Position is obtained from

$$
\vec r(t) = \vec r_0 + \vec v_0 t + \frac{1}{2}\vec a t^2
$$

The work done by a constant force over displacement $\Delta \vec r$ is

$$
W = \vec F \cdot \Delta \vec r
$$

The work-energy theorem states

$$
W = \Delta K = K_f - K_i
$$

## Step-by-Step Solution

### 1. Acceleration

Given

$$
\vec F = (6,\; 2) \, \mathrm{N}
$$

and

$$
m = 2 \, \mathrm{kg}
$$

the acceleration is

$$
\vec a = \frac{\vec F}{m} = \left(\frac{6}{2},\; \frac{2}{2}\right)
$$

Thus,

$$
\vec a(t) = (3,\; 1) \, \mathrm{m/s^2}
$$

This is constant in time.

### 2. Velocity

Use

$$
\vec v(t) = \vec v_0 + \vec a t
$$

with

$$
\vec v_0 = (1,\; -1)
$$

Therefore,

$$
\vec v(t) = (1,\; -1) + (3,\; 1)t
$$

Hence,

$$
\vec v(t) = (1 + 3t,\; -1 + t)
$$

### 3. Position

Use

$$
\vec r(t) = \vec r_0 + \vec v_0 t + \frac{1}{2}\vec a t^2
$$

with $\vec r_0 = (0,\; 0)$:

$$
\vec r(t) = (1,\; -1)t + \frac{1}{2}(3,\; 1)t^2
$$

Thus,

$$
\vec r(t) = \left(t + \frac{3}{2}t^2,\; -t + \frac{1}{2}t^2\right)
$$

### 4. Trajectory

The motion is described parametrically by

$$
x(t) = t + \frac{3}{2}t^2
$$

$$
y(t) = -t + \frac{1}{2}t^2
$$

To eliminate $t$, form two combinations:

$$
x + y = 2t^2
$$

and

$$
x - 3y = 4t
$$

Therefore,

$$
(x - 3y)^2 = 16t^2 = 8(x + y)
$$

This is the Cartesian equation of the trajectory, which is a parabola.

### 5. Work done by the force at $t = 3 \, \mathrm{s}$

First compute the position at $t = 3$:

$$
x(3) = 3 + \frac{3}{2}\cdot 9 = 3 + 13.5 = 16.5 \, \mathrm{m}
$$

$$
y(3) = -3 + \frac{1}{2}\cdot 9 = -3 + 4.5 = 1.5 \, \mathrm{m}
$$

So the displacement from the origin is

$$
\Delta \vec r = (16.5,\; 1.5)
$$

The work is

$$
W = \vec F \cdot \Delta \vec r
$$

$$
W = (6,\; 2) \cdot (16.5,\; 1.5)
$$

$$
W = 6 \cdot 16.5 + 2 \cdot 1.5
$$

$$
W = 99 + 3 = 102 \, \mathrm{J}
$$

### 6. Verification using the work-energy theorem

Initial kinetic energy:

$$
K_i = \frac{1}{2}m(v_{x0}^2 + v_{y0}^2)
$$

$$
K_i = \frac{1}{2}\cdot 2 \cdot (1^2 + (-1)^2)
$$

$$
K_i = 1 \cdot (1 + 1) = 2 \, \mathrm{J}
$$

Final velocity at $t = 3$:

$$
\vec v(3) = (1 + 3\cdot 3,\; -1 + 3) = (10,\; 2)
$$

Final kinetic energy:

$$
K_f = \frac{1}{2}m(v_x^2 + v_y^2)
$$

$$
K_f = \frac{1}{2}\cdot 2 \cdot (10^2 + 2^2)
$$

$$
K_f = 1 \cdot (100 + 4) = 104 \, \mathrm{J}
$$

Therefore,

$$
\Delta K = K_f - K_i = 104 - 2 = 102 \, \mathrm{J}
$$

Thus,

$$
W = \Delta K
$$

which confirms the work-energy theorem.

## Final Result

The acceleration is

$$
\vec a(t) = (3,\; 1) \, \mathrm{m/s^2}
$$

The velocity is

$$
\vec v(t) = (1 + 3t,\; -1 + t)
$$

The position is

$$
\vec r(t) = \left(t + \frac{3}{2}t^2,\; -t + \frac{1}{2}t^2\right)
$$

The trajectory is the parabola

$$
(x - 3y)^2 = 8(x + y)
$$

The work done by the force at $t = 3 \, \mathrm{s}$ is

$$
W = 102 \, \mathrm{J}
$$

The work-energy theorem is satisfied because

$$
\Delta K = 102 \, \mathrm{J}
$$

## Interpretation

A constant force produces constant acceleration, so the motion in each coordinate is quadratic in time. Although the force is constant, the path is not a straight line because the body already has an initial velocity not aligned with the force. The equality between work and kinetic-energy change confirms the internal consistency of the solution.
