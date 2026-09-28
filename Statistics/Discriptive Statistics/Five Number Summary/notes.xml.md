# Five-Number Summary

The **Five-Number Summary** is a statistical summary that describes a dataset using exactly five values:

1. Minimum
2. First Quartile ($Q_1$)
3. Median ($Q_2$)
4. Third Quartile ($Q_3$)
5. Maximum

---

## 1. Minimum

The **minimum** is the smallest value in the dataset.

Example:

$$
10,\ 20,\ 30,\ 40,\ 50
$$

Therefore:

$$
Minimum = 10
$$

---

## 2. First Quartile ($Q_1$)

The **First Quartile ($Q_1$)** represents the 25th percentile.

$$
Q_1 = P_{25}
$$

Approximately 25% of the observations are at or below $Q_1$, depending on the quartile calculation method used.

---

## 3. Median ($Q_2$)

The **median** is the middle value of an ordered dataset.

The median is also called the Second Quartile ($Q_2$).

$$
Q_2 = P_{50} = Median
$$

---

## 4. Third Quartile ($Q_3$)

The **Third Quartile ($Q_3$)** represents the 75th percentile.

$$
Q_3 = P_{75}
$$

Approximately 75% of the observations are at or below $Q_3$, depending on the quartile calculation method used.

---

## 5. Maximum

The **maximum** is the largest value in the dataset.

Example:

$$
10,\ 20,\ 30,\ 40,\ 50
$$

Therefore:

$$
Maximum = 50
$$

---

# Five-Number Summary Formula

The complete Five-Number Summary is:

$$
\boxed{
Minimum,\ Q_1,\ Median,\ Q_3,\ Maximum
}
$$

---

# Example

Consider the ordered dataset:

$$
10,\ 20,\ 30,\ 40,\ 50,\ 60,\ 70
$$

Using a common introductory quartile convention:

$$
Minimum = 10
$$

$$
Q_1 = 20
$$

$$
Median = 40
$$

$$
Q_3 = 60
$$

$$
Maximum = 70
$$

Therefore:

$$
\boxed{
(10,\ 20,\ 40,\ 60,\ 70)
}
$$

---

# Five-Number Summary Table

| Statistic      | Value | Meaning         |
| -------------- | ----: | --------------- |
| Minimum        |    10 | Smallest value  |
| $Q_1$          |    20 | 25th percentile |
| Median ($Q_2$) |    40 | 50th percentile |
| $Q_3$          |    60 | 75th percentile |
| Maximum        |    70 | Largest value   |

---

# Interquartile Range (IQR)

The **IQR is not one of the five values** in the Five-Number Summary.

It is a separate measure of dispersion calculated from $Q_1$ and $Q_3$.

### Formula

$$
IQR = Q_3 - Q_1
$$

For the example:

$$
IQR = 60 - 20
$$

$$
IQR = 40
$$

---

# Range

The range is another measure of dispersion.

### Formula

$$
Range = Maximum - Minimum
$$

For the example:

$$
Range = 70 - 10
$$

$$
Range = 60
$$

---

# Five-Number Summary vs IQR vs Range

| Concept             | Formula / Values               | Purpose                       |
| ------------------- | ------------------------------ | ----------------------------- |
| Five-Number Summary | Min, $Q_1$, Median, $Q_3$, Max | Summarizes the distribution   |
| IQR                 | $Q_3-Q_1$                      | Measures spread of middle 50% |
| Range               | Max-Min                        | Measures total range          |

---

# Relationship with Percentiles

Quartiles are directly related to percentiles:

$$
Q_1 = P_{25}
$$

$$
Q_2 = P_{50}
$$

$$
Q_3 = P_{75}
$$

Therefore:

```text
Percentiles
│
├── P25 → Q1
├── P50 → Q2 → Median
└── P75 → Q3
```

---

# Box Plot

The Five-Number Summary is closely related to a **box plot**.

A simplified representation is:

```text
Minimum ───── Q1 ┌──────────────┐ Q3 ───── Maximum
                 │              │
                 │   Median     │
                 │      │       │
                 └──────────────┘
```

The box represents the middle 50% of the data:

$$
Q_1 \rightarrow Q_3
$$

The line inside the box represents the median.

---

# Outlier Detection Using IQR

The IQR can be used to identify potential outliers.

### Step 1: Calculate IQR

$$
IQR = Q_3-Q_1
$$

### Step 2: Calculate Lower Fence

$$
Lower\ Fence = Q_1 - 1.5(IQR)
$$

### Step 3: Calculate Upper Fence

$$
Upper\ Fence = Q_3 + 1.5(IQR)
$$

Values outside these fences are commonly flagged as potential outliers.

---

# Example of Outlier Detection

Suppose:

$$
Q_1 = 20
$$

and:

$$
Q_3 = 60
$$

Then:

$$
IQR = 60-20 = 40
$$

### Lower Fence

$$
Lower\ Fence = 20 - 1.5(40)
$$

$$
Lower\ Fence = -40
$$

### Upper Fence

$$
Upper\ Fence = 60 + 1.5(40)
$$

$$
Upper\ Fence = 120
$$

Therefore:

$$
Lower\ Fence=-40
$$

$$
Upper\ Fence=120
$$

Any observation below -40 or above 120 is a potential outlier using the 1.5 × IQR rule.

---

# Five-Number Summary and Data Science

The Five-Number Summary is useful in:

* Exploratory Data Analysis (EDA)
* Data profiling
* Data cleaning
* Outlier detection
* Feature analysis
* Distribution analysis
* Box plots
* Business analytics
* Machine Learning preprocessing

---

# Python Example

Using NumPy:

```python
import numpy as np

data = [10, 20, 30, 40, 50, 60, 70]

minimum = np.min(data)
q1 = np.percentile(data, 25)
median = np.percentile(data, 50)
q3 = np.percentile(data, 75)
maximum = np.max(data)

print("Minimum:", minimum)
print("Q1:", q1)
print("Median:", median)
print("Q3:", q3)
print("Maximum:", maximum)
```

---

# Python Using Pandas

```python
import pandas as pd

data = pd.Series([10, 20, 30, 40, 50, 60, 70])

print(data.describe())
```

`describe()` provides:

* Count
* Mean
* Standard deviation
* Minimum
* Q1
* Median
* Q3
* Maximum

---

# Important Note About Quartiles

Different statistical software and textbooks can use different methods to calculate quartiles.

Therefore, $Q_1$ and $Q_3$ can sometimes have different values for the same dataset.

For reproducible Data Science work, specify the percentile or quartile calculation method when the exact result matters.

---

# Complete Tree

```text
Five-Number Summary
│
├── Minimum
│
├── Q1
│   └── P25
│
├── Median
│   ├── Q2
│   └── P50
│
├── Q3
│   └── P75
│
└── Maximum
```

### Related Concepts

```text
Five-Number Summary
│
├── Minimum
├── Q1
├── Median
├── Q3
└── Maximum
     │
     ├── IQR = Q3 - Q1
     │
     ├── Range = Maximum - Minimum
     │
     └── Box Plot
          │
          └── Potential Outliers
```

---

# Quick Revision

$$
\boxed{
Five\text{-}Number\ Summary
=
Minimum,\ Q_1,\ Median,\ Q_3,\ Maximum
}
$$

$$
\boxed{
Q_1=P_{25}
}
$$

$$
\boxed{
Median=Q_2=P_{50}
}
$$

$$
\boxed{
Q_3=P_{75}
}
$$

$$
\boxed{
IQR=Q_3-Q_1
}
$$

$$
\boxed{
Range=Maximum-Minimum
}
$$

> **Remember:** The Five-Number Summary contains exactly five values. IQR and Range are related measures of dispersion, but they are not part of the five-number summary itself.
