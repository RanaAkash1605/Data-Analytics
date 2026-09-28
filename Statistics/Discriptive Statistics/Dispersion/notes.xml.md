# Measures of Dispersion

Measures of Dispersion describe **how spread out or scattered the values in a dataset are**.

Measures of central tendency such as mean, median, and mode tell us about
the **center** of the data.

Measures of dispersion tell us about the **spread** of the data.

---

# Why Do We Need Dispersion?

Consider two datasets:

### Dataset A

$$
10,\ 20,\ 30,\ 40,\ 50
$$

### Dataset B

$$
28,\ 29,\ 30,\ 31,\ 32
$$

Both datasets have the same mean:

$$
Mean_A = 30
$$

$$
Mean_B = 30
$$

However, Dataset A is much more spread out than Dataset B.

Therefore:

> Mean alone cannot completely describe a dataset.

We need measures of dispersion to understand the variability.

---

# Main Measures of Dispersion

The important measures are:

1. Range
2. Interquartile Range (IQR)
3. Quartile Deviation
4. Mean Absolute Deviation (MAD)
5. Variance
6. Standard Deviation
7. Coefficient of Variation (CV)

---

# 1. Range

Range is the difference between the largest and smallest values.

### Formula

$$
Range = Maximum - Minimum
$$

### Example

Data:

$$
10,\ 20,\ 30,\ 40,\ 50
$$

Maximum:

$$
50
$$

Minimum:

$$
10
$$

Therefore:

$$
Range = 50-10
$$

$$
Range=40
$$

### Interpretation

A range of 40 means that the distance between the smallest and
largest observations is 40 units.

### Advantages

- Very easy to calculate
- Easy to understand
- Quick measure of total spread

### Disadvantages

- Uses only minimum and maximum
- Highly affected by outliers
- Not very stable for small samples

---

# 2. Interquartile Range (IQR)

The Interquartile Range measures the spread of the **middle 50%**
of the dataset.

### Formula

$$
IQR=Q_3-Q_1
$$

Where:

- $Q_1$ = First quartile
- $Q_3$ = Third quartile

### Example

Suppose:

$$
Q_1=20
$$

and:

$$
Q_3=60
$$

Then:

$$
IQR=60-20
$$

$$
IQR=40
$$

Therefore:

**IQR = 40**

### Why IQR Is Useful

IQR is less affected by extreme values than range.

It is particularly useful when:

- Data is skewed
- Outliers are present
- We are using the median instead of the mean

---

# 3. Quartile Deviation

Quartile Deviation is also called the **Semi-Interquartile Range**.

It represents half of the IQR.

### Formula

$$
QD=\frac{Q_3-Q_1}{2}
$$

Since:

$$
IQR=Q_3-Q_1
$$

we can also write:

$$
QD=\frac{IQR}{2}
$$

### Example

If:

$$
Q_1=20
$$

and:

$$
Q_3=60
$$

then:

$$
QD=\frac{60-20}{2}
$$

$$
QD=20
$$

---

# 4. Mean Absolute Deviation (MAD)

Mean Absolute Deviation measures the average distance of observations
from a central value.

When calculated around the mean:

### Formula

$$
MAD=
\frac{\sum_{i=1}^{n}|x_i-\bar{x}|}{n}
$$

Where:

- $x_i$ = Individual observation
- $\bar{x}$ = Mean
- $n$ = Number of observations
- $|x_i-\bar{x}|$ = Absolute deviation

---

## Example

Consider:

$$
2,\ 4,\ 6
$$

### Step 1: Calculate the mean

$$
\bar{x}=\frac{2+4+6}{3}
$$

$$
\bar{x}=4
$$

### Step 2: Calculate absolute deviations

$$
|2-4|=2
$$

$$
|4-4|=0
$$

$$
|6-4|=2
$$

### Step 3: Calculate MAD

$$
MAD=\frac{2+0+2}{3}
$$

$$
MAD=\frac{4}{3}
$$

$$
MAD\approx1.33
$$

---

# 5. Variance

Variance measures the average **squared deviation** of observations
from the mean.

In simple words:

> Variance tells us how much the observations vary around the mean.


::contentReference[oaicite:0]{index=0}


---

## Population Variance

When the data represents the entire population:

$$
\sigma^2=
\frac{\sum_{i=1}^{N}(x_i-\mu)^2}{N}
$$

Where:

- $\sigma^2$ = Population variance
- $x_i$ = Observation
- $\mu$ = Population mean
- $N$ = Population size

---

## Sample Variance

When the data represents a sample:

$$
s^2=
\frac{\sum_{i=1}^{n}(x_i-\bar{x})^2}{n-1}
$$

Where:

- $s^2$ = Sample variance
- $\bar{x}$ = Sample mean
- $n$ = Sample size

### Why do we use $n-1$?

When estimating population variance from a sample, using $n-1$
provides the commonly used unbiased estimator of population variance.

This is called **Bessel's correction**.

---

# Example of Variance

Consider:

$$
2,\ 4,\ 6
$$

Mean:

$$
\bar{x}=4
$$

Deviations:

$$
2-4=-2
$$

$$
4-4=0
$$

$$
6-4=2
$$

Squared deviations:

$$
(-2)^2=4
$$

$$
0^2=0
$$

$$
2^2=4
$$

### Population Variance

$$
\sigma^2=
\frac{4+0+4}{3}
$$

$$
\sigma^2=\frac{8}{3}
$$

$$
\sigma^2\approx2.67
$$

### Sample Variance

$$
s^2=
\frac{4+0+4}{3-1}
$$

$$
s^2=4
$$

---

# 6. Standard Deviation

Standard deviation is the **square root of variance**.

It measures the spread of observations around the mean.

### Population Standard Deviation

$$
\sigma=
\sqrt{
\frac{\sum_{i=1}^{N}(x_i-\mu)^2}{N}
}
$$

### Sample Standard Deviation

$$
s=
\sqrt{
\frac{\sum_{i=1}^{n}(x_i-\bar{x})^2}{n-1}
}
$$

---

## Example

If:

$$
Variance=4
$$

then:

$$
SD=\sqrt{4}
$$

$$
SD=2
$$

### Important Difference

Variance is measured in **squared units**.

Standard deviation is measured in the **same units as the original data**.

For example:

```text
Original data     → kilograms
Variance          → kilograms²
Standard deviation → kilograms