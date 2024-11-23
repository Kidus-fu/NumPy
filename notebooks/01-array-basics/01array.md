# **This is base of array in NumPy 1D,2D,3D array and Some Functions**

## **1D Arrays in NumPy**

A 1D array is essentially a list of elements. It has only one axis.

### **Example: Creating a 1D Array**

```python
import numpy as np

# Creating a 1D array
array_1d = np.array([1, 2, 3, 4, 5])
print("1D Array:", array_1d)

# Shape of the array
print("Shape:", array_1d.shape)

# Accessing elements
print("First Element:", array_1d[0])
print("Last Element:", array_1d[-1])
```

## **2D Arrays in NumPy**

A 2D array is a grid or a matrix. It has two axes (rows and columns).

### **Example: Creating a 2D Array**

```python
# Creating a 2D

array_2d = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])

print("2D Array:\n", array_2d)

# Shape of the array 
print("Shape:", array_2d.shape) 

# Accessing elements 
print("Element at (0, 0):", array_2d[0, 0])
print("Row 1:", array_2d[0]) 

print("Column 2:", array_2d[:, 1])
```

## **3D Arrays in NumPy**

A 3D array is a collection of matrices stacked together. It has three axes.

### **Example: Creating a 3D Array**

```python
# Creating a 3D array
array_3d = np.array([
    [[1, 2, 3], [4, 5, 6]],
    [[7, 8, 9], [10, 11, 12]]
])
print("3D Array:\n", array_3d)

# Shape of the array
print("Shape:", array_3d.shape)

# Accessing elements
print("Element at (0, 1, 2):", array_3d[0, 1, 2])  # 6
```

## **Key NumPy Array Functions**

### **1\. Reshaping Arrays**

Reshape arrays to change their dimensions.

```python
# Reshaping a 1D array to 2D

reshaped = np.array([1, 2, 3, 4, 5, 6]).reshape(2, 3) 

print("Reshaped Array:\n", reshaped)
```

### **2\. Basic Mathematical Operations**

Perform element-wise operations.

```python
array = np.array([1, 2, 3])

print("Array + 10:", array + 10) # Add 10 to each element 
print("Array * 2:", array * 2) # Multiply each element by 2
```

### **3\. Statistical Functions**

Compute basic statistics.

```python
array = np.array([1, 2, 3, 4, 5])
print("Mean:", np.mean(array))
print("Sum:", np.sum(array))
print("Max:", np.max(array))
print("Min:", np.min(array))
```

### **4\. Broadcasting**

Broadcast smaller arrays to larger ones.

```python
array = np.array([[1, 2, 3], [4, 5, 6]])
print("Broadcasting with scalar:\n", array + 10)
```

### **5\. Slicing and Indexing**

Access subarrays or elements

```python
array = np.array([1, 2, 3, 4, 5])
print("Slice [1:4]:", array[1:4])  # Get elements from index 1 to 3
```

### **6\. Creating Special Arrays**

```python
# Array of zeros
zeros = np.zeros((2, 3))
print("Zeros:\n", zeros)

# Array of ones
ones = np.ones((3, 3))
print("Ones:\n", ones)

# Identity matrix
identity = np.eye(3)
print("Identity Matrix:\n", identity)

# Random array
random_array = np.random.rand(3, 3)
print("Random Array:\n", random_array)
```