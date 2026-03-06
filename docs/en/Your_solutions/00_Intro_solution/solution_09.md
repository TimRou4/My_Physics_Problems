# Task 09 - Optimization of a Rectangle Under a Curve

## Problem Statement

A rectangle is under the curve

$$
y = 3 - x^2
$$

in the first quadrant. Determine the dimensions of the rectangle with the maximum area.

## Theory

In the first quadrant, the usual interpretation is that the rectangle has one corner at the origin and the opposite corner on the curve.

If the upper-right corner is $(x, y)$ and lies on the parabola, then

$$
y = 3 - x^2
$$

The rectangle area is

$$
A = x y
$$

Substituting the curve equation gives an area function in one variable. The maximum is found by differentiation.

## Step-by-Step Solution

Let the rectangle width be $x$ and the height be $y$.

Because the upper-right corner lies on the curve,

$$
y = 3 - x^2
$$

Therefore the area is

$$
A(x) = x(3 - x^2)
$$

Expand:

$$
A(x) = 3x - x^3
$$

The rectangle must lie in the first quadrant, so

$$
x \geq 0
$$

and

$$
3 - x^2 \geq 0
$$

Thus,

$$
0 \leq x \leq \sqrt{3}
$$

Differentiate the area function:

$$
A'(x) = 3 - 3x^2
$$

Set the derivative equal to zero:

$$
3 - 3x^2 = 0
$$

$$
1 - x^2 = 0
$$

$$
x^2 = 1
$$

Since $x$ is in the first quadrant,

$$
x = 1
$$

Now find the height:

$$
y = 3 - x^2
$$

$$
y = 3 - 1^2
$$

$$
y = 2
$$

To confirm this is a maximum, compute the second derivative:

$$
A''(x) = -6x
$$

At $x = 1$,

$$
A''(1) = -6 < 0
$$

so the area is maximal there.

## Final Result

The rectangle with maximum area has dimensions

$$
\text{width} = 1
$$

and

$$
\text{height} = 2
$$

Its maximum area is

$$
A_{\max} = 1 \cdot 2 = 2
$$

## Interpretation

The parabola decreases as $x$ increases, so a wider rectangle must also become lower. The optimal dimensions occur where the balance between width and height gives the largest possible product.
