# Deterministic Domain and Grid Generators in NumPy

## 1. Introduction

Deterministic domain and grid generators are NumPy functions used to generate predictable numerical sequences and coordinate grids.

They are called deterministic because, given the same inputs, they produce the same outputs.

They are useful in:
- Data science
- Numerical analysis
- Scientific computing
- Machine learning
- Mathematical calculations
- Data visualization
- Image processing

### Main functions

1. `np.arange()`
2. `np.linspace()`
3. `np.logspace()`
4. `np.geomspace()`
5. `np.meshgrid()`
6. `np.mgrid`
7. `np.ogrid()`

First, import NumPy:

```python
import numpy as np
```

---

# 2. np.arange()

## Definition

The `np.arange()` function generates evenly spaced values within a given interval using a specified step size.

It is similar to Python's built-in `range()`, but it returns a NumPy array and also supports floating-point steps.

## Syntax

```python
np.arange(start, stop, step, dtype=None)
```

### Parameters

| Parameter | Description |
|---|---|
| start | Starting value (inclusive). |
| stop | Ending value (exclusive). |
| step | Difference between consecutive values. |
| dtype | Optional data type of the output array. |

## Example 1: Basic usage

```python
import numpy as np

a = np.arange(1, 10, 2)
print(a)
```

Output:

```text
[1 3 5 7 9]
```

Explanation:
- Start = 1
- Stop = 10
- Step = 2
- The stop value is excluded.

## Example 2: Using only the stop parameter

```python
a = np.arange(5)
print(a)
```

Output:

```text
[0 1 2 3 4]
```

When only one argument is provided, NumPy starts at 0 and uses a step of 1.

## Example 3: Floating-point step

```python
a = np.arange(0, 2, 0.5)
print(a)
```

Output:

```text
[0.  0.5 1.  1.5]
```

## Example 4: Negative step

```python
a = np.arange(10, 0, -2)
print(a)
```

Output:

```text
[10  8  6  4  2]
```

A negative step generates values in descending order.

## Example 5: Specifying the data type

```python
a = np.arange(1, 6, dtype=float)
print(a)
print(a.dtype)
```

Output:

```text
[1. 2. 3. 4. 5.]
float64
```

## Important points

- The stop value is excluded.
- The step determines the interval between values.
- A positive step is generally used for ascending sequences.
- A negative step is used for descending sequences.
- Floating-point steps can introduce precision errors.
- Use `arange()` when you know the step size.

---

# 3. np.linspace()

## Definition

The `np.linspace()` function generates a specified number of evenly spaced values between a starting and ending value.

Unlike `arange()`, it specifies the number of values instead of the step size.

## Syntax

```python
np.linspace(
    start,
    stop,
    num=50,
    endpoint=True,
    retstep=False,
    dtype=None
)
```

### Parameters

| Parameter | Description |
|---|---|
| start | Starting value. |
| stop | Ending value. |
| num | Number of values to generate. |
| endpoint | If True, includes the stop value. |
| retstep | If True, also returns the spacing. |
| dtype | Optional data type of the output. |

## Example 1: Basic usage

```python
a = np.linspace(0, 10, 5)
print(a)
```

Output:

```text
[ 0.   2.5  5.   7.5 10. ]
```

Explanation:

- Start = 0
- Stop = 10
- Number of values = 5
- Spacing = 2.5

The generated values are:

0, 2.5, 5, 7.5, 10

## Example 2: Excluding the endpoint

```python
a = np.linspace(0, 10, 5, endpoint=False)
print(a)
```

Output:

```text
[0. 2. 4. 6. 8.]
```

The ending value 10 is excluded.

## Example 3: Returning the step size

```python
a, step = np.linspace(0, 10, 5, retstep=True)

print(a)
print(step)
```

Output:

```text
[ 0.   2.5  5.   7.5 10. ]
2.5
```

## Example 4: Generating 100 values

```python
a = np.linspace(0, 1, 100)

print(a.shape)
print(a.size)
```

Output:

```text
(100,)
100
```

## Mathematical formula

When the endpoint is included and there is more than one point, the spacing is:

```text
step = (stop - start) / (num - 1)
```

For example:

```python
a = np.linspace(0, 20, 5)
```

Spacing:

```text
(20 - 0) / (5 - 1) = 5
```

Output:

```text
[ 0.  5. 10. 15. 20.]
```

## Important points

- `linspace()` specifies the number of values.
- The endpoint is included by default.
- It is useful when an exact number of evenly spaced samples is required.
- It is frequently used in mathematical functions and scientific computing.

---

# 4. np.logspace()

## Definition

The `np.logspace()` function generates values that are evenly spaced on a logarithmic scale.

Instead of evenly spacing the values themselves, it evenly spaces their exponents.

## Syntax

```python
np.logspace(
    start,
    stop,
    num=50,
    endpoint=True,
    base=10.0,
    dtype=None
)
```

### Parameters

| Parameter | Description |
|---|---|
| start | Starting exponent. |
| stop | Ending exponent. |
| num | Number of values. |
| endpoint | Whether to include the ending exponent. |
| base | Base of the exponentiation. Defaults to 10. |
| dtype | Optional output data type. |

## Example 1: Basic usage

```python
a = np.logspace(1, 4, 4)
print(a)
```

Output:

```text
[   10.  100. 1000. 10000.]
```

Explanation:

The exponents are:

```text
1, 2, 3, 4
```

The resulting values are:

```text
10^1, 10^2, 10^3, 10^4
```

## Example 2: Using a different base

```python
a = np.logspace(1, 4, 4, base=2)
print(a)
```

Output:

```text
[ 2.  4.  8. 16.]
```

The base is 2, so the generated values are 2¹, 2², 2³ and 2⁴.

## Example 3: Generating seven values

```python
a = np.logspace(0, 3, 7)
print(a)
```

Output:

```text
[   1.            3.16227766   10.
   31.6227766   100.          316.22776602
 1000.        ]
```

## Mathematical formula

```text
output = base ** exponent
```

For example:

```python
a = np.logspace(0, 3, 4)
```

Output:

```text
[   1.   10.  100. 1000.]
```

## Important points

- `logspace()` evenly spaces exponents, not the output values.
- The default base is 10.
- It is useful for values spanning several orders of magnitude.
- It is commonly used when exploring logarithmic ranges of machine-learning hyperparameters.

---

# 5. np.geomspace()

## Definition

The `np.geomspace()` function generates numbers that are evenly spaced geometrically.

This means the ratio between consecutive values remains constant.

## Syntax

```python
np.geomspace(
    start,
    stop,
    num=50,
    endpoint=True,
    dtype=None
)
```

### Parameters

| Parameter | Description |
|---|---|
| start | Starting value. |
| stop | Ending value. |
| num | Number of values. |
| endpoint | Whether to include the ending value. |
| dtype | Optional output data type. |

## Example 1: Basic usage

```python
a = np.geomspace(1, 1000, 4)
print(a)
```

Output:

```text
[   1.   10.  100. 1000.]
```

The ratio between consecutive values is 10.

## Example 2: Geometric progression

```python
a = np.geomspace(2, 162, 5)
print(a)
```

Output:

```text
[  2.   6.  18.  54. 162.]
```

Each value is multiplied by 3.

## Example 3: Negative endpoints

```python
a = np.geomspace(-1, -1000, 4)
print(a)
```

Output:

```text
[   -1.   -10.  -100. -1000.]
```

For real-valued geometric spacing, both endpoints must be nonzero and have the same sign.

## Mathematical formula

For positive endpoints, the common ratio is:

```text
ratio = (stop / start) ** (1 / (num - 1))
```

For example:

```python
a = np.geomspace(1, 81, 4)
print(a)
```

Output:

```text
[ 1.  4. 16. 64. 81.]
```

Correction: for these endpoints, the values are not a constant-ratio sequence. A sequence with four points from 1 to 81 has ratio 81 ** (1/3), approximately 4.3267.

## Important points

- `geomspace()` uses a constant ratio between successive values.
- It specifies the endpoints directly.
- It is useful for geometric progressions and multiplicative scales.
- Unlike `logspace()`, it accepts starting and ending values rather than exponents.

---

# 6. np.meshgrid()

## Definition

The `np.meshgrid()` function converts one-dimensional coordinate arrays into coordinate matrices.

It is mainly used to create two-dimensional and three-dimensional grids for mathematical functions, contour plots and surface plots.

## Syntax

```python
np.meshgrid(*xi, indexing='xy', sparse=False)
```

### Parameters

| Parameter | Description |
|---|---|
| xi | One-dimensional coordinate arrays. |
| indexing | Specifies either Cartesian ('xy') or matrix ('ij') indexing. |
| sparse | If True, returns sparse coordinate arrays. |

## Example 1: Basic two-dimensional grid

```python
x = np.array([1, 2, 3])
y = np.array([4, 5])

X, Y = np.meshgrid(x, y)

print(X)
print(Y)
```

Output:

```text
X =
[[1 2 3]
 [1 2 3]]

Y =
[[4 4 4]
 [5 5 5]]
```

Explanation:

- X contains the x-coordinates.
- Y contains the y-coordinates.
- Each matching pair represents one point in the coordinate grid.

The coordinate pairs are:

```text
(1, 4) (2, 4) (3, 4)
(1, 5) (2, 5) (3, 5)
```

## Example 2: Creating a mathematical surface

Suppose:

```text
z = x² + y²
```

Python implementation:

```python
x = np.linspace(-2, 2, 5)
y = np.linspace(-2, 2, 5)

X, Y = np.meshgrid(x, y)

Z = X**2 + Y**2

print(Z)
```

Output:

```text
[[8. 5. 4. 5. 8.]
 [5. 2. 1. 2. 5.]
 [4. 1. 0. 1. 4.]
 [5. 2. 1. 2. 5.]
 [8. 5. 4. 5. 8.]]
```

Here, Z contains the function values at every coordinate pair.

## Example 3: Using indexing='ij'

```python
x = np.array([1, 2, 3])
y = np.array([4, 5])

X, Y = np.meshgrid(x, y, indexing='ij')

print(X)
print(Y)
```

Output:

```text
X =
[[1 1]
 [2 2]
 [3 3]]

Y =
[[4 5]
 [4 5]
 [4 5]]
```

The difference is:

- 'xy': follows Cartesian plotting conventions.
- 'ij': follows the order of the input arrays.

## Example 4: Sparse meshgrid

```python
x = np.array([1, 2, 3])
y = np.array([4, 5])

X, Y = np.meshgrid(x, y, sparse=True)

print(X.shape)
print(Y.shape)
```

Output:

```text
(1, 3)
(2, 1)
```

Sparse coordinate arrays use less memory and can be used with broadcasting.

## Important points

- `meshgrid()` creates coordinate matrices.
- The default indexing is 'xy'.
- The 'ij' option is useful for matrix indexing.
- Sparse grids can save memory.
- It is widely used for plotting mathematical functions.

---

# 7. np.mgrid

## Definition

The `np.mgrid` object generates dense coordinate grids using slice notation.

It is convenient when you want to generate a multidimensional grid without explicitly creating coordinate arrays.

## Syntax

```python
np.mgrid[start:stop:step]
```

For multidimensional grids, separate slices with commas.

## Example 1: One-dimensional grid

```python
a = np.mgrid[0:5:1]
print(a)
```

Output:

```text
[0 1 2 3 4]
```

## Example 2: Two-dimensional grid

```python
grid = np.mgrid[0:3, 0:4]

print(grid)
```

Output:

```text
[[[0 0 0 0]
  [1 1 1 1]
  [2 2 2 2]]

 [[0 1 2 3]
  [0 1 2 3]
  [0 1 2 3]]]
```

The first array represents the row coordinates, and the second represents the column coordinates.

## Example 3: Using a complex step

A complex step specifies the number of points instead of the step size.

```python
a = np.mgrid[0:10:5j]
print(a)
```

Output:

```text
[ 0.   2.5  5.   7.5 10. ]
```

Here, 5j means five evenly spaced points, including both endpoints.

## Example 4: Three-dimensional grid

```python
grid = np.mgrid[0:2, 0:3, 0:4]

print(grid.shape)
```

Output:

```text
(3, 2, 3, 4)
```

The first dimension holds the three coordinate arrays.

## Important points

- `mgrid` generates dense coordinate grids.
- It supports multiple dimensions.
- Ordinary steps exclude the stop value.
- Complex steps specify the number of points and include the endpoint.
- It is useful for numerical simulations and multidimensional calculations.

---

# 8. np.ogrid()

## Definition

The `np.ogrid()` object generates open or sparse coordinate grids.

Unlike `mgrid`, it does not repeat coordinates across every dimension. This reduces memory usage.

## Syntax

```python
np.ogrid[start:stop:step]
```

It also supports multidimensional slice notation.

## Example 1: One-dimensional grid

```python
a = np.ogrid[0:5:1]
print(a)
```

Output:

```text
[0 1 2 3 4]
```

## Example 2: Two-dimensional open grid

```python
x, y = np.ogrid[0:3, 0:4]

print(x)
print(y)
```

Output:

```text
x =
[[0]
 [1]
 [2]]

y =
[[0 1 2 3]]
```

Shapes:

```python
print(x.shape)
print(y.shape)
```

Output:

```text
(3, 1)
(1, 4)
```

## Example 3: Using broadcasting

```python
x, y = np.ogrid[-2:3, -2:3]

Z = x**2 + y**2

print(Z)
```

Output:

```text
[[8 5 4 5 8]
 [5 2 1 2 5]
 [4 1 0 1 4]
 [5 2 1 2 5]
 [8 5 4 5 8]]
```

The coordinate arrays are sparse, but broadcasting creates the full result.

## Important points

- `ogrid()` produces sparse coordinate arrays.
- It is memory-efficient for large grids.
- It works with NumPy broadcasting.
- It is particularly useful for evaluating functions over multidimensional domains.

---

# 9. Difference between arange() and linspace()

| Feature | arange() | linspace() |
|---|---|---|
| Main purpose | Generate values using a step | Generate a fixed number of values |
| Input | Start, stop, step | Start, stop, number of points |
| Stop | Excluded | Included by default |
| Floating-point support | Yes | Yes |
| Exact number of points | Not specified directly | Specified directly |
| Best use | Known step size | Known number of points |

Example:

```python
a = np.arange(0, 10, 2)
b = np.linspace(0, 10, 5)

print(a)
print(b)
```

Output:

```text
[0 2 4 6 8]
[ 0.   2.5  5.   7.5 10. ]
```

---

# 10. Difference between logspace() and geomspace()

| Feature | logspace() | geomspace() |
|---|---|---|
| Input | Start and stop exponents | Start and stop values |
| Default base | 10 | Not applicable |
| Spacing | Equal exponent intervals | Equal ratio |
| Endpoints | Powers of the specified base | Specified values |
| Main use | Logarithmic ranges | Geometric sequences |

Example:

```python
a = np.logspace(0, 3, 4)
b = np.geomspace(1, 1000, 4)

print(a)
print(b)
```

Output:

```text
[   1.   10.  100. 1000.]
[   1.   10.  100. 1000.]
```

Both produce the same values in this example, but their inputs represent different things.

---

# 11. Difference between meshgrid(), mgrid and ogrid()

| Feature | meshgrid() | mgrid | ogrid() |
|---|---|---|---|
| Input | Coordinate arrays | Slice notation | Slice notation |
| Output | Coordinate arrays | Dense grid | Sparse grid |
| Memory | Depends on sparse option | Higher | Usually lower |
| Indexing | 'xy' or 'ij' | Matrix-style | Matrix-style |
| Main use | Plotting and coordinates | Dense grids | Memory-efficient grids |

---

# 12. Practical applications in data science

## 12.1 Generating data for a mathematical function

```python
x = np.linspace(-5, 5, 100)
y = x**2

print(y[:5])
```

This generates 100 x-values and evaluates a quadratic function.

## 12.2 Creating logarithmic hyperparameter values

```python
learning_rates = np.logspace(-5, -1, 5)

print(learning_rates)
```

Output:

```text
[1.e-05 1.e-04 1.e-03 1.e-02 1.e-01]
```

These values can be used when exploring a machine-learning model's learning rate.

## 12.3 Creating a two-dimensional mathematical domain

```python
x, y = np.ogrid[-5:6, -5:6]

z = x**2 + y**2

print(z.shape)
```

Output:

```text
(11, 11)
```

This produces a two-dimensional array of values for a mathematical function.

## 12.4 Generating data for a surface plot

```python
import numpy as np
import matplotlib.pyplot as plt

x = np.linspace(-5, 5, 100)
y = np.linspace(-5, 5, 100)

X, Y = np.meshgrid(x, y)
Z = np.sin(np.sqrt(X**2 + Y**2))

fig = plt.figure()
ax = fig.add_subplot(111, projection='3d')

ax.plot_surface(X, Y, Z)

plt.show()
```

This generates and plots a three-dimensional mathematical surface.

---

# 13. Common mistakes

### Mistake 1: Expecting arange() to include the stop value

```python
np.arange(1, 6)
```

Output:

```text
[1 2 3 4 5]
```

The stop value is excluded.

### Mistake 2: Confusing num with step

```python
np.linspace(0, 10, 5)
```

The third argument means five values, not a step of five.

### Mistake 3: Confusing logspace() inputs with actual values

```python
np.logspace(1, 3, 3)
```

Output:

```text
[  10.  100. 1000.]
```

The inputs 1 and 3 are exponents.

### Mistake 4: Confusing dense and sparse grids

```python
x, y = np.ogrid[0:3, 0:4]

print(x.shape)
print(y.shape)
```

Output:

```text
(3, 1)
(1, 4)
```

These are sparse coordinate arrays, not full 3-by-4 matrices.

---

# 14. Quick revision notes

| Function | Remember |
|---|---|
| np.arange() | Step size |
| np.linspace() | Number of points |
| np.logspace() | Equally spaced exponents |
| np.geomspace() | Constant ratio |
| np.meshgrid() | Coordinate matrices |
| np.mgrid | Dense grid |
| np.ogrid() | Sparse grid |

### Important formulas

Spacing for linspace when the endpoint is included and num > 1:

```text
(stop - start) / (num - 1)
```

Geometric ratio for positive endpoints and num > 1:

```text
(stop / start) ** (1 / (num - 1))
```

Logarithmic generation:

```text
base ** exponent
```

---

# 15. Practice questions

## Beginner

1. Generate numbers from 0 to 20 with a step size of 2 using arange().
2. Generate 10 equally spaced numbers between 0 and 100 using linspace().
3. Generate powers of 10 from 10^0 to 10^5 using logspace().
4. Generate five geometrically spaced values from 1 to 625.
5. Create a coordinate grid using meshgrid() with x = [1, 2, 3] and y = [4, 5].

## Intermediate

6. Generate 50 points between -10 and 10 and calculate their squares.
7. Generate 10 logarithmically spaced learning rates between 0.0001 and 1.
8. Use meshgrid() to calculate z = x² + y².
9. Generate a two-dimensional dense grid with mgrid.
10. Generate a sparse two-dimensional grid with ogrid and calculate the sum of the squares of its coordinates.

## Advanced

11. Compare the memory usage of meshgrid() with sparse=True and sparse=False for large arrays.
12. Create a three-dimensional grid using mgrid.
13. Use ogrid and broadcasting to evaluate a Gaussian function.
14. Generate logarithmically spaced values for exploring model hyperparameters.
15. Create a contour plot of z = sin(x) * cos(y) using meshgrid().

---

# 16. Final summary

Deterministic domain and grid generators are fundamental NumPy tools for generating numerical sequences and coordinate grids.

- Use arange() when the step size is known.
- Use linspace() when the number of points is known.
- Use logspace() for logarithmic scales.
- Use geomspace() for geometric scales.
- Use meshgrid() to construct coordinate matrices.
- Use mgrid for dense coordinate grids.
- Use ogrid for memory-efficient sparse coordinate grids.

Understanding these functions makes it easier to work with numerical domains, mathematical functions, simulations, machine learning and data visualization.