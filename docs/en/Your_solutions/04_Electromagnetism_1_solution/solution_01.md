# Problem Set 01 - Solutions

## Task 01 - Coulomb's Law

### Problem Statement

Four point charges of $+1.0 \mathrm{C}$ each are placed at the corners of a square with side length $1.0 \mathrm{m}$. A charge of $-2.0 \mathrm{C}$ is placed at the center of the square.

The magnitude and direction of the electric force on the central charge must be calculated.

### Theory

Coulomb's law gives the magnitude of the electric force between two point charges:

$$
F = k \frac{|q_1 q_2|}{r^2}
$$

where:

- $F$ is the magnitude of the electric force,
- $k$ is Coulomb's constant,
- $q_1$ and $q_2$ are the charges,
- $r$ is the distance between the two charges.

The value of Coulomb's constant is

$$
k = 8.99 \times 10^9 \frac{\mathrm{N} \cdot \mathrm{m}^2}{\mathrm{C}^2}
$$

Electric force is a vector quantity. Therefore, the net force on a charge is the vector sum of all individual forces acting on it.

$$
\vec{F}_{\mathrm{net}} = \vec{F}_1 + \vec{F}_2 + \vec{F}_3 + \vec{F}_4
$$

A negative charge is attracted toward positive charges. Since the central charge is negative and all four corner charges are positive, each force on the central charge points from the center toward one corner of the square.

### Step-by-Step Solution

The side length of the square is

$$
a = 1.0 \mathrm{m}
$$

The distance from the center of a square to any corner is half of the diagonal of the square.

The diagonal of the square is

$$
d = a\sqrt{2}
$$

Therefore, the distance from the center to one corner is

$$
r = \frac{d}{2}
$$

Substitute $d = a\sqrt{2}$:

$$
r = \frac{a\sqrt{2}}{2}
$$

With $a = 1.0 \mathrm{m}$:

$$
r = \frac{\sqrt{2}}{2} \mathrm{m}
$$

Thus,

$$
r^2 = \left(\frac{\sqrt{2}}{2}\right)^2
$$

$$
r^2 = \frac{1}{2} \mathrm{m}^2
$$

The magnitude of the force from one corner charge on the central charge is

$$
F = k \frac{|q_1 q_2|}{r^2}
$$

The values are

$$
q_1 = +1.0 \mathrm{C}
$$

$$
q_2 = -2.0 \mathrm{C}
$$

The magnitude of the product of the charges is

$$
|q_1 q_2| = |(+1.0)(-2.0)|
$$

$$
|q_1 q_2| = 2.0 \mathrm{C}^2
$$

Substitute the values into Coulomb's law:

$$
F = \left(8.99 \times 10^9\right) \frac{2.0}{1/2}
$$

Since dividing by $1/2$ is equivalent to multiplying by $2$:

$$
F = \left(8.99 \times 10^9\right)(4)
$$

$$
F = 3.596 \times 10^{10} \mathrm{N}
$$

Each corner charge attracts the central charge with the same force magnitude:

$$
F_1 = F_2 = F_3 = F_4 = 3.596 \times 10^{10} \mathrm{N}
$$

However, the four forces are directed symmetrically toward the four corners of the square.

The force toward the upper-right corner is canceled by the force toward the lower-left corner.

$$
\vec{F}_{\mathrm{upper-right}} + \vec{F}_{\mathrm{lower-left}} = \vec{0}
$$

The force toward the upper-left corner is canceled by the force toward the lower-right corner.

$$
\vec{F}_{\mathrm{upper-left}} + \vec{F}_{\mathrm{lower-right}} = \vec{0}
$$

Therefore, the total vector force is

$$
\vec{F}_{\mathrm{net}} = \vec{0}
$$

The magnitude of the net force is

$$
|\vec{F}_{\mathrm{net}}| = 0 \mathrm{N}
$$

### Final Result

$$
|\vec{F}_{\mathrm{net}}| = 0 \mathrm{N}
$$

The net electric force on the central charge is zero.

There is no specific direction for the net force because the net force vector is zero.

### Interpretation

Each positive corner charge attracts the negative central charge. Individually, each force is very large because the charges are large and the distances are small.

However, the square arrangement is perfectly symmetric. The forces from opposite corners have equal magnitudes and opposite directions. As a result, all four forces cancel pairwise.

Therefore, the central charge is in a state of electrostatic equilibrium. The net force is zero, so the charge has no preferred direction of motion due to the electric forces.
