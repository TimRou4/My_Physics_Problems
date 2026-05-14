# 06_01_series_parallel_circuit.md

# 1. Series and Parallel Circuit

Given:

$R_1 = 15\,\Omega$

$R_2 = 30\,\Omega$

$R_3 = 50\,\Omega$

$V = 12\,\text{V}$

## Series connection

For resistors in series:

$$
R_{\text{eq}} = R_1 + R_2 + R_3
$$

$$
R_{\text{eq}} = 15 + 30 + 50 = 95\,\Omega
$$

Using Ohm's law:

$$
I = \frac{V}{R}
$$

$$
I = \frac{12}{95} \approx 0.126\,\text{A}
$$

## Parallel connection

For resistors in parallel:

$$
\frac{1}{R_{\text{eq}}} = \frac{1}{R_1} + \frac{1}{R_2} + \frac{1}{R_3}
$$

$$
\frac{1}{R_{\text{eq}}} = \frac{1}{15} + \frac{1}{30} + \frac{1}{50}
$$

Common denominator:

$$
\frac{1}{R_{\text{eq}}} = \frac{10}{150} + \frac{5}{150} + \frac{3}{150}
$$

$$
\frac{1}{R_{\text{eq}}} = \frac{18}{150}
$$

$$
R_{\text{eq}} = \frac{150}{18} \approx 8.33\,\Omega
$$

Current from the battery:

$$
I = \frac{12}{8.33} \approx 1.44\,\text{A}
$$

## Final Answer

Series:

$$
R_{\text{eq}} = 95\,\Omega
$$

$$
I \approx 0.126\,\text{A}
$$

Parallel:

$$
R_{\text{eq}} \approx 8.33\,\Omega
$$

$$
I \approx 1.44\,\text{A}
$$
