# Task 03 - Superposition Principle

## Problem Statement

Two waves are described by

$$
y_1(x,t) = A \sin(kx - \omega t)
$$

and

$$
y_2(x,t) = A \sin(kx + \omega t)
$$

Determine the equation of the resulting standing wave and identify the positions of the nodes.

## Theory

The principle of superposition states that the resultant displacement is the sum of the individual displacements:

$$
y(x,t) = y_1(x,t) + y_2(x,t)
$$

A useful trigonometric identity is

$$
\sin(\alpha - \beta) + \sin(\alpha + \beta) = 2 \sin \alpha \cos \beta
$$

A standing wave is characterized by a spatial factor and a time factor. Nodes are positions where the displacement is always zero.

## Step-by-Step Solution

### 1. Add the two waves

$$
y(x,t) = A \sin(kx - \omega t) + A \sin(kx + \omega t)
$$

Factor out $A$:

$$
y(x,t) = A \left[\sin(kx - \omega t) + \sin(kx + \omega t)\right]
$$

### 2. Apply the trigonometric identity

Let

$$
\alpha = kx
$$

and

$$
\beta = \omega t
$$

Then

$$
y(x,t) = 2A \sin(kx)\cos(\omega t)
$$

This is the equation of the standing wave.

### 3. Determine the nodes

Nodes occur where the spatial factor is zero:

$$
\sin(kx) = 0
$$

This happens when

$$
kx = n\pi
$$

where $n = 0, \pm 1, \pm 2, \dots$

Therefore,

$$
x = \frac{n\pi}{k}
$$

Using

$$
k = \frac{2\pi}{\lambda}
$$

we obtain

$$
x = \frac{n\pi}{2\pi/\lambda}
$$

$$
x = \frac{n\lambda}{2}
$$

## Final Result

The resulting standing wave is

$$
y(x,t) = 2A \sin(kx)\cos(\omega t)
$$

The nodes are located at

$$
x = \frac{n\lambda}{2}
$$

where $n = 0, \pm 1, \pm 2, \dots$

## Interpretation

The two original waves have the same amplitude, wavelength, and frequency, but travel in opposite directions. Their superposition produces a standing wave. At the node positions, destructive interference is permanent, so the displacement remains zero for all time.
