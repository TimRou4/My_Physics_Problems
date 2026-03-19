# Task 10 - Kinematics of a Space Curve

## Problem Statement

A point moves according to

$$
\vec{r}(t) = (a \cos(\omega t), b \sin(\omega t), bt)
$$

where $a$, $b$, and $\omega$ are positive constants.

Required:

1. Find the equation of the trajectory.
2. Compute the path length from $t=0$ to $t=t_0$.
3. Provide a Python visualization and discuss special cases.

## Theory

A parametric space curve is described by its coordinate functions:

$$
x(t) = a \cos(\omega t)
$$

$$
y(t) = b \sin(\omega t)
$$

$$
z(t) = bt
$$

The velocity vector is

$$
\vec{v}(t) = \frac{d\vec{r}}{dt}
$$

The path length from $t=0$ to $t=t_0$ is

$$
s(t_0) = \int_0^{t_0} |\vec{v}(t)|\,dt
$$

## Step-by-Step Solution

### 1. Equation of the trajectory

From the first two coordinate equations,

$$
\frac{x}{a} = \cos(\omega t)
$$

$$
\frac{y}{b} = \sin(\omega t)
$$

Squaring and adding gives

$$
\frac{x^2}{a^2} + \frac{y^2}{b^2} = \cos^2(\omega t) + \sin^2(\omega t)
$$

$$
\frac{x^2}{a^2} + \frac{y^2}{b^2} = 1
$$

Thus the projection onto the $xy$-plane is an ellipse.

Now use

$$
z = bt
$$

to write

$$
t = \frac{z}{b}
$$

Substituting into the parametric equations gives

$$
x = a \cos\left(\frac{\omega z}{b}\right)
$$

$$
y = b \sin\left(\frac{\omega z}{b}\right)
$$

Therefore the point moves along an **elliptic helix** wrapped around the elliptical cylinder

$$
\frac{x^2}{a^2} + \frac{y^2}{b^2} = 1
$$

### 2. Velocity vector

Differentiate each component:

$$
\frac{dx}{dt} = -a\omega \sin(\omega t)
$$

$$
\frac{dy}{dt} = b\omega \cos(\omega t)
$$

$$
\frac{dz}{dt} = b
$$

Hence,

$$
\vec{v}(t) = \left( -a\omega \sin(\omega t), b\omega \cos(\omega t), b \right)
$$

### 3. Speed

The speed is

$$
|\vec{v}(t)| = \sqrt{a^2\omega^2 \sin^2(\omega t) + b^2\omega^2 \cos^2(\omega t) + b^2}
$$

Therefore the path length is

$$
s(t_0) = \int_0^{t_0} \sqrt{a^2\omega^2 \sin^2(\omega t) + b^2\omega^2 \cos^2(\omega t) + b^2}\,dt
$$

This is already a correct exact integral formula.

### 4. Reduction of the arc-length integral

Factor the terms containing $b$:

$$
s(t_0) = \int_0^{t_0} \sqrt{b^2(1+\omega^2) + \omega^2(a^2-b^2)\sin^2(\omega t)}\,dt
$$

Set

$$
u = \omega t
$$

Then

$$
dt = \frac{du}{\omega}
$$

and the limits change from $t=0$ and $t=t_0$ to $u=0$ and $u=\omega t_0$. Hence

$$
s(t_0) = \frac{1}{\omega}\int_0^{\omega t_0} \sqrt{b^2(1+\omega^2) + \omega^2(a^2-b^2)\sin^2 u}\,du
$$

In general this integral is not elementary. It can be written in terms of the incomplete elliptic integral of the second kind:

$$
s(t_0) = \frac{\sqrt{b^2(1+\omega^2)}}{\omega}
E\left(
\omega t_0 \,\middle|\, -\frac{\omega^2(a^2-b^2)}{b^2(1+\omega^2)}
\right)
$$

where $E(\phi \mid m)$ denotes the incomplete elliptic integral of the second kind.

### 5. Special case: circular helix

If

$$
a=b
$$

then the projection in the $xy$-plane is a circle, and the speed becomes constant:

$$
|\vec{v}(t)| = \sqrt{a^2\omega^2 + b^2}
$$

Thus the arc length simplifies to

$$
s(t_0) = t_0 \sqrt{a^2\omega^2 + b^2}
$$

This is the standard result for uniform motion along a circular helix.

### 6. Python visualization

The following Python script plots the trajectory in three dimensions.

```python
import numpy as np
import matplotlib.pyplot as plt

a = 3.0
b = 2.0
omega = 1.2
t0 = 12.0

t = np.linspace(0, t0, 1000)

x = a * np.cos(omega * t)
y = b * np.sin(omega * t)
z = b * t

fig = plt.figure(figsize=(8, 6))
ax = fig.add_subplot(111, projection="3d")

ax.plot(x, y, z, linewidth=2)

ax.set_xlabel("x")
ax.set_ylabel("y")
ax.set_zlabel("z")
ax.set_title("Elliptic Helix")

plt.show()
```

## Final Result

The trajectory is an elliptic helix given by

$$
x = a \cos\left(\frac{\omega z}{b}\right), \qquad
y = b \sin\left(\frac{\omega z}{b}\right)
$$

or equivalently by the elliptical-cylinder relation

$$
\frac{x^2}{a^2} + \frac{y^2}{b^2} = 1
$$

with vertical coordinate

$$
z = bt
$$

The velocity vector is

$$
\vec{v}(t) = \left( -a\omega \sin(\omega t), b\omega \cos(\omega t), b \right)
$$

The arc length from $0$ to $t_0$ is

$$
s(t_0) = \int_0^{t_0} \sqrt{a^2\omega^2 \sin^2(\omega t) + b^2\omega^2 \cos^2(\omega t) + b^2}\,dt
$$

and in general it is expressed using an incomplete elliptic integral of the second kind.

If $a=b$, then

$$
s(t_0) = t_0 \sqrt{a^2\omega^2 + b^2}
$$

## Interpretation

The motion combines periodic oscillation in the $x$ and $y$ directions with uniform growth in the $z$ direction. Because of this, the point does not stay in a plane. Instead, it winds upward around an elliptical cylinder.

Important special cases:

1. If $a=b$, the curve becomes a circular helix.
2. If $\omega$ is very small, the horizontal oscillation is slow and the curve resembles a gently twisted line.
3. Larger $\omega$ produces tighter winding around the cylinder.
4. Larger $b$ increases both the vertical rise rate and the size of the ellipse in the $y$-direction.

This curve is a natural three-dimensional extension of planar harmonic motion.










