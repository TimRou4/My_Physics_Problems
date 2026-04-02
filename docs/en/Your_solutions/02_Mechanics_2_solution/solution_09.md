# Task 09 - Vertical Throw with Drag

## Problem Statement

The vertical motion is governed by

$$
m\frac{dv}{dt} = -mg - kv
$$

with initial conditions

$$
v(0) = v_0
$$

and

$$
x(0) = 10
$$

Required:
1. Solve the equation analytically.
2. Determine the maximum height.
3. Compare with the case without drag.
4. Provide a numerical simulation in Python.

## Theory

The equation

$$
m\frac{dv}{dt} = -mg - kv
$$

describes vertical motion under gravity and linear drag. The drag force is proportional to velocity and opposes the upward motion.

It is convenient to divide by $m$ and define

$$
\beta = \frac{k}{m}
$$

Then the equation becomes

$$
\frac{dv}{dt} + \beta v = -g
$$

This is a first-order linear differential equation.

The position function is obtained by integrating the velocity.

## Step-by-Step Solution

### 1. Analytical solution for the velocity

Start from

$$
\frac{dv}{dt} + \beta v = -g
$$

The homogeneous equation is

$$
\frac{dv_h}{dt} + \beta v_h = 0
$$

with solution

$$
v_h(t) = C e^{-\beta t}
$$

A constant particular solution is sought:

$$
v_p = \text{const}
$$

Substituting into the differential equation gives

$$
\beta v_p = -g
$$

so

$$
v_p = -\frac{g}{\beta}
$$

Therefore,

$$
v(t) = C e^{-\beta t} - \frac{g}{\beta}
$$

Apply the initial condition $v(0) = v_0$:

$$
v_0 = C - \frac{g}{\beta}
$$

Hence,

$$
C = v_0 + \frac{g}{\beta}
$$

So the velocity is

$$
v(t) = \left(v_0 + \frac{g}{\beta}\right)e^{-\beta t} - \frac{g}{\beta}
$$

Replacing $\beta = \frac{k}{m}$ gives

$$
v(t) = \left(v_0 + \frac{mg}{k}\right)e^{-kt/m} - \frac{mg}{k}
$$

### 2. Analytical solution for the position

Integrate the velocity:

$$
x(t) = x(0) + \int_0^t v(s)\,ds
$$

Using $x(0) = 10$,

$$
x(t) = 10 + \int_0^t \left[\left(v_0 + \frac{g}{\beta}\right)e^{-\beta s} - \frac{g}{\beta}\right] ds
$$

Integrate term by term:

$$
x(t) = 10 + \left(v_0 + \frac{g}{\beta}\right)\frac{1 - e^{-\beta t}}{\beta} - \frac{g}{\beta}t
$$

In terms of $k$ and $m$,

$$
x(t) = 10 + \left(v_0 + \frac{mg}{k}\right)\frac{m}{k}\left(1 - e^{-kt/m}\right) - \frac{mg}{k}t
$$

### 3. Time at maximum height

The maximum height is reached when

$$
v(t_{\max}) = 0
$$

Thus,

$$
\left(v_0 + \frac{mg}{k}\right)e^{-kt_{\max}/m} - \frac{mg}{k} = 0
$$

Rearrange:

$$
\left(v_0 + \frac{mg}{k}\right)e^{-kt_{\max}/m} = \frac{mg}{k}
$$

Therefore,

$$
e^{-kt_{\max}/m} = \frac{mg}{kv_0 + mg}
$$

Taking the natural logarithm,

$$
t_{\max} = \frac{m}{k}\ln\left(1 + \frac{kv_0}{mg}\right)
$$

### 4. Maximum height

Insert $t_{\max}$ into the position function. A compact form is

$$
x_{\max} = 10 + \frac{mv_0}{k} - \frac{m^2 g}{k^2}\ln\left(1 + \frac{kv_0}{mg}\right)
$$

This is the maximum vertical position.

### 5. Comparison with the case without drag

Without drag, the equation is

$$
m\frac{dv}{dt} = -mg
$$

so

$$
v(t) = v_0 - gt
$$

and

$$
x(t) = 10 + v_0 t - \frac{1}{2}gt^2
$$

At maximum height, $v = 0$, hence

$$
t_{\max}^{(0)} = \frac{v_0}{g}
$$

and

$$
x_{\max}^{(0)} = 10 + \frac{v_0^2}{2g}
$$

The drag case always gives a smaller maximum height than the no-drag case.

### 6. Numerical simulation in Python

The following script performs a simple Euler integration and compares the numerical result with the analytical solution.

```python
import math
import matplotlib.pyplot as plt

# Parameters
m = 1.0
k = 0.4
g = 9.81
v0 = 15.0
x0 = 10.0

# Time settings
dt = 0.001
t_max = 4.0

# Lists for numerical solution
t_values = [0.0]
v_values = [v0]
x_values = [x0]

# Euler method
t = 0.0
v = v0
x = x0

while t < t_max:
    a = -g - (k / m) * v
    v = v + a * dt
    x = x + v * dt
    t = t + dt

    t_values.append(t)
    v_values.append(v)
    x_values.append(x)

# Analytical solutions
v_exact = []
x_exact = []

for t in t_values:
    v_t = (v0 + m * g / k) * math.exp(-k * t / m) - m * g / k
    x_t = x0 + (v0 + m * g / k) * (m / k) * (1 - math.exp(-k * t / m)) - (m * g / k) * t
    v_exact.append(v_t)
    x_exact.append(x_t)

# Plot velocity
plt.figure()
plt.plot(t_values, v_values, label="Numerical v(t)")
plt.plot(t_values, v_exact, label="Analytical v(t)")
plt.xlabel("t [s]")
plt.ylabel("v [m/s]")
plt.legend()
plt.grid(True)

# Plot position
plt.figure()
plt.plot(t_values, x_values, label="Numerical x(t)")
plt.plot(t_values, x_exact, label="Analytical x(t)")
plt.xlabel("t [s]")
plt.ylabel("x [m]")
plt.legend()
plt.grid(True)

plt.show()
```

## Final Result

The analytical velocity is

$$
v(t) = \left(v_0 + \frac{mg}{k}\right)e^{-kt/m} - \frac{mg}{k}
$$

The analytical position is

$$
x(t) = 10 + \left(v_0 + \frac{mg}{k}\right)\frac{m}{k}\left(1 - e^{-kt/m}\right) - \frac{mg}{k}t
$$

The time to maximum height is

$$
t_{\max} = \frac{m}{k}\ln\left(1 + \frac{kv_0}{mg}\right)
$$

The maximum height is

$$
x_{\max} = 10 + \frac{mv_0}{k} - \frac{m^2 g}{k^2}\ln\left(1 + \frac{kv_0}{mg}\right)
$$

Without drag, the maximum height would be

$$
x_{\max}^{(0)} = 10 + \frac{v_0^2}{2g}
$$

## Interpretation

Linear drag continuously removes mechanical energy from the motion. As a consequence, the ascent is shorter and the maximum height is lower than in vacuum. The analytical solution shows exponential decay in the velocity, while the numerical simulation illustrates the same effect by direct time stepping.
