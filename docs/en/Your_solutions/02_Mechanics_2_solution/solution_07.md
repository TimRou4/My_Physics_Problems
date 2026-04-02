# Task 07 - Dynamics with Friction

## Problem Statement

A block of mass $5 \, \mathrm{kg}$ is placed on top of a block of mass $10 \, \mathrm{kg}$. A horizontal force of $45 \, \mathrm{N}$ is applied to the $10 \, \mathrm{kg}$ block. The $5 \, \mathrm{kg}$ block is tied to the wall. The coefficient of kinetic friction between all moving surfaces is $0.2$.

Determine the acceleration of the $10 \, \mathrm{kg}$ block.

## Theory

The lower block experiences two friction forces opposing its motion:

1. Kinetic friction from the upper block sliding relative to it.
2. Kinetic friction from the floor.

The kinetic friction magnitude is

$$
f_k = \mu_k N
$$

Newton's second law for the lower block is

$$
\sum F_x = ma
$$

## Step-by-Step Solution

Given:
- upper block mass: $m_1 = 5 \, \mathrm{kg}$
- lower block mass: $m_2 = 10 \, \mathrm{kg}$
- applied force: $F = 45 \, \mathrm{N}$
- coefficient of kinetic friction: $\mu_k = 0.2$
- gravitational acceleration: $g = 9.81 \, \mathrm{m/s^2}$

### 1. Friction between the two blocks

The upper block is tied to the wall, so the lower block slides beneath it. Therefore the friction between them is kinetic.

The normal force between the two blocks is

$$
N_{12} = m_1 g
$$

$$
N_{12} = 5 \cdot 9.81 = 49.05 \, \mathrm{N}
$$

Hence the friction magnitude is

$$
f_{12} = \mu_k N_{12}
$$

$$
f_{12} = 0.2 \cdot 49.05 = 9.81 \, \mathrm{N}
$$

This force acts to the left on the lower block.

### 2. Friction between the lower block and the floor

The floor supports both blocks, so the normal force from the floor is

$$
N_{\text{floor}} = (m_1 + m_2)g
$$

$$
N_{\text{floor}} = (5 + 10) \cdot 9.81 = 147.15 \, \mathrm{N}
$$

Thus the floor friction is

$$
f_{\text{floor}} = \mu_k N_{\text{floor}}
$$

$$
f_{\text{floor}} = 0.2 \cdot 147.15 = 29.43 \, \mathrm{N}
$$

This force also acts to the left.

### 3. Net force on the lower block

The total resistive force is

$$
f_{\text{total}} = f_{12} + f_{\text{floor}}
$$

$$
f_{\text{total}} = 9.81 + 29.43 = 39.24 \, \mathrm{N}
$$

The net horizontal force is

$$
F_{\text{net}} = 45 - 39.24 = 5.76 \, \mathrm{N}
$$

### 4. Acceleration of the lower block

Apply Newton's second law to the $10 \, \mathrm{kg}$ block:

$$
a = \frac{F_{\text{net}}}{m_2}
$$

$$
a = \frac{5.76}{10} = 0.576 \, \mathrm{m/s^2}
$$

## Final Result

The acceleration of the $10 \, \mathrm{kg}$ block is

$$
a \approx 0.58 \, \mathrm{m/s^2}
$$

to the right.

## Interpretation

Even though the applied force is $45 \, \mathrm{N}$, most of it is spent overcoming kinetic friction. The friction from the upper block and the floor together leave only a small net force, so the resulting acceleration is relatively small.
