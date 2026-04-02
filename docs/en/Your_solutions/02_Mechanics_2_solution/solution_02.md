# Task 02 - Harmonic Motion

## Problem Statement

A mass of $10 \, \mathrm{kg}$ is attached to a spring and oscillates according to

$$
x(t) = 0.2 \cos(10\pi t)
$$

where $x$ is measured in meters.

Determine:
1. The spring constant $k$.
2. The total mechanical energy of the system.

## Theory

The standard form of simple harmonic motion is

$$
x(t) = A \cos(\omega t + \phi)
$$

where:
- $A$ is the amplitude,
- $\omega$ is the angular frequency,
- $\phi$ is the phase constant.

For a mass-spring oscillator,

$$
\omega = \sqrt{\frac{k}{m}}
$$

Therefore,

$$
k = m\omega^2
$$

The total mechanical energy of a harmonic oscillator is constant and equal to

$$
E = \frac{1}{2} k A^2
$$

## Step-by-Step Solution

### 1. Identify the parameters of motion

Given

$$
x(t) = 0.2 \cos(10\pi t)
$$

Comparison with the standard form gives:

$$
A = 0.2 \, \mathrm{m}
$$

and

$$
\omega = 10\pi \, \mathrm{rad/s}
$$

The mass is

$$
m = 10 \, \mathrm{kg}
$$

### 2. Calculate the spring constant

Using

$$
k = m\omega^2
$$

substitute the known values:

$$
k = 10(10\pi)^2
$$

$$
k = 10 \cdot 100\pi^2
$$

$$
k = 1000\pi^2 \, \mathrm{N/m}
$$

Numerically,

$$
k \approx 1000 \cdot 9.8696 \approx 9869.6 \, \mathrm{N/m}
$$

### 3. Calculate the total mechanical energy

Use

$$
E = \frac{1}{2} k A^2
$$

Substitute $k = 1000\pi^2$ and $A = 0.2$:

$$
E = \frac{1}{2} \cdot 1000\pi^2 \cdot (0.2)^2
$$

$$
E = \frac{1}{2} \cdot 1000\pi^2 \cdot 0.04
$$

$$
E = 20\pi^2 \, \mathrm{J}
$$

Numerically,

$$
E \approx 20 \cdot 9.8696 \approx 197.4 \, \mathrm{J}
$$

## Final Result

The spring constant is

$$
k = 1000\pi^2 \, \mathrm{N/m} \approx 9.87 \times 10^3 \, \mathrm{N/m}
$$

The total mechanical energy is

$$
E = 20\pi^2 \, \mathrm{J} \approx 197.4 \, \mathrm{J}
$$

## Interpretation

The angular frequency is large, so the spring must be very stiff. The total mechanical energy depends on both the stiffness and the amplitude. Even though the amplitude is only $0.2 \, \mathrm{m}$, the large value of $k$ produces a substantial stored energy.
