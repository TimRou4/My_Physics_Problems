# Task 05 - Inelastic Collision

## Problem Statement

A runner of mass $70 \, \mathrm{kg}$ moving at $3 \, \mathrm{m/s}$ jumps onto a stationary cart of mass $140 \, \mathrm{kg}$.

Determine:
1. The final speed of the cart and runner together.
2. Whether kinetic energy is conserved.

## Theory

When two bodies stick together after collision, the collision is perfectly inelastic.

In such collisions:
- momentum is conserved,
- kinetic energy is generally not conserved.

The momentum conservation equation is

$$
m_1 v_1 + m_2 v_2 = (m_1 + m_2)v_f
$$

Since the cart is initially at rest, $v_2 = 0$, so

$$
v_f = \frac{m_1 v_1}{m_1 + m_2}
$$

## Step-by-Step Solution

Given:
- $m_1 = 70 \, \mathrm{kg}$
- $v_1 = 3 \, \mathrm{m/s}$
- $m_2 = 140 \, \mathrm{kg}$
- $v_2 = 0$

### 1. Final speed from momentum conservation

$$
v_f = \frac{m_1 v_1}{m_1 + m_2}
$$

$$
v_f = \frac{70 \cdot 3}{70 + 140}
$$

$$
v_f = \frac{210}{210}
$$

$$
v_f = 1.0 \, \mathrm{m/s}
$$

### 2. Initial kinetic energy

Only the runner initially has kinetic energy:

$$
K_i = \frac{1}{2}m_1 v_1^2
$$

$$
K_i = \frac{1}{2} \cdot 70 \cdot 3^2
$$

$$
K_i = 35 \cdot 9 = 315 \, \mathrm{J}
$$

### 3. Final kinetic energy

After the collision, the total mass is

$$
m_1 + m_2 = 210 \, \mathrm{kg}
$$

Thus,

$$
K_f = \frac{1}{2}(m_1 + m_2)v_f^2
$$

$$
K_f = \frac{1}{2} \cdot 210 \cdot 1^2 = 105 \, \mathrm{J}
$$

### 4. Compare initial and final kinetic energy

$$
K_i = 315 \, \mathrm{J}
$$

$$
K_f = 105 \, \mathrm{J}
$$

Therefore,

$$
K_f \neq K_i
$$

The loss of kinetic energy is

$$
\Delta K = K_f - K_i = 105 - 315 = -210 \, \mathrm{J}
$$

## Final Result

The final speed is

$$
v_f = 1.0 \, \mathrm{m/s}
$$

Kinetic energy is **not** conserved.

## Interpretation

The collision is perfectly inelastic because the runner and cart move together afterward. Momentum is conserved because external horizontal forces are neglected, but part of the kinetic energy is transformed into internal energy, deformation, sound, and heat. This is why the final kinetic energy is smaller than the initial one.
