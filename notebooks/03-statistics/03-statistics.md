### 03 - Statistics in NumPy

In this notebook, we will explore common statistical operations using NumPy, which will help you summarize and understand data distributions.

### 1\. **Mean (Average)**

The **mean** is just the average of all the numbers in a list. It tells you the "central" value of your data.

#### How to calculate it:

*   Add all the numbers together.
*   Divide the sum by how many numbers there are.

For example, let's say we have the numbers **\[1, 2, 3, 4, 5\]**.

To calculate the mean:

1.  Add them up: **1 + 2 + 3 + 4 + 5 = 15**
2.  Divide by 5 (since there are 5 numbers): **15 / 5 = 3**

So, the **mean** is **3**.

#### Why is it useful?

The mean helps summarize a set of data into a single number. It’s useful when you want to know the "average" value of something, like the average score of students in a class.

```
import numpy as np

data = np.array([1, 2, 3, 4, 5])

# Mean
mean_value = np.mean(data)
print(f"Mean: {mean_value}")
```

Output:

`Mean: 3.0`

*   The mean is calculated as the sum of all elements divided by the number of elements. In this case, (1 + 2 + 3 + 4 + 5) / 5 = 3.

### 2\. **Median**

The **median** is the middle value of a sorted list of numbers. If there’s an even number of values, the median is the average of the two middle numbers.

#### How to calculate it:

1.  Arrange the numbers in order.
2.  If there's an odd number of values, the middle one is the median.
3.  If there's an even number, find the average of the two middle numbers.

For example, let's use **\[1, 2, 3, 4, 5\]**:

*   Sorted: **\[1, 2, 3, 4, 5\]**
*   The middle value is **3**, so the median is **3**.

For an even number set, like **\[1, 2, 3, 4\]**:

*   Sorted: **\[1, 2, 3, 4\]**
*   The middle values are **2** and **3**, so the median is the average: **(2 + 3) / 2 = 2.5**.

#### Why is it useful?

The median is useful when the data has extreme values (outliers). It’s less affected by very high or very low numbers, making it a good choice when you want a "central" value but without outliers skewing the result.

```
# Median
median_value = np.median(data)
print(f"Median: {median_value}")
```

Output:

`Median: 3.0`

*   The median of \[1, 2, 3, 4, 5\] is 3, since it's the middle value.

### 3\. **Mode (Most Frequent Value)**

The **mode** is the number that appears most often in a dataset. If no number repeats, the dataset has **no mode**.

#### How to calculate it:

*   Look for the number that occurs the most times.
*   If all numbers appear the same number of times, there’s no mode.

For example, in **\[1, 2, 2, 3, 4\]**:

*   The number **2** appears twice, so **2** is the mode.

In **\[1, 2, 3, 4\]**, every number appears only once, so there is **no mode**.

#### Why is it useful?

The mode is useful when you want to know which value occurs the most. For example, in a survey about favorite colors, the mode tells you the most popular color.

```
from scipy import stats

# Mode
mode_value = stats.mode(data)
print(f"Mode: {mode_value.mode[0]}")
```

Output:

`Mode: 1`

*   The mode is the value that appears most frequently in the dataset.

### 4\. **Variance**

**Variance** tells you how spread out your data is. If the values in your data are very spread out from the mean, the variance will be high. If they are close to the mean, the variance will be low.

#### How to calculate it:

1.  Find the **mean** of the data.
2.  Subtract the mean from each value to find the "difference."
3.  Square each difference (to get rid of negative numbers).
4.  Average those squared differences.

For example, with **\[1, 2, 3, 4, 5\]**:

1.  Mean is **3**.
2.  Differences from the mean: **\[-2, -1, 0, 1, 2\]**.
3.  Squared differences: **\[4, 1, 0, 1, 4\]**.
4.  Average the squared differences: **(4 + 1 + 0 + 1 + 4) / 5 = 2**.

So, the **variance** is **2**.

#### Why is it useful?

Variance gives a sense of how spread out the data is. A **high variance** means the values are far from the mean, while a **low variance** means they are close to the mean.

```
# Variance
variance_value = np.var(data)
print(f"Variance: {variance_value}")
```

Output:

`Variance: 2.0`

*   Variance is the average of the squared differences from the mean. For example, the variance of the data \[1, 2, 3, 4, 5\] is 2.

### 5\. **Standard Deviation**

The **standard deviation** is just the square root of the variance. It’s another way to measure how spread out the data is, but it’s in the same units as the original data, making it easier to understand.

#### How to calculate it:

1.  Calculate the variance (as we did earlier).
2.  Take the square root of the variance.

For example, with **variance = 2**:

*   The **standard deviation** is **√2 ≈ 1.41**.

#### Why is it useful?

Standard deviation is easier to interpret than variance because it’s in the same units as the data. For example, if you're measuring people's heights in centimeters, the standard deviation tells you how much people's heights differ from the average height in centimeters.

```
# Standard Deviation
std_dev_value = np.std(data)
print(f"Standard Deviation: {std_dev_value}")
```

Output:

`Standard Deviation: 1.4142135623730951`

*   Standard deviation is a more interpretable measure of the spread compared to variance because it is in the same units as the data.

### 6\. **Minimum and Maximum**

The **minimum** is the smallest number, and the **maximum** is the largest number in a dataset.

#### How to calculate it:

*   The **minimum** is the lowest value.
*   The **maximum** is the highest value.

For example, with **\[1, 2, 3, 4, 5\]**:

*   Minimum: **1**
*   Maximum: **5**

#### Why is it useful?

Knowing the minimum and maximum values helps you understand the range of your data. It gives you a sense of the smallest and largest values, which can be useful when analyzing extremes.

```
# Minimum and Maximum
min_value = np.min(data)
max_value = np.max(data)

print(f"Minimum: {min_value}")
print(f"Maximum: {max_value}")
```

Output:

`Minimum: 1 Maximum: 5`

*   The minimum value is 1 and the maximum value is 5.

### 7\. **Percentiles**

A **percentile** tells you the value below which a certain percentage of your data lies. For example, the **50th percentile** is the **median**, which is the middle value.

#### How to calculate it:

*   Find the value below which a certain percentage of the data falls. For instance, the 25th percentile means 25% of the data is less than that value.

For example, in **\[1, 2, 3, 4, 5\]**:

*   The **25th percentile** is **2** (25% of the data is less than 2).
*   The **50th percentile (median)** is **3**.
*   The **75th percentile** is **4**.

#### Why is it useful?

Percentiles are useful to understand the distribution of data. For example, the 90th percentile gives you a sense of what the "top 10%" looks like.

```
# Percentile (e.g., 25th, 50th, 75th)
percentile_25 = np.percentile(data, 25)
percentile_50 = np.percentile(data, 50)
percentile_75 = np.percentile(data, 75)

print(f"25th Percentile: {percentile_25}")
print(f"50th Percentile (Median): {percentile_50}")
print(f"75th Percentile: {percentile_75}")
```

Output:

`25th Percentile: 2.0 50th Percentile (Median): 3.0 75th Percentile: 4.0`

*   Percentiles are useful for understanding the spread of data.

### 8\. **Correlation**

**Correlation** tells you how two sets of data are related. If two sets of data have a high correlation, it means when one set increases, the other tends to increase as well (or decrease, depending on the type of correlation).

#### How to calculate it:

*   Calculate a number between -1 and 1, where:
    *   **1** means a perfect positive correlation (both sets increase together),
    *   **\-1** means a perfect negative correlation (one set increases while the other decreases),
    *   **0** means no correlation (the sets don't affect each other).

For example, with data **\[1, 2, 3, 4, 5\]** and **\[5, 4, 3, 2, 1\]**:

*   The correlation coefficient is **\-1**, meaning they have a perfect negative correlation.

#### Why is it useful?

Correlation is useful for understanding relationships between variables. For instance, you might want to know if a student’s study hours correlate with their exam scores.

```
data_2 = np.array([5, 4, 3, 2, 1])

# Correlation coefficient
correlation = np.corrcoef(data, data_2)
print(f"Correlation Coefficient:\n{correlation}")
```

Output:

`Correlation Coefficient: [[ 1. -1.] [-1.  1.]]`

*   The correlation coefficient ranges from -1 to 1, where:
    *   1 means a perfect positive correlation,
    *   \-1 means a perfect negative correlation,
    *   0 means no correlation.

### 9\. **Cumulative Sum**

The **cumulative sum** is the running total of the values. It gives you a sense of how the sum changes as you move through the data.

#### How to calculate it:

*   Add each value one by one and keep a running total.

For example, with **\[1, 2, 3, 4, 5\]**:

*   Cumulative sum: **\[1, 3, 6, 10, 15\]**.

#### Why is it useful?

Cumulative sum is useful for tracking how something accumulates over time, such as tracking a running total of sales or expenses.

```
# Cumulative Sum
cumsum_value = np.cumsum(data)
print(f"Cumulative Sum: {cumsum_value}")
```

Output:

`Cumulative Sum: [ 1  3  6 10 15]`

*   The cumulative sum is the sum of elements as you move through the array: \[1, 3, 6, 10, 15\].

### Summary

In this notebook, we covered fundamental statistical operations in NumPy, including:

*   **Mean**: Average of values.
*   **Median**: Middle value of sorted data.
*   **Mode**: Most frequent value (using SciPy).
*   **Variance**: Measure of how much data is spread out.
*   **Standard Deviation**: Spread of data, in the same unit as the data.
*   **Min/Max**: Lowest and highest values.
*   **Percentiles**: Data values below which a given percentage of observations fall.
*   **Correlation**: Measure of relationship between two datasets.
*   **Cumulative Sum**: Running total of array elements.

These statistical functions are crucial for understanding and analyzing data, and can be used in various fields such as data analysis, machine learning, economics, and more.