# Task 08 - Definite Integral of $\sin(x)$

## Problem Statement

Calculate the area under the curve of the function

$$
f(x) = \sin(x)
$$

from

$$
x = 0
$$

to

$$
x = \pi
$$

## Theory

The area under a curve on an interval $[a, b]$ is given by the definite integral

$$
\int_a^b f(x)\,dx
$$

If the function is nonnegative on the interval, the integral equals the geometric area.

An antiderivative of $\sin(x)$ is

$$
-\cos(x)
$$

## Step-by-Step Solution

The required area is

$$
\int_0^{\pi} \sin(x)\,dx
$$

Use the antiderivative:

$$
\int \sin(x)\,dx = -\cos(x)
$$

Therefore,

$$
\int_0^{\pi} \sin(x)\,dx = \left[-\cos(x)\right]_0^{\pi}
$$

Evaluate at the bounds:

$$
-\cos(\pi) - \left(-\cos(0)\right)
$$

Use the known values:

$$
\cos(\pi) = -1
$$

and

$$
\cos(0) = 1
$$

Then

$$
-\cos(\pi) - \left(-\cos(0)\right) = -(-1) - (-1)
$$

$$
= 1 + 1
$$

$$
= 2
$$

## Final Result

The area under the curve is

$$
2
$$

## Interpretation

On the interval from $0$ to $\pi$, the sine function is nonnegative, so the definite integral gives the full geometric area directly. This area equals $2$ square units.
