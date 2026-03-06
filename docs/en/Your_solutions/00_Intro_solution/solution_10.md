# Task 10 - Infinite Series and Final Position

## Problem Statement

An ant starts at the origin and moves according to the pattern:

$$
1 \text{ m east},\,
\frac{1}{2} \text{ m north},\,
\frac{1}{3} \text{ m west},\,
\frac{1}{4} \text{ m south},\,
\frac{1}{5} \text{ m east},\,
\dots
$$

Determine the ant's final position.

## Theory

The motion can be separated into horizontal and vertical components.

The horizontal displacement is the sum of odd reciprocal terms with alternating signs:

$$
x = 1 - \frac{1}{3} + \frac{1}{5} - \frac{1}{7} + \dots
$$

The vertical displacement is the sum of even reciprocal terms with alternating signs:

$$
y = \frac{1}{2} - \frac{1}{4} + \frac{1}{6} - \frac{1}{8} + \dots
$$

These are convergent alternating series.

A standard result is

$$
1 - \frac{1}{2} + \frac{1}{3} - \frac{1}{4} + \dots = \ln 2
$$

Another standard result is

$$
1 - \frac{1}{3} + \frac{1}{5} - \frac{1}{7} + \dots = \frac{\pi}{4}
$$

## Step-by-Step Solution

### Horizontal Coordinate

The ant moves east on the first, fifth, ninth, and similar steps, and west on the third, seventh, eleventh, and similar steps.

Therefore,

$$
x = 1 - \frac{1}{3} + \frac{1}{5} - \frac{1}{7} + \dots
$$

This is the Gregory-Leibniz series, so

$$
x = \frac{\pi}{4}
$$

### Vertical Coordinate

The ant moves north on the second, sixth, tenth, and similar steps, and south on the fourth, eighth, twelfth, and similar steps.

Therefore,

$$
y = \frac{1}{2} - \frac{1}{4} + \frac{1}{6} - \frac{1}{8} + \dots
$$

Factor out $\frac{1}{2}$:

$$
y = \frac{1}{2} \left(1 - \frac{1}{2} + \frac{1}{3} - \frac{1}{4} + \dots\right)
$$

Use the alternating harmonic series result:

$$
1 - \frac{1}{2} + \frac{1}{3} - \frac{1}{4} + \dots = \ln 2
$$

Hence,

$$
y = \frac{1}{2} \ln 2
$$

### Final Position

The final position is therefore

$$
\left(\frac{\pi}{4}, \frac{\ln 2}{2}\right)
$$

Numerically,

$$
\frac{\pi}{4} \approx 0.7854
$$

and

$$
\frac{\ln 2}{2} \approx 0.3466
$$

## Final Result

The ant's final position is

$$
\left(\frac{\pi}{4}, \frac{\ln 2}{2}\right)
$$

which is approximately

$$
(0.7854,\ 0.3466)
$$

## Interpretation

Although the ant takes infinitely many steps, the total displacement converges to a finite point. The horizontal and vertical motions form two convergent alternating series, so the path approaches a well-defined limiting position.
