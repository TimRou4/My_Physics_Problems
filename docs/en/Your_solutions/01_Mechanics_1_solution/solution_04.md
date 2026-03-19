# Task 04 - Velocity and Acceleration from a Position Vector

## Problem Statement

The position of an object is given by

$$
\vec{r}(t) = (3t^2)\hat{i} + (5t - 8t^2)\hat{j}
$$

Find the velocity vector and the acceleration vector as functions of time.

## Theory

Velocity is the time derivative of position:

$$
\vec{v}(t) = \frac{d\vec{r}}{dt}
$$

Acceleration is the time derivative of velocity:

$$
\vec{a}(t) = \frac{d\vec{v}}{dt} = \frac{d^2\vec{r}}{dt^2}
$$

The derivatives are taken componentwise.

## Step-by-Step Solution

Write the position vector in component form:

$$
\vec{r}(t) = \langle 3t^2, 5t - 8t^2 \rangle
$$

### 1. Velocity vector

Differentiate each component with respect to $t$:

$$
\frac{d}{dt}(3t^2) = 6t
$$

$$
\frac{d}{dt}(5t - 8t^2) = 5 - 16t
$$

Therefore,

$$
\vec{v}(t) = \langle 6t, 5 - 16t \rangle
$$

or in unit-vector form,

$$
\vec{v}(t) = (6t)\hat{i} + (5 - 16t)\hat{j}
$$

### 2. Acceleration vector

Differentiate the velocity components:

$$
\frac{d}{dt}(6t) = 6
$$

$$
\frac{d}{dt}(5 - 16t) = -16
$$

Hence,

$$
\vec{a}(t) = \langle 6, -16 \rangle
$$

or

$$
\vec{a}(t) = 6\hat{i} - 16\hat{j}
$$

## Final Result

The velocity vector is

$$
\vec{v}(t) = (6t)\hat{i} + (5 - 16t)\hat{j}
$$

The acceleration vector is

$$
\vec{a}(t) = 6\hat{i} - 16\hat{j}
$$

## Interpretation

The motion is planar. The $x$-component of velocity increases linearly with time, while the $y$-component decreases linearly with time. The acceleration is constant, which indicates uniformly accelerated motion in both coordinate directions.
