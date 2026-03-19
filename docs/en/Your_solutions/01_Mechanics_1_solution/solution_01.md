# Task 01 - Projectile Motion

## Problem Statement

A projectile is launched from ground level with initial speed $v_0 = 100 \text{ m/s}$ at an angle $\theta = 37^\circ$ above the horizontal. Air resistance is neglected.

Required:

1. Derive the differential equations of motion in the horizontal and vertical directions.
2. Determine the time of flight.
3. Determine the maximum height.
4. Determine the range.

## Theory

For projectile motion without air resistance, the only force acting after launch is gravity.

In Cartesian coordinates:

- the $x$-axis is horizontal,
- the $y$-axis is vertical and positive upward.

The acceleration vector is constant:

$$
\vec{a} = (0, -g)
$$

with

$$
g = 9.81 \text{ m/s}^2
$$

The initial velocity components are

$$
v_{0x} = v_0 \cos\theta
$$

$$
v_{0y} = v_0 \sin\theta
$$

## Step-by-Step Solution

### 1. Differential equations of motion

Newton's second law gives constant acceleration in each direction:

$$
\frac{d^2 x}{dt^2} = 0
$$

$$
\frac{d^2 y}{dt^2} = -g
$$

The initial conditions are

$$
x(0) = 0, \qquad y(0) = 0
$$

$$
\frac{dx}{dt}(0) = v_0 \cos\theta, \qquad \frac{dy}{dt}(0) = v_0 \sin\theta
$$

Integrating once gives the velocity components:

$$
v_x(t) = \frac{dx}{dt} = v_0 \cos\theta
$$

$$
v_y(t) = \frac{dy}{dt} = v_0 \sin\theta - gt
$$

Integrating again gives the position functions:

$$
x(t) = v_0 \cos\theta \, t
$$

$$
y(t) = v_0 \sin\theta \, t - \frac{1}{2} g t^2
$$

For the given data,

$$
v_{0x} = 100 \cos 37^\circ \approx 79.86 \text{ m/s}
$$

$$
v_{0y} = 100 \sin 37^\circ \approx 60.18 \text{ m/s}
$$

### 2. Time of flight

The projectile lands when it returns to the ground, so $y(T) = 0$.

Using the vertical position equation:

$$
0 = v_0 \sin\theta \, T - \frac{1}{2} g T^2
$$

Factor out $T$:

$$
T \left( v_0 \sin\theta - \frac{1}{2} gT \right) = 0
$$

The solution $T = 0$ corresponds to launch. The physical landing time is

$$
T = \frac{2 v_0 \sin\theta}{g}
$$

Substituting the data:

$$
T = \frac{2 \cdot 100 \sin 37^\circ}{9.81} \approx 12.27 \text{ s}
$$

### 3. Maximum height

At the highest point, the vertical velocity is zero:

$$
v_y(t_H) = v_0 \sin\theta - gt_H = 0
$$

Hence,

$$
t_H = \frac{v_0 \sin\theta}{g}
$$

The maximum height is obtained by substituting this time into $y(t)$:

$$
H_{\max} = v_0 \sin\theta \cdot \frac{v_0 \sin\theta}{g} - \frac{1}{2} g \left( \frac{v_0 \sin\theta}{g} \right)^2
$$

After simplification,

$$
H_{\max} = \frac{v_0^2 \sin^2\theta}{2g}
$$

Numerically,

$$
H_{\max} = \frac{100^2 \sin^2 37^\circ}{2 \cdot 9.81} \approx 184.60 \text{ m}
$$

### 4. Range

The horizontal range is the horizontal distance traveled during the full flight time:

$$
R = x(T) = v_0 \cos\theta \cdot T
$$

Substitute the expression for $T$:

$$
R = v_0 \cos\theta \cdot \frac{2 v_0 \sin\theta}{g}
$$

Using the identity $2 \sin\theta \cos\theta = \sin 2\theta$,

$$
R = \frac{v_0^2 \sin 2\theta}{g}
$$

Numerically,

$$
R = \frac{100^2 \sin 74^\circ}{9.81} \approx 979.88 \text{ m}
$$

## Final Result

The equations of motion are

$$
\frac{d^2 x}{dt^2} = 0, \qquad \frac{d^2 y}{dt^2} = -g
$$

with solutions

$$
x(t) = 100 \cos 37^\circ \, t
$$

$$
y(t) = 100 \sin 37^\circ \, t - \frac{1}{2} gt^2
$$

The numerical results are

$$
T \approx 12.27 \text{ s}
$$

$$
H_{\max} \approx 184.60 \text{ m}
$$

$$
R \approx 979.88 \text{ m}
$$

## Interpretation

The horizontal motion is uniform because there is no horizontal acceleration. The vertical motion is uniformly accelerated downward due to gravity. The projectile rises until its vertical velocity becomes zero, then falls symmetrically back to the ground. The range is much larger than the maximum height because the launch angle is moderate rather than steep.
