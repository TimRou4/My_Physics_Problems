# Task 05 - Relative Velocity in a River

## Problem Statement

A river flows east with speed

$$
2 \text{ m/s}
$$

A boat can travel at speed

$$
5 \text{ m/s}
$$

relative to the water. The boat wants to move directly north across the river.

Determine:

1. The direction in which the boat must head.
2. The time required to cross a river of width $200 \text{ m}$.

## Theory

Relative velocities add as vectors:

$$
\vec{v}_{\text{boat, ground}} = \vec{v}_{\text{boat, water}} + \vec{v}_{\text{water, ground}}
$$

To move directly north relative to the ground, the east-west component of the boat's ground velocity must be zero. Therefore the westward component of the boat's velocity relative to the water must exactly cancel the eastward river current.

## Step-by-Step Solution

Choose axes:

- positive $x$ toward the east,
- positive $y$ toward the north.

The river velocity is

$$
\vec{v}_{\text{water, ground}} = \langle 2, 0 \rangle
$$

Let the boat's velocity relative to the water be

$$
\vec{v}_{\text{boat, water}} = \langle u_x, u_y \rangle
$$

with magnitude

$$
\sqrt{u_x^2 + u_y^2} = 5
$$

### 1. Condition for going directly north

For the actual ground velocity to point due north, the horizontal component must vanish:

$$
u_x + 2 = 0
$$

Hence,

$$
u_x = -2
$$

This means the boat must aim westward.

Now use the magnitude condition:

$$
u_x^2 + u_y^2 = 25
$$

$$
(-2)^2 + u_y^2 = 25
$$

$$
4 + u_y^2 = 25
$$

$$
u_y^2 = 21
$$

$$
u_y = \sqrt{21}
$$

So the boat's velocity relative to the water is

$$
\vec{v}_{\text{boat, water}} = \langle -2, \sqrt{21} \rangle
$$

### 2. Heading angle

Let $\alpha$ be the angle west of north. Then

$$
\sin\alpha = \frac{2}{5}
$$

Therefore,

$$
\alpha = \sin^{-1}\left(\frac{2}{5}\right) \approx 23.58^\circ
$$

So the required heading is

$$
23.58^\circ \text{ west of north}
$$

### 3. Crossing time

Since the boat moves directly north relative to the ground, its northward speed is

$$
v_{\text{north}} = \sqrt{21} \text{ m/s}
$$

The crossing time is

$$
t = \frac{\text{width}}{\text{northward speed}} = \frac{200}{\sqrt{21}}
$$

Numerically,

$$
t \approx 43.64 \text{ s}
$$

## Final Result

The boat must head

$$
23.58^\circ \text{ west of north}
$$

The time to cross the $200 \text{ m}$ river is

$$
t = \frac{200}{\sqrt{21}} \approx 43.64 \text{ s}
$$

## Interpretation

The river current pushes the boat eastward, so the boat must aim upstream, that is, slightly west of north. The required correction angle is set by the need to cancel the river's horizontal velocity exactly. The crossing time depends only on the northward component of the boat's ground velocity.
