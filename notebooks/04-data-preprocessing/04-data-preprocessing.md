# 04 - Data Preprocessing with NumPy

In this notebook, we will explore how to preprocess datasets using NumPy. Data preprocessing is an essential step in any data analysis or machine learning pipeline. It involves cleaning, transforming, and preparing data to improve the quality of results.

1\. Importing Libraries

```python
import numpy as np
```

2\. Loading Data

You can load data into NumPy arrays from various sources, such as CSV files.

```python
# Example dataset
data = np.array([
    [25, 170, 70],
    [30, 165, 80],
    [35, 180, np.nan],  # Missing value
    [40, 175, 90],
])
print("Original Data:\n", data)
```

3\. Handling Missing Values

Missing values can be handled by replacing them with the mean, median, or a constant value.

```python
# Replace NaN with column mean
col_mean = np.nanmean(data[:, 2])  # Mean of the third column (ignoring NaN)
data[:, 2] = np.where(np.isnan(data[:, 2]), col_mean, data[:, 2])
print("Data after handling missing values:\n", data)
```

4\. Normalizing Data

Normalization scales data to a specific range, often \[0, 1\], for uniformity.

```python
# Min-max normalization for the second column (heights)
min_val = np.min(data[:, 1])
max_val = np.max(data[:, 1])
data[:, 1] = (data[:, 1] - min_val) / (max_val - min_val)
print("Data after normalization:\n", data)
```

5\. Standardizing Data

Standardization transforms data to have a mean of 0 and a standard deviation of 1.

```python
# Standardization for the third column (weights)
mean = np.mean(data[:, 2])
std_dev = np.std(data[:, 2])
data[:, 2] = (data[:, 2] - mean) / std_dev
print("Data after standardization:\n", data)
```

6\. Binning Data

Binning groups continuous values into discrete bins.

```python
# Binning ages into categories
bins = [20, 30, 40, 50]
labels = [1, 2, 3]  # Represent categories
data[:, 0] = np.digitize(data[:, 0], bins)
print("Data after binning:\n", data)
```

7\. Removing Outliers

Outliers are extreme values that can skew the results of data analysis

```python
# Remove rows where weight (third column) is more than 2 standard deviations from the mean
z_scores = np.abs((data[:, 2] - np.mean(data[:, 2])) / np.std(data[:, 2]))
data = data[z_scores < 2]
print("Data after removing outliers:\n", data)
```

8\. Feature Scaling

Feature scaling adjusts the range of variables for optimal performance

```python
# Scale all features to a range of [0, 1]
data_min = np.min(data, axis=0)
data_max = np.max(data, axis=0)
data_scaled = (data - data_min) / (data_max - data_min)
print("Data after feature scaling:\n", data_scaled)
```

9\. Saving Preprocessed Data

Save the processed dataset for future use.

```python
# Save to a CSV file
np.savetxt("processed_data.csv", data, delimiter=",", fmt="%.2f")
print("Data saved to 'processed_data.csv'")
```

### **10\. Handling Compressed Files**

#### **Saving as a Compressed** `**.npz**` **File**

A compressed `.npz` file stores multiple NumPy arrays efficiently.

```python
# Save the preprocessed data in a compressed format
np.savez_compressed("processed_data.npz", data=data_scaled)

print("Data saved to 'processed_data.npz'")
```

#### **Loading from a Compressed** `**.npz**` **File**

You can easily load compressed data later for analysis.

```python
# Load data from a compressed file
loaded_data = np.load("processed_data.npz")
data_loaded = loaded_data['data']

print("Loaded Data from 'processed_data.npz':\n", data_loaded)
```

---

### **11\. Exporting Processed Data**

#### **Saving to CSV**

If you prefer working with tools like Excel or other text-based formats, save the data as a CSV file.

```python
# Save to a CSV file
np.savetxt("processed_data.csv", data_scaled, delimiter=",", fmt="%.2f")
print("Data saved to 'processed_data.csv'")
```

#### **Saving to Text File**

For simple datasets, you can use a plain text file.

```python
# Save to a text file
np.savetxt("processed_data.txt", data_scaled, fmt="%.2f")
print("Data saved to 'processed_data.txt'")
```

---

### **12\. Loading CSV or Text Files**

#### **Loading a CSV File**

You can reload a previously saved CSV file.

```python
# Load the CSV file
loaded_csv = np.loadtxt("processed_data.csv", delimiter=",")
print("Loaded Data from 'processed_data.csv':\n", loaded_csv)
```

#### **Loading a Text File**

Similarly, text files can be reloaded.

```python
# Load the text file
loaded_txt = np.loadtxt("processed_data.txt")
print("Loaded Data from 'processed_data.txt':\n", loaded_txt)
```

---

### **13\. Cleaning Temporary or Old Files**

It's good practice to clean up unused files to save disk space.

```python
import os

# Delete unnecessary files
if os.path.exists("processed_data.csv"):
    os.remove("processed_data.csv")
    print("'processed_data.csv' has been deleted.")

if os.path.exists("processed_data.txt"):
    os.remove("processed_data.txt")
    print("'processed_data.txt' has been deleted.")
```

This notebook covers:

*   Handling missing values.
*   Normalizing and standardizing data.
*   Binning continuous data into categories.
*   Removing outliers to clean data.
*   Scaling features for uniformity.
*   Saving the processed dataset for future analysis.
*   Saving processed data in compressed `.npz` format.
*   Reloading compressed files.
*   Exporting preprocessed data as `.csv` or `.txt`.
*   Cleaning up unused files.

Data preprocessing is a critical step in ensuring clean, reliable inputs for analysis or modeling.