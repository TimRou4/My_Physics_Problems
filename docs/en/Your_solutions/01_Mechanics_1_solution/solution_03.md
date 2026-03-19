# Task 03 - Path Intersection and Collision Analysis

## Problem Statement

Alice moves along the path

$$
A(t) = (2+t, 8-3t)
$$

and Bob moves along the path

$$
B(t) = (2t-1, 2t+2)
$$

Determine:

1. Whether their paths intersect geometrically.
2. Whether they collide at the same time.
3. If they do not collide, determine the minimum distance between them and when it occurs.

## Theory

Two moving particles may satisfy two different conditions:

1. **Path intersection**: their trajectories cross in space, possibly at different parameter values.
2. **Collision**: they occupy the same point at the same time.

If no collision occurs, the distance between them at time $t$ is found from the relative position vector

$$
\Delta \vec{r}(t) = A(t) - B(t)
$$

The minimum distance is obtained by minimizing either $D(t)$ or the simpler function $D^2(t)$.

## Step-by-Step Solution

### 1. Geometric intersection of the trajectories

To test whether the trajectories intersect as geometric curves, use different parameters for the two motions:

$$
A(t_A) = (2+t_A, 8-3t_A)
$$

$$
B(t_B) = (2t_B-1, 2t_B+2)
$$

At an intersection point,

$$
2+t_A = 2t_B - 1
$$

$$
8-3t_A = 2t_B + 2
$$

From the first equation,

$$
2t_B = t_A + 3
$$

$$
t_B = \frac{t_A + 3}{2}
$$

Substitute into the second equation:

$$
8 - 3t_A = 2 \cdot \frac{t_A + 3}{2} + 2
$$

$$
8 - 3t_A = t_A + 3 + 2
$$

$$
8 - 3t_A = t_A + 5
$$

$$
3 = 4t_A
$$

$$
t_A = \frac{3}{4}
$$

Then

$$
t_B = \frac{\frac{3}{4} + 3}{2} = \frac{15}{8}
$$

Substitute into either path:

$$
A\left(\frac{3}{4}\right) = \left(2+\frac{3}{4}, 8-3\cdot\frac{3}{4}\right)
$$

$$
A\left(\frac{3}{4}\right) = \left(\frac{11}{4}, \frac{23}{4}\right)
$$

Therefore the two trajectories intersect geometrically at

$$
\left(\frac{11}{4}, \frac{23}{4}\right)
$$

### 2. Collision test

For a collision, the same time $t$ must satisfy

$$
A(t) = B(t)
$$

This gives the system

$$
2+t = 2t-1
$$

$$
8-3t = 2t+2
$$

From the first equation,

$$
t = 3
$$

From the second equation,

$$
6 = 5t
$$

$$
t = \frac{6}{5}
$$

The two equations give different times, so no single time satisfies both.

Therefore, the particles do **not** collide.

### 3. Minimum distance during simultaneous motion

Since the particles do not collide, compute their relative position at the same time $t$:

$$
\Delta \vec{r}(t) = A(t) - B(t)
$$

$$
\Delta \vec{r}(t) = (2+t-(2t-1), 8-3t-(2t+2))
$$

$$
\Delta \vec{r}(t) = (3-t, 6-5t)
$$

The squared distance is

$$
D^2(t) = (3-t)^2 + (6-5t)^2
$$

Expand:

$$
D^2(t) = 9 - 6t + t^2 + 36 - 60t + 25t^2
$$

$$
D^2(t) = 26t^2 - 66t + 45
$$

Differentiate:

$$
\frac{d}{dt}D^2(t) = 52t - 66
$$

Set the derivative equal to zero:

$$
52t - 66 = 0
$$

$$
t = \frac{66}{52} = \frac{33}{26}
$$

This is the minimizing time because the coefficient of $t^2$ is positive.

Now evaluate the squared distance:

$$
D^2\left(\frac{33}{26}\right) = 26\left(\frac{33}{26}\right)^2 - 66\left(\frac{33}{26}\right) + 45
$$

$$
D^2\left(\frac{33}{26}\right) = \frac{81}{26}
$$

Hence,

$$
D_{\min} = \sqrt{\frac{81}{26}} = \frac{9}{\sqrt{26}} \approx 1.77
$$

## Final Result

The trajectories intersect geometrically at

$$
\left(\frac{11}{4}, \frac{23}{4}\right)
$$

but the parameter values are different, so the particles do not arrive there at the same time. Therefore there is **no collision**.

The minimum distance during simultaneous motion occurs at

$$
t = \frac{33}{26} \approx 1.269
$$

and its value is

$$
D_{\min} = \frac{9}{\sqrt{26}} \approx 1.77
$$

## Interpretation

The problem distinguishes between the geometry of the paths and the dynamics of the motion. Alice and Bob move along lines that cross, but their time laws are different, so they miss each other. The closest approach occurs before either reaches the geometric intersection point.
