# Task 07 - Logic and Series: Bicycle and Fly

## Problem Statement

A bicycle is $10$ meters from a wall and moves towards it at a constant speed of $1 \text{ m/s}$. A fly starts from the bicycle's front wheel and flies towards the wall at $2 \text{ m/s}$. Each time it hits the wall, it instantly turns back and flies to the bicycle, and so on.

Determine the total distance the fly travels before being crushed.

## Theory

Although the fly changes direction infinitely many times, the total motion lasts only as long as the bicycle needs to reach the wall.

If the total time of motion is known, then the fly's total distance is simply

$$
d = vt
$$

This avoids summing an infinite sequence of shorter and shorter trips.

## Step-by-Step Solution

### Time Until the Bicycle Reaches the Wall

The bicycle starts $10$ meters from the wall and moves at

$$
v_{\text{bike}} = 1 \text{ m/s}
$$

Therefore, the travel time is

$$
t = \frac{d}{v}
$$

$$
t = \frac{10}{1}
$$

$$
t = 10 \text{ s}
$$

### Distance Traveled by the Fly

The fly moves continuously during these $10$ seconds with speed

$$
v_{\text{fly}} = 2 \text{ m/s}
$$

Hence its total distance is

$$
d_{\text{fly}} = v_{\text{fly}} t
$$

$$
d_{\text{fly}} = 2 \cdot 10
$$

$$
d_{\text{fly}} = 20 \text{ m}
$$

## Final Result

The fly travels a total distance of

$$
20 \text{ m}
$$

## Interpretation

The repeated back-and-forth motion creates infinitely many segments, but not infinite distance. The key quantity is the finite time before the bicycle reaches the wall. This is a standard example showing that an infinite sequence of events can occur within a finite interval of time.
