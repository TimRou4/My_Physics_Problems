# Task 03 - Conservation of Energy in a Pendulum

## Problem Statement

A pendulum of length $1.0 \, \mathrm{m}$ is released from an initial angle of $15^\circ$.

Determine the speed of the pendulum bob at the bottom of the swing.

## Theory

Mechanical energy is conserved if friction and air resistance are neglected.

At the release point, the pendulum has gravitational potential energy relative to the lowest point. At the bottom, this energy has been converted into kinetic energy.

Thus,

$$
mgh = \frac{1}{2}mv^2
$$

The vertical drop from angle $\theta$ is

$$
h = L(1 - \cos\theta)
$$

Substituting into the energy equation gives

$$
mgL(1 - \cos\theta) = \frac{1}{2}mv^2
$$

The mass cancels, so

$$
v = \sqrt{2gL(1 - \cos\theta)}
$$

## Step-by-Step Solution

Given:
- $L = 1.0 \, \mathrm{m}$
- $\theta = 15^\circ$
- $g = 9.81 \, \mathrm{m/s^2}$

### 1. Compute the vertical height drop

$$
h = L(1 - \cos\theta)
$$

$$
h = 1.0(1 - \cos 15^\circ)
$$

Using

$$
\cos 15^\circ \approx 0.9659
$$

gives

$$
h \approx 1.0(1 - 0.9659) = 0.0341 \, \mathrm{m}
$$

### 2. Apply conservation of energy

$$
mgh = \frac{1}{2}mv^2
$$

After canceling $m$,

$$
v = \sqrt{2gh}
$$

Substitute the value of $h$:

$$
v = \sqrt{2 \cdot 9.81 \cdot 0.0341}
$$

$$
v \approx \sqrt{0.6685}
$$

$$
v \approx 0.818 \, \mathrm{m/s}
$$

## Final Result

The speed of the pendulum bob at the bottom is

$$
v \approx 0.82 \, \mathrm{m/s}
$$

## Interpretation

The initial angular displacement is relatively small, so the bob starts only slightly above the lowest point. Consequently, the gained speed is modest. The result depends only on the conversion of gravitational potential energy into kinetic energy.
