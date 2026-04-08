# Task 06 - Wave Equation Parameters

## Problem Statement

A wave is described by

$$
y(x,t) = 0.05 \sin(2\pi x - 50\pi t)
$$

where $x$ and $y$ are in meters and $t$ is in seconds.

Determine:

1. the amplitude $A$,
2. the wavelength $\lambda$,
3. the frequency $f$,
4. the wave speed $v$.

## Theory

The standard form of a traveling wave is

$$
y(x,t) = A \sin(kx - \omega t)
$$

where:

- $A$ is the amplitude,
- $k$ is the wave number,
- $\omega$ is the angular frequency.

The relations are

$$
k = \frac{2\pi}{\lambda}
$$

$$
\omega = 2\pi f
$$

$$
v = \frac{\omega}{k} = f\lambda
$$

## Step-by-Step Solution

### 1. Compare the given equation with the standard form

Given:

$$
y(x,t) = 0.05 \sin(2\pi x - 50\pi t)
$$

By comparison with

$$
y(x,t) = A \sin(kx - \omega t)
$$

it follows that

$$
A = 0.05 \, \mathrm{m}
$$

$$
k = 2\pi \, \mathrm{rad/m}
$$

$$
\omega = 50\pi \, \mathrm{rad/s}
$$

### 2. Determine the wavelength

Use

$$
k = \frac{2\pi}{\lambda}
$$

Thus,

$$
\lambda = \frac{2\pi}{k}
$$

Substitute $k = 2\pi$:

$$
\lambda = \frac{2\pi}{2\pi} = 1 \, \mathrm{m}
$$

### 3. Determine the frequency

Use

$$
\omega = 2\pi f
$$

Thus,

$$
f = \frac{\omega}{2\pi}
$$

Substitute $\omega = 50\pi$:

$$
f = \frac{50\pi}{2\pi} = 25 \, \mathrm{Hz}
$$

### 4. Determine the wave speed

Use

$$
v = \frac{\omega}{k}
$$

Substitute the values:

$$
v = \frac{50\pi}{2\pi} = 25 \, \mathrm{m/s}
$$

As a check,

$$
v = f\lambda = 25 \cdot 1 = 25 \, \mathrm{m/s}
$$

## Final Result

The wave parameters are:

$$
A = 0.05 \, \mathrm{m}
$$

$$
\lambda = 1 \, \mathrm{m}
$$

$$
f = 25 \, \mathrm{Hz}
$$

$$
v = 25 \, \mathrm{m/s}
$$

## Interpretation

The coefficient in front of the sine function gives the maximum displacement, so it is the amplitude. The coefficients of $x$ and $t$ inside the sine determine the spatial periodicity and time periodicity, which lead directly to the wavelength and frequency.
