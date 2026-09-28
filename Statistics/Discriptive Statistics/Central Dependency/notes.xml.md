# Measures of Central Tendency

Measures of Central Tendency are statistical techniques used to identify
the **central or typical value** of a dataset.

They help us answer:

> "What is a representative value of this dataset?"

The main measures are:

1. Arithmetic Mean
2. Weighted Mean
3. Median
4. Mode
5. Geometric Mean
6. Harmonic Mean
7. Trimmed Mean

---

# 1. Arithmetic Mean

The arithmetic mean is commonly called the **average**.

It is calculated by adding all observations and dividing by the
number of observations.

### Formula

$$
\bar{x} = \frac{\sum_{i=1}^{n}x_i}{n}
$$

Where:

- $\bar{x}$ = Sample mean
- $x_i$ = Individual observation
- $n$ = Number of observations
- $\sum$ = Sum of observations

---

## Example

Consider:

$$
10,\ 20,\ 30,\ 40,\ 50
$$

Sum:

$$
10+20+30+40+50=150
$$

Number of observations:

$$
n=5
$$

Therefore:

$$
\bar{x}=\frac{150}{5}=30
$$

**Mean = 30**

---

# 2. Population Mean

When we have data for the entire population, we use the population mean.

### Formula

$$
\mu = \frac{\sum_{i=1}^{N}x_i}{N}
$$

Where:

- $\mu$ = Population mean
- $N$ = Population size
- $x_i$ = Population observation

---

# 3. Sample Mean

When we work with a sample taken from a population, we use the sample mean.

### Formula

$$
\bar{x} = \frac{\sum_{i=1}^{n}x_i}{n}
$$

The sample mean is often used to estimate the population mean.

---

# 4. Weighted Mean

A weighted mean is used when different observations have
different levels of importance.

### Formula

$$
\bar{x}_w =
\frac{\sum_{i=1}^{n}w_i x_i}
{\sum_{i=1}^{n}w_i}
$$

Where:

- $x_i$ = Observation
- $w_i$ = Weight
- $w_i x_i$ = Weighted observation

---

## Example

Suppose:

| Subject | Marks | Weight |
|---------|-------|--------|
| Math | 80 | 2 |
| Science | 70 | 3 |
| English | 90 | 1 |

Then:

$$
\bar{x}_w =
\frac{(80)(2)+(70)(3)+(90)(1)}
{2+3+1}
$$

$$
= \frac{160+210+90}{6}
$$

$$
=76.67
$$

**Weighted Mean = 76.67**

---

# 5. Median

The median is the **middle value** of an ordered dataset.

Before calculating the median, arrange the observations in
ascending or descending order.

---

## Odd Number of Observations

Example:

$$
10,\ 20,\ 30,\ 40,\ 50
$$

There are 5 observations.

The middle observation is:

$$
30
$$

Therefore:

**Median = 30**

### Position Formula

For odd $n$:

$$
Position = \frac{n+1}{2}
$$

---

## Even Number of Observations

Example:

$$
10,\ 20,\ 30,\ 40
$$

The two middle values are:

$$
20,\ 30
$$

Therefore:

$$
Median = \frac{20+30}{2}
$$

$$
Median=25
$$

### Formula

For even $n$:

$$
Median =
\frac{
x_{\frac{n}{2}}+
x_{\frac{n}{2}+1}
}{2}
$$

---

# 6. Median and Outliers

The median is relatively resistant to extreme values.

Example:

$$
10,\ 20,\ 30,\ 40,\ 50
$$

Mean:

$$
30
$$

Median:

$$
30
$$

Now add an extreme value:

$$
10,\ 20,\ 30,\ 40,\ 500
$$

Mean:

$$
120
$$

Median:

$$
30
$$

The outlier has a large effect on the mean but not on the median.

### Data Science Insight

For highly skewed data or data containing strong outliers,
the median can be a more representative measure of the center.

---

# 7. Mode

The mode is the value that occurs **most frequently**.

Example:

$$
10,\ 20,\ 20,\ 30,\ 40
$$

The value 20 occurs most frequently.

Therefore:

$$
Mode=20
$$

---

# 8. Types of Mode

## Unimodal

One mode.

$$
10,\ 20,\ 20,\ 30
$$

Mode:

$$
20
$$

---

## Bimodal

Two modes.

$$
10,\ 20,\ 20,\ 30,\ 30,\ 40
$$

Modes:

$$
20,\ 30
$$

---

## Multimodal

More than two modes.

$$
10,\ 10,\ 20,\ 20,\ 30,\ 30
$$

Modes:

$$
10,\ 20,\ 30
$$

---

## No Mode

If every observation occurs only once, there is no mode.

Example:

$$
10,\ 20,\ 30,\ 40
$$

---

# 9. Geometric Mean

The geometric mean is useful for **growth rates, ratios, percentages,
and multiplicative changes**.

### Formula

$$
GM =
\left(
\prod_{i=1}^{n}x_i
\right)^{\frac{1}{n}}
$$

For two values:

$$
GM=\sqrt{x_1x_2}
$$

---

## Example

Consider:

$$
2,\ 8
$$

Then:

$$
GM=\sqrt{2\times8}
$$

$$
GM=\sqrt{16}=4
$$

Therefore:

**Geometric Mean = 4**

### Important

The geometric mean generally requires positive values.

---

# 10. Harmonic Mean

The harmonic mean is useful for **rates and ratios**, especially
when averaging rates over equal distances or quantities.

### Formula

$$
HM =
\frac{n}
{\sum_{i=1}^{n}\frac{1}{x_i}}
$$

For two values:

$$
HM=\frac{2xy}{x+y}
$$

---

## Example

Consider:

$$
2,\ 4
$$

Then:

$$
HM =
\frac{2}
{\frac{1}{2}+\frac{1}{4}}
$$

$$
HM =
\frac{2}{0.75}
$$

$$
HM\approx2.67
$$

---

# 11. Trimmed Mean

A trimmed mean is calculated after removing a specified percentage
of the smallest and largest observations.

It is useful when extreme observations may distort the arithmetic mean.

### Example

Consider:

$$
10,\ 20,\ 30,\ 40,\ 50,\ 1000
$$

The value 1000 is an extreme observation.

Removing extreme observations before calculating the mean can
reduce their influence.

### Important

The percentage removed must be specified.

For example:

- 5% trimmed mean
- 10% trimmed mean
- 20% trimmed mean

---

# 12. Midrange

The midrange is the average of the minimum and maximum values.

### Formula

$$
Midrange =
\frac{Minimum+Maximum}{2}
$$

### Example

If:

$$
Minimum=10
$$

and:

$$
Maximum=50
$$

Then:

$$
Midrange=\frac{10+50}{2}=30
$$

### Important

Midrange is highly sensitive to outliers, so it is not commonly
used as the primary measure of center in Data Science.

---

# 13. Midhinge

The midhinge is the average of the first and third quartiles.

### Formula

$$
Midhinge =
\frac{Q_1+Q_3}{2}
$$

Where:

- $Q_1$ = First quartile
- $Q_3$ = Third quartile

It describes the center of the middle 50% of the data.

---

# 14. Trimean

The trimean combines the first quartile, median, and third quartile.

### Formula

$$
Trimean =
\frac{Q_1+2Q_2+Q_3}{4}
$$

Where:

- $Q_1$ = First quartile
- $Q_2$ = Median
- $Q_3$ = Third quartile

The median receives twice the weight of Q1 and Q3.

---

# 15. Mean vs Median vs Mode

| Measure | Description | Outlier Sensitivity | Typical Use |
|---------|-------------|---------------------|-------------|
| Mean | Arithmetic average | High | Numerical, roughly symmetric data |
| Median | Middle value | Low | Skewed data |
| Mode | Most frequent value | Low | Categorical/frequency data |
| Weighted Mean | Weighted average | Depends on weights and data | Weighted observations |
| Geometric Mean | Multiplicative average | Sensitive to very small/large values | Growth rates |
| Harmonic Mean | Rate-based average | Sensitive to small values | Rates |
| Trimmed Mean | Mean after trimming extremes | Lower than ordinary mean | Data with extreme values |
| Midrange | Average of min and max | Very high | Simple descriptive summary |
| Midhinge | Average of Q1 and Q3 | Relatively low | Center of middle 50% |
| Trimean | Weighted quartile-based center | Relatively low | Robust descriptive analysis |

---

# 16. Choosing the Correct Measure

The correct measure depends on the **type and distribution of data**.

```text
                    What is your data like?
                            │
             ┌──────────────┴──────────────┐
             │                             │
       Numerical                      Categorical
             │                             │
       ┌─────┴─────┐                       │
       │           │                       ▼
    Symmetric    Skewed                  Mode
       │           │
       ▼           ▼
     Mean        Median