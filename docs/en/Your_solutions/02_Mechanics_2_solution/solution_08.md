# Task 08 - Work of a Variable Force

## Problem Statement

A one-dimensional force is given by

$$
F(x) = -kx
$$

Required:
1. Write the equation of motion and solve it.
2. Calculate the work done during the displacement from $0$ to $x_0$.
3. Interpret the result as potential energy.
4. Verify the relation $F = -\frac{dU}{dx}$.
5. Draw the graphs of $F(x)$ and $U(x)$.

## Theory

The force

$$
F(x) = -kx
$$

is the restoring force of a linear spring. It is proportional to the displacement and always points toward the equilibrium point $x = 0$.

The equation of motion follows from Newton's second law:

$$
m\frac{d^2x}{dt^2} = F(x)
$$

The work of a variable force from $x=a$ to $x=b$ is

$$
W_{a \to b} = \int_a^b F(x)\,dx
$$

For conservative forces, the potential energy satisfies

$$
F(x) = -\frac{dU}{dx}
$$

## Step-by-Step Solution

### 1. Equation of motion

From Newton's second law,

$$
m\frac{d^2x}{dt^2} = -kx
$$

or equivalently,

$$
\frac{d^2x}{dt^2} + \frac{k}{m}x = 0
$$

Define

$$
\omega = \sqrt{\frac{k}{m}}
$$

Then the equation becomes

$$
\frac{d^2x}{dt^2} + \omega^2 x = 0
$$

This is the differential equation of simple harmonic motion.

### 2. General solution

The general solution is

$$
x(t) = A \cos(\omega t) + B \sin(\omega t)
$$

where $A$ and $B$ are constants determined by initial conditions.

An equivalent form is

$$
x(t) = C \cos(\omega t + \phi)
$$

where $C$ is the amplitude and $\phi$ is the phase constant.

### 3. Work done from $0$ to $x_0$

The work is

$$
W_{0 \to x_0} = \int_0^{x_0} (-kx)\,dx
$$

Carry out the integration:

$$
W_{0 \to x_0} = -k \int_0^{x_0} x\,dx
$$

$$
W_{0 \to x_0} = -k \left[\frac{x^2}{2}\right]_0^{x_0}
$$

$$
W_{0 \to x_0} = -\frac{1}{2}k x_0^2
$$

### 4. Interpretation as potential energy

For a conservative force,

$$
W_{0 \to x_0} = -(U(x_0) - U(0))
$$

Choose the reference level

$$
U(0) = 0
$$

Then

$$
U(x_0) = -W_{0 \to x_0}
$$

so

$$
U(x_0) = \frac{1}{2}k x_0^2
$$

Since $x_0$ is arbitrary, the potential energy function is

$$
U(x) = \frac{1}{2}k x^2
$$

### 5. Verification of the relation $F = -\frac{dU}{dx}$

Differentiate the potential:

$$
\frac{dU}{dx} = \frac{d}{dx}\left(\frac{1}{2}k x^2\right)
$$

$$
\frac{dU}{dx} = kx
$$

Therefore,

$$
-\frac{dU}{dx} = -kx
$$

Hence,

$$
F(x) = -\frac{dU}{dx}
$$

which confirms the conservative-force relation.

### 6. Graphs of $F(x)$ and $U(x)$

The force is a straight line through the origin with negative slope:

$$
F(x) = -kx
$$

The potential energy is an upward-opening parabola:

$$
U(x) = \frac{1}{2}k x^2
$$

A simple qualitative sketch is shown below.

```text
F(x)
 ^
 |\
 | \
 |  \
 |   \
 |    \
 +-----\--------> x
 |      \
 |       \
 |        \

U(x)
 ^
 |        *
 |      *   *
 |    *       *
 |  *           *
 | *             *
 +------------------> x
```

## Final Result

The equation of motion is

$$
m\ddot{x} + kx = 0
$$

with general solution

$$
x(t) = A \cos\left(\sqrt{\frac{k}{m}}\,t\right) + B \sin\left(\sqrt{\frac{k}{m}}\,t\right)
$$

The work done by the force from $0$ to $x_0$ is

$$
W_{0 \to x_0} = -\frac{1}{2}k x_0^2
$$

The potential energy is

$$
U(x) = \frac{1}{2}k x^2
$$

and the relation

$$
F(x) = -\frac{dU}{dx}
$$

is satisfied.

## Interpretation

The force always points toward equilibrium, which is why it generates oscillatory motion. The work done by the restoring force is negative when the displacement is away from equilibrium, because the force opposes that displacement. The associated potential energy is quadratic in $x$, so the oscillator stores more energy rapidly as displacement increases.
