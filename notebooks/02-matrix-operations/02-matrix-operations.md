## **02 - Matrix Operations in Numpy**

In this notebook, we will explore how to perform basic and advanced matrix operations using NumPy. Matrices are a fundamental part of data manipulation, machine learning, and linear algebra.

---

### **1\. Creating Matrices**

A matrix in NumPy is simply a 2D array.

#### **Examples:**

```python
import numpy as np

# Creating a matrix
matrix_a = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])
print("Matrix A:\n", matrix_a)

# Creating a matrix of zeros
zeros_matrix = np.zeros((3, 3))
print("Zeros Matrix:\n", zeros_matrix)

# Creating a matrix of ones
ones_matrix = np.ones((2, 4))
print("Ones Matrix:\n", ones_matrix)

# Creating an identity matrix
identity_matrix = np.eye(3)
print("Identity Matrix:\n", identity_matrix)
```

---

### **2\. Basic Matrix Operations**

#### **Addition and Subtraction**

```python
matrix_b = np.array([[9, 8, 7], [6, 5, 4], [3, 2, 1]])

# Matrix addition
result_add = matrix_a + matrix_b
print("Matrix Addition:\n", result_add)

# Matrix subtraction
result_sub = matrix_a - matrix_b
print("Matrix Subtraction:\n", result_sub)
```

#### **Element-wise Multiplication**

```python
result_mul = matrix_a * matrix_b
print("Element-wise Multiplication:\n", result_mul)
```

---

### **3\. Matrix Multiplication**

#### **Dot Product**

Matrix multiplication involves the dot product of rows and columns.

```python
# Dot product
result_dot = np.dot(matrix_a, matrix_b)
print("Matrix Multiplication (Dot Product):\n", result_dot)
```

#### **@ Operator (Preferred for Matrix Multiplication)**

```python
# Using @ operator for matrix multiplication
result_at = matrix_a @ matrix_b
print("Matrix Multiplication (@ Operator):\n", result_at)
```

---

### **4\. Transpose of a Matrix**

The transpose of a matrix flips it over its diagonal, interchanging rows and columns.

```python
# Transpose of a matrix
transpose_a = matrix_a.T
print("Transpose of Matrix A:\n", transpose_a)
```

---

### **5\. Determinant of a Matrix**

The determinant is a scalar value that can be computed from the elements of a square matrix.

```python
from numpy.linalg import det

# Determinant of a matrix
det_a = det(matrix_a)
print("Determinant of Matrix A:", det_a)
```

---

### **6\. Inverse of a Matrix**

The inverse of a matrix exists only for square matrices with a non-zero determinant.

```python
from numpy.linalg import inv

# Inverse of a matrix
matrix_c = np.array([[4, 7], [2, 6]])
inverse_c = inv(matrix_c)
print("Matrix C:\n", matrix_c)
print("Inverse of Matrix C:\n", inverse_c)
```

---

### **7\. Eigenvalues and Eigenvectors**

Eigenvalues and eigenvectors are fundamental concepts in linear algebra.

```python
from numpy.linalg import eig

# Eigenvalues and eigenvectors
eigenvalues, eigenvectors = eig(matrix_a)
print("Eigenvalues:\n", eigenvalues)
print("Eigenvectors:\n", eigenvectors)
```

---

### **8\. Solving a System of Linear Equations**

You can solve equations of the form AX=BAX = BAX=B where AAA is a matrix, BBB is a vector, and XXX is the unknown.

```python
from numpy.linalg import solve

# Coefficient matrix (A)
A = np.array([[3, 1], [1, 2]])

# Constant matrix (B)
B = np.array([9, 8])

# Solving for X
X = solve(A, B)
print("Solution X:", X)
```

---

### **9\. Other Useful Linear Algebra Functions**

*   **Matrix Rank**: Determines the rank of a matrix.
*   **Trace**: Sum of diagonal elements.

```python
from numpy.linalg import matrix_rank

# Matrix rank
rank_a = matrix_rank(matrix_a)
print("Rank of Matrix A:", rank_a)

# Trace of a matrix
trace_a = np.trace(matrix_a)
print("Trace of Matrix A:", trace_a)
```

---

### **10\. Practical Examples**

#### **Example 1: Linear Regression Using Normal Equation**

Using the equation θ=(XTX)−1XTy\\theta = (X^T X)^{-1} X^T yθ=(XTX)−1XTy:

```python
# Example data
X = np.array([[1, 1], [1, 2], [1, 3]])
y = np.array([1, 2, 3])

# Normal equation
theta = inv(X.T @ X) @ X.T @ y
print("Coefficients (theta):", theta)
```

---

### **Summary**

This notebook covers:

1.  Creating matrices.
2.  Basic matrix operations (addition, subtraction, multiplication).
3.  Linear algebra functions like transpose, determinant, inverse, and eigenvalues.
4.  Solving linear equations.

You can now apply these concepts to solve real-world problems involving matrices, such as in **machine learning**, **image processing**, or **data analysis**.