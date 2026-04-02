# Task 01 - Gravitational Dependence

## Problem Statement

A simple pendulum has a period of $4 \, \mathrm{s}$ on Earth.

1. Determine its period on the Moon, where the gravitational acceleration is approximately $g_{\text{Moon}} = \frac{1}{6} g_{\text{Earth}}$.
2. Determine the required pendulum length for a period of exactly $1 \, \mathrm{s}$ on Earth.

## Theory

For a simple pendulum in the small-angle approximation, the period is

$$
T = 2\pi \sqrt{\frac{L}{g}}
$$

where:
- $T$ is the period,
- $L$ is the pendulum length,
- $g$ is the gravitational acceleration.

For a fixed length $L$, the period depends on gravity as

$$
T \propto \frac{1}{\sqrt{g}}
$$

## Step-by-Step Solution

### 1. Period on the Moon

The same pendulum length is assumed on Earth and on the Moon. Therefore,

$$
\frac{T_{\text{Moon}}}{T_{\text{Earth}}} = \sqrt{\frac{g_{\text{Earth}}}{g_{\text{Moon}}}}
$$

Since

$$
g_{\text{Moon}} = \frac{1}{6} g_{\text{Earth}}
$$

it follows that

$$
\frac{g_{\text{Earth}}}{g_{\text{Moon}}} = 6
$$

Hence,

$$
T_{\text{Moon}} = T_{\text{Earth}} \sqrt{6}
$$

Substituting $T_{\text{Earth}} = 4 \, \mathrm{s}$,

$$
T_{\text{Moon}} = 4\sqrt{6} \, \mathrm{s}
$$

Numerically,

$$
T_{\text{Moon}} \approx 4 \cdot 2.449 = 9.80 \, \mathrm{s}
$$

### 2. Length for a period of $1 \, \mathrm{s}$ on Earth

The statement is interpreted literally as a full period of $1 \, \mathrm{s}$.

From

$$
T = 2\pi \sqrt{\frac{L}{g}}
$$

solve for $L$:

$$
L = g\left(\frac{T}{2\pi}\right)^2
$$

Using $g = 9.81 \, \mathrm{m/s^2}$ and $T = 1 \, \mathrm{s}$,

$$
L = 9.81 \left(\frac{1}{2\pi}\right)^2
$$

$$
L = \frac{9.81}{4\pi^2}
$$

Numerically,

$$
L \approx \frac{9.81}{39.478} \approx 0.249 \, \mathrm{m}
$$

## Final Result

The pendulum period on the Moon is

$$
T_{\text{Moon}} = 4\sqrt{6} \, \mathrm{s} \approx 9.80 \, \mathrm{s}
$$

The required pendulum length for a period of $1 \, \mathrm{s}$ on Earth is

$$
L \approx 0.249 \, \mathrm{m}
$$

## Interpretation

A pendulum oscillates more slowly when gravity is weaker. Since lunar gravity is six times smaller than terrestrial gravity, the period becomes $\sqrt{6}$ times larger.

The required length for a $1 \, \mathrm{s}$ period is relatively short, about $25 \, \mathrm{cm}$. This follows from the square-root dependence of the period on length.
