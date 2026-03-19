# Task 08 - Circular Motion at the Earth's Equator

## Problem Statement

Calculate the centripetal acceleration of a person standing on the Earth's equator. The Earth's radius is approximately

$$
R = 6378 \text{ km}
$$

## Theory

A person standing on the equator moves in a circle due to the Earth's rotation. The centripetal acceleration is

$$
a_c = \frac{v^2}{R}
$$

It can also be written in terms of the angular speed $\omega$:

$$
a_c = \omega^2 R
$$

where

$$
\omega = \frac{2\pi}{T}
$$

Assuming one rotation every $24$ hours,

$$
T = 24 \cdot 3600 = 86400 \text{ s}
$$

The radius must be converted to meters:

$$
R = 6378 \times 10^3 \text{ m} = 6.378 \times 10^6 \text{ m}
$$

## Step-by-Step Solution

### 1. Angular speed of the Earth

Using

$$
\omega = \frac{2\pi}{T}
$$

gives

$$
\omega = \frac{2\pi}{86400}
$$

$$
\omega \approx 7.272 \times 10^{-5} \text{ rad/s}
$$

### 2. Centripetal acceleration

Now substitute into

$$
a_c = \omega^2 R
$$

Thus,

$$
a_c = \left( \frac{2\pi}{86400} \right)^2 (6.378 \times 10^6)
$$

Numerically,

$$
a_c \approx 0.0337 \text{ m/s}^2
$$

## Final Result

The centripetal acceleration of a person standing at the Earth's equator is approximately

$$
a_c \approx 3.37 \times 10^{-2} \text{ m/s}^2
$$

## Interpretation

This acceleration is much smaller than gravitational acceleration:

$$
g \approx 9.81 \text{ m/s}^2
$$

In fact,

$$
\frac{a_c}{g} \approx 0.0034
$$

so the centripetal acceleration at the equator is only about $0.34\%$ of $g$. It is small, but it is physically necessary to keep the person moving in a circular path with the rotating Earth.
