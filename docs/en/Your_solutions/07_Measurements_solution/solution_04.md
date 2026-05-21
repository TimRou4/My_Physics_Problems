# Task 04 - Relative Uncertainty

## Problem Statement

A car's speedometer has a $5\%$ uncertainty. If it reads $60\text{ km/h}$, determine the range of the car's actual speed.

## Theory

Percentage uncertainty is related to absolute uncertainty by

$$
\Delta v = \frac{p}{100}v
$$

where $p$ is the percentage uncertainty and $v$ is the measured value.

The possible range of the actual value is

$$
v_{\text{min}} = v - \Delta v
$$

$$
v_{\text{max}} = v + \Delta v
$$

## Step-by-Step Solution

Given values:

$$
v = 60\text{ km/h}
$$

$$
p = 5\%
$$

Calculate the absolute uncertainty:

$$
\Delta v = \frac{5}{100}(60)
$$

$$
\Delta v = 0.05(60)
$$

$$
\Delta v = 3\text{ km/h}
$$

Calculate the lower limit:

$$
v_{\text{min}} = 60 - 3
$$

$$
v_{\text{min}} = 57\text{ km/h}
$$

Calculate the upper limit:

$$
v_{\text{max}} = 60 + 3
$$

$$
v_{\text{max}} = 63\text{ km/h}
$$

## Final Result

$$
v = (60 \pm 3)\text{ km/h}
$$

The actual speed is in the range

$$
57\text{ km/h} \leq v \leq 63\text{ km/h}
$$

## Interpretation

A $5\%$ uncertainty means the speedometer reading may differ from the actual speed by $5\%$ of the indicated value. For a reading of $60\text{ km/h}$, this corresponds to an uncertainty of $3\text{ km/h}$.
