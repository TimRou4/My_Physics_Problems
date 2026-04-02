# Task 04 - Energy and Momentum

## Problem Statement

A block of mass $0.5 \, \mathrm{kg}$ slides down a frictionless track from a height of $3.0 \, \mathrm{m}$. At the bottom, it collides and sticks to a second block of mass $1.5 \, \mathrm{kg}$, initially at rest.

Determine the speed of the combined mass immediately after the collision.

## Theory

This problem has two stages:

1. Conversion of gravitational potential energy into kinetic energy during the descent.
2. A perfectly inelastic collision at the bottom.

For the descent,

$$
mgh = \frac{1}{2}mv^2
$$

so the speed before collision is

$$
v_1 = \sqrt{2gh}
$$

For the collision, momentum is conserved:

$$
m_1 v_1 + m_2 v_2 = (m_1 + m_2)v_f
$$

Since the second block is initially at rest, $v_2 = 0$, so

$$
v_f = \frac{m_1 v_1}{m_1 + m_2}
$$

## Step-by-Step Solution

Given:
- $m_1 = 0.5 \, \mathrm{kg}$
- $m_2 = 1.5 \, \mathrm{kg}$
- $h = 3.0 \, \mathrm{m}$
- $g = 9.81 \, \mathrm{m/s^2}$

### 1. Speed of the first block at the bottom

$$
v_1 = \sqrt{2gh}
$$

$$
v_1 = \sqrt{2 \cdot 9.81 \cdot 3.0}
$$

$$
v_1 = \sqrt{58.86}
$$

$$
v_1 \approx 7.67 \, \mathrm{m/s}
$$

### 2. Apply conservation of momentum

$$
v_f = \frac{m_1 v_1}{m_1 + m_2}
$$

$$
v_f = \frac{0.5 \cdot 7.67}{0.5 + 1.5}
$$

$$
v_f = \frac{3.835}{2.0}
$$

$$
v_f \approx 1.92 \, \mathrm{m/s}
$$

## Final Result

The speed of the combined mass immediately after the collision is

$$
v_f \approx 1.92 \, \mathrm{m/s}
$$

## Interpretation

The first block reaches the bottom with a relatively high speed because the descent is frictionless. During the collision, momentum is conserved, but the masses stick together, so kinetic energy is not conserved. The final speed is much smaller because the motion is shared by a larger total mass.
