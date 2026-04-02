# Task 10 - Force Field and Power

## Problem Statement

A particle of mass $m = 0.5 \, \mathrm{kg}$ moves according to

$$
x = 5t^2 - t
$$

$$
y = 2t^3
$$

$$
z = -3t + 2
$$

Determine the time dependence of:
1. velocity,
2. momentum,
3. acceleration,
4. force,
5. power transferred by the field.

## Theory

The position vector is

$$
\vec r(t) = (x(t), y(t), z(t))
$$

The velocity is the time derivative of position:

$$
\vec v(t) = \frac{d\vec r}{dt}
$$

The acceleration is the time derivative of velocity:

$$
\vec a(t) = \frac{d\vec v}{dt}
$$

Momentum is

$$
\vec p(t) = m\vec v(t)
$$

Force is

$$
\vec F(t) = m\vec a(t)
$$

Power delivered by the force is

$$
P(t) = \vec F(t) \cdot \vec v(t)
$$

## Step-by-Step Solution

### 1. Velocity

Differentiate each coordinate with respect to time:

$$
v_x = \frac{dx}{dt} = 10t - 1
$$

$$
v_y = \frac{dy}{dt} = 6t^2
$$

$$
v_z = \frac{dz}{dt} = -3
$$

Therefore,

$$
\vec v(t) = (10t - 1,\; 6t^2,\; -3)
$$

### 2. Momentum

Using $m = 0.5 \, \mathrm{kg}$,

$$
\vec p(t) = 0.5 \vec v(t)
$$

Hence,

$$
\vec p(t) = \left(5t - 0.5,\; 3t^2,\; -1.5\right)
$$

### 3. Acceleration

Differentiate the velocity components:

$$
a_x = \frac{d}{dt}(10t - 1) = 10
$$

$$
a_y = \frac{d}{dt}(6t^2) = 12t
$$

$$
a_z = \frac{d}{dt}(-3) = 0
$$

Thus,

$$
\vec a(t) = (10,\; 12t,\; 0)
$$

### 4. Force

Use Newton's second law:

$$
\vec F(t) = m\vec a(t)
$$

$$
\vec F(t) = 0.5(10,\; 12t,\; 0)
$$

$$
\vec F(t) = (5,\; 6t,\; 0)
$$

### 5. Power

The power is the scalar product of force and velocity:

$$
P(t) = \vec F(t) \cdot \vec v(t)
$$

$$
P(t) = (5,\; 6t,\; 0) \cdot (10t - 1,\; 6t^2,\; -3)
$$

Compute the dot product:

$$
P(t) = 5(10t - 1) + 6t(6t^2) + 0 \cdot (-3)
$$

$$
P(t) = 50t - 5 + 36t^3
$$

Therefore,

$$
P(t) = 36t^3 + 50t - 5
$$

## Final Result

The velocity is

$$
\vec v(t) = (10t - 1,\; 6t^2,\; -3)
$$

The momentum is

$$
\vec p(t) = \left(5t - 0.5,\; 3t^2,\; -1.5\right)
$$

The acceleration is

$$
\vec a(t) = (10,\; 12t,\; 0)
$$

The force is

$$
\vec F(t) = (5,\; 6t,\; 0)
$$

The power is

$$
P(t) = 36t^3 + 50t - 5
$$

## Interpretation

The particle does not move with constant acceleration because the $y$ component of the acceleration depends on time. The force field therefore varies in time through the $y$ direction. The power is not constant, which means the rate of energy transfer changes throughout the motion.
