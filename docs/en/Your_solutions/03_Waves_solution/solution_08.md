# Task 08 - Traveling Wave Check

## Problem Statement

Determine which of the following functions can describe a traveling wave by checking whether each function satisfies the wave equation

$$
\frac{\partial^2 y}{\partial x^2} = \frac{1}{v^2}\frac{\partial^2 y}{\partial t^2}
$$

The candidate functions are:

$$
\text{a)} \quad y(x,t) = A \cos(kx^2 - \omega t)
$$

$$
\text{b)} \quad y(x,t) = A(x-vt)^2
$$

$$
\text{c)} \quad y(x,t) = A \log(x+vt)
$$

## Theory

A standard one-dimensional traveling wave can be written as

$$
y(x,t) = F(x-vt)
$$

or

$$
y(x,t) = F(x+vt)
$$

for some sufficiently differentiable function $F$.

Such functions satisfy the wave equation automatically. A direct derivative check can be used to verify whether a given function belongs to this class.

## Step-by-Step Solution

### a) Function $y(x,t) = A \cos(kx^2 - \omega t)$

Let

$$
\phi = kx^2 - \omega t
$$

Then

$$
y = A \cos \phi
$$

First derivative with respect to $x$:

$$
\frac{\partial y}{\partial x} = -A \sin \phi \cdot 2kx
$$

$$
\frac{\partial y}{\partial x} = -2Akx \sin \phi
$$

Second derivative with respect to $x$:

$$
\frac{\partial^2 y}{\partial x^2} = -2Ak \sin \phi - 4Ak^2x^2 \cos \phi
$$

Now differentiate with respect to $t$:

$$
\frac{\partial y}{\partial t} = A\omega \sin \phi
$$

$$
\frac{\partial^2 y}{\partial t^2} = -A\omega^2 \cos \phi
$$

The wave equation would require

$$
-2Ak \sin \phi - 4Ak^2x^2 \cos \phi = \frac{1}{v^2}\left(-A\omega^2 \cos \phi\right)
$$

This equality does not hold in general because the left-hand side contains both $\sin \phi$ and $x^2 \cos \phi$ terms, while the right-hand side contains only $\cos \phi$.

Therefore, function a) does not satisfy the wave equation.

### b) Function $y(x,t) = A(x-vt)^2$

Differentiate with respect to $x$:

$$
\frac{\partial y}{\partial x} = 2A(x-vt)
$$

$$
\frac{\partial^2 y}{\partial x^2} = 2A
$$

Differentiate with respect to $t$:

$$
\frac{\partial y}{\partial t} = -2Av(x-vt)
$$

$$
\frac{\partial^2 y}{\partial t^2} = 2Av^2
$$

Then

$$
\frac{1}{v^2}\frac{\partial^2 y}{\partial t^2} = \frac{1}{v^2}(2Av^2) = 2A
$$

Hence,

$$
\frac{\partial^2 y}{\partial x^2} = \frac{1}{v^2}\frac{\partial^2 y}{\partial t^2}
$$

So function b) satisfies the wave equation.

### c) Function $y(x,t) = A \log(x+vt)$

Differentiate with respect to $x$:

$$
\frac{\partial y}{\partial x} = \frac{A}{x+vt}
$$

$$
\frac{\partial^2 y}{\partial x^2} = -\frac{A}{(x+vt)^2}
$$

Differentiate with respect to $t$:

$$
\frac{\partial y}{\partial t} = \frac{Av}{x+vt}
$$

$$
\frac{\partial^2 y}{\partial t^2} = -\frac{Av^2}{(x+vt)^2}
$$

Then

$$
\frac{1}{v^2}\frac{\partial^2 y}{\partial t^2} = \frac{1}{v^2}\left(-\frac{Av^2}{(x+vt)^2}\right)
$$

$$
\frac{1}{v^2}\frac{\partial^2 y}{\partial t^2} = -\frac{A}{(x+vt)^2}
$$

Hence,

$$
\frac{\partial^2 y}{\partial x^2} = \frac{1}{v^2}\frac{\partial^2 y}{\partial t^2}
$$

So function c) satisfies the wave equation, provided that the argument of the logarithm is positive:

$$
x + vt > 0
$$

## Final Result

The functions that can describe traveling waves are:

$$
\text{b)} \quad y(x,t) = A(x-vt)^2
$$

and

$$
\text{c)} \quad y(x,t) = A \log(x+vt)
$$

The function

$$
\text{a)} \quad y(x,t) = A \cos(kx^2 - \omega t)
$$

does not satisfy the wave equation.

## Interpretation

Functions of the form $F(x-vt)$ or $F(x+vt)$ represent traveling shapes that move without changing form. Options b) and c) have exactly this structure, so they satisfy the wave equation. Option a) contains the term $x^2$, which changes the spatial form in a way that is not compatible with ordinary wave propagation.
