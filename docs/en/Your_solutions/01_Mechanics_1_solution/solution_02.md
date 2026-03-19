# Task 02 - Range Optimization

## Problem Statement

For projectile motion with fixed initial speed $v_0$, show analytically that the range

$$
R(\theta) = \frac{v_0^2 \sin(2\theta)}{g}
$$

is maximized when the launch angle is $45^\circ$.

## Theory

For fixed $v_0$ and constant gravitational acceleration $g$, the range depends only on the angle $\theta$. Therefore the optimization problem reduces to finding the maximum value of the function $\sin(2\theta)$.

For physically meaningful launch angles,

$$
0 \leq \theta \leq \frac{\pi}{2}
$$

so that

$$
0 \leq 2\theta \leq \pi
$$

## Step-by-Step Solution

The range function is

$$
R(\theta) = \frac{v_0^2}{g} \sin(2\theta)
$$

Since $\frac{v_0^2}{g}$ is a positive constant, maximizing $R(\theta)$ is equivalent to maximizing $\sin(2\theta)$.

### 1. First derivative

Differentiate with respect to $\theta$:

$$
\frac{dR}{d\theta} = \frac{v_0^2}{g} \cdot 2\cos(2\theta)
$$

Thus,

$$
\frac{dR}{d\theta} = \frac{2v_0^2}{g} \cos(2\theta)
$$

A critical point occurs when

$$
\frac{dR}{d\theta} = 0
$$

Therefore,

$$
\cos(2\theta) = 0
$$

This gives

$$
2\theta = \frac{\pi}{2}
$$

and hence

$$
\theta = \frac{\pi}{4}
$$

That is,

$$
\theta = 45^\circ
$$

### 2. Second derivative test

Differentiate once more:

$$
\frac{d^2R}{d\theta^2} = \frac{2v_0^2}{g} \cdot (-2\sin(2\theta))
$$

so

$$
\frac{d^2R}{d\theta^2} = -\frac{4v_0^2}{g} \sin(2\theta)
$$

Evaluate at $\theta = \frac{\pi}{4}$:

$$
\frac{d^2R}{d\theta^2}\bigg|_{\theta = \pi/4} = -\frac{4v_0^2}{g} \sin\left(\frac{\pi}{2}\right)
$$

$$
\frac{d^2R}{d\theta^2}\bigg|_{\theta = \pi/4} = -\frac{4v_0^2}{g} < 0
$$

Since the second derivative is negative, the critical point is a maximum.

### 3. Maximum value of the range

At $\theta = 45^\circ$,

$$
R_{\max} = \frac{v_0^2 \sin(90^\circ)}{g}
$$

$$
R_{\max} = \frac{v_0^2}{g}
$$

## Final Result

The range is maximized when

$$
\theta = 45^\circ
$$

and the corresponding maximum range is

$$
R_{\max} = \frac{v_0^2}{g}
$$

## Interpretation

The factor controlling the range is $\sin(2\theta)$. Its largest possible value is $1$, which occurs at $2\theta = 90^\circ$. Therefore a launch angle of $45^\circ$ gives the greatest horizontal distance for a fixed launch speed when air resistance is neglected. Angles such as $30^\circ$ and $60^\circ$ produce the same range because they have the same value of $\sin(2\theta)$.
