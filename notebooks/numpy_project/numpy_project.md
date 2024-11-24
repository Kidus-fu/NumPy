### **Project: Weather Data Analysis**

We'll analyze a small dataset of **daily temperature readings** collected in real-time from a hypothetical sensor.

---

### **Steps to Follow**

#### 1\. **Simulate Real-Time Data**

We’ll generate synthetic weather data (e.g., temperature in °C) for 7 days, including missing values.

```
import numpy as np

# Simulated temperature data for 7 days (some missing values)
temperature_data = np.array([20.5, 22.3, np.nan, 19.8, 21.1, 25.4, np.nan])
print("Original Temperature Data:", temperature_data)
```

---

#### 2\. **Handle Missing Data**

Replace missing values (NaN) with the **mean temperature**.

```
# Replace NaN with mean temperature
mean_temp = np.nanmean(temperature_data)
temperature_data = np.where(np.isnan(temperature_data), mean_temp, temperature_data)
print("Temperature Data After Filling Missing Values:", temperature_data)
```

---

#### 3\. **Detect Outliers**

Detect extreme outliers using the **Z-score method**.

```
# Compute Z-scores
z_scores = (temperature_data - np.mean(temperature_data)) / np.std(temperature_data)

# Identify outliers (Z-score > 2 or < -2)
outliers = np.abs(z_scores) > 2
print("Outliers Detected:", temperature_data[outliers])
```

---

#### 4\. **Normalize the Data**

Scale temperatures to a range of **\[0, 1\]**.

```
# Min-max normalization
min_temp = np.min(temperature_data)
max_temp = np.max(temperature_data)
normalized_temps = (temperature_data - min_temp) / (max_temp - min_temp)
print("Normalized Temperature Data:", normalized_temps)
```

---

#### 5\. **Analyze Trends**

Compute basic statistics like **average**, **maximum**, and **minimum temperature**.

```
# Statistical analysis
average_temp = np.mean(temperature_data)
max_temp = np.max(temperature_data)
min_temp = np.min(temperature_data)

print(f"Average Temperature: {average_temp:.2f} °C")
print(f"Maximum Temperature: {max_temp:.2f} °C")
print(f"Minimum Temperature: {min_temp:.2f} °C")
```

---

#### 6\. **Visualize Data (Optional)**

Use **matplotlib** for visualization if required (you can skip if focusing only on NumPy).

---

### **Real Dataset Ideas**

1.  **Weather APIs**: Fetch live data from APIs like OpenWeatherMap or NOAA (requires API keys).
2.  **Stock Prices**: Download CSV data for stock prices and perform similar preprocessing.
3.  **IoT Sensors**: If you have access to sensors, collect real-time data for analysis.