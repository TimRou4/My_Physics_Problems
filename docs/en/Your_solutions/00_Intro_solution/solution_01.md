# Task 01 - Vector Algebra

## Problem Statement

Given two vectors in 3D space:

$$
\vec{a} = [2, 1, -3]
$$

and

$$
\vec{b} = [4, -2, 1]
$$

calculate:

a) the magnitude of each vector

b) the dot product $\vec{a} \cdot \vec{b}$

c) the cross product $\vec{a} \times \vec{b}$

d) the angle between the vectors

## Theory

For a vector $\vec{v} = [v_x, v_y, v_z]$, its magnitude is

$$
|\vec{v}| = \sqrt{v_x^2 + v_y^2 + v_z^2}
$$

The dot product of two vectors is

$$
\vec{a} \cdot \vec{b} = a_x b_x + a_y b_y + a_z b_z
$$

The cross product in component form is

$$
\vec{a} \times \vec{b} =
\left[
a_y b_z - a_z b_y,\,
a_z b_x - a_x b_z,\,
a_x b_y - a_y b_x
\right]
$$

The angle $\theta$ between two vectors is obtained from

$$
\cos \theta = \frac{\vec{a} \cdot \vec{b}}{|\vec{a}| |\vec{b}|}
$$

## Step-by-Step Solution

### Magnitudes

For $\vec{a} = [2, 1, -3]$,

$$
|\vec{a}| = \sqrt{2^2 + 1^2 + (-3)^2}
$$

$$
|\vec{a}| = \sqrt{4 + 1 + 9}
$$

$$
|\vec{a}| = \sqrt{14}
$$

For $\vec{b} = [4, -2, 1]$,

$$
|\vec{b}| = \sqrt{4^2 + (-2)^2 + 1^2}
$$

$$
|\vec{b}| = \sqrt{16 + 4 + 1}
$$

$$
|\vec{b}| = \sqrt{21}
$$

### Dot Product

$$
\vec{a} \cdot \vec{b} = 2 \cdot 4 + 1 \cdot (-2) + (-3) \cdot 1
$$

$$
\vec{a} \cdot \vec{b} = 8 - 2 - 3
$$

$$
\vec{a} \cdot \vec{b} = 3
$$

### Cross Product

Using the component formula,

$$
\vec{a} \times \vec{b} =
\left[
1 \cdot 1 - (-3) \cdot (-2),\,
(-3) \cdot 4 - 2 \cdot 1,\,
2 \cdot (-2) - 1 \cdot 4
\right]
$$

$$
\vec{a} \times \vec{b} =
[1 - 6,\,-12 - 2,\,-4 - 4]
$$

$$
\vec{a} \times \vec{b} = [-5, -14, -8]
$$

### Angle Between the Vectors

$$
\cos \theta = \frac{\vec{a} \cdot \vec{b}}{|\vec{a}| |\vec{b}|}
$$

$$
\cos \theta = \frac{3}{\sqrt{14}\sqrt{21}}
$$

$$
\cos \theta = \frac{3}{\sqrt{294}}
$$

Therefore,

$$
\theta = \arccos\left(\frac{3}{\sqrt{294}}\right)
$$

Numerically,

$$
\theta \approx 79.93^\circ
$$

## Final Result

The results are:

$$
|\vec{a}| = \sqrt{14}
$$

$$
|\vec{b}| = \sqrt{21}
$$

$$
\vec{a} \cdot \vec{b} = 3
$$

$$
\vec{a} \times \vec{b} = [-5, -14, -8]
$$

$$
\theta = \arccos\left(\frac{3}{\sqrt{294}}\right) \approx 79.93^\circ
$$

## Interpretation

The positive dot product shows that the angle between the vectors is acute, but close to $90^\circ$. The cross product gives a vector perpendicular to both $\vec{a}$ and $\vec{b}$. Its nonzero value confirms that the two vectors are not parallel.
