# Data-Analysis
### Notes on NumPy

**NumPy** is a fundamental library for scientific computing in Python. It provides support for arrays and matrices and offers a collection of mathematical functions to operate on these data structures.

### 1. Installing and Importing NumPy

To install NumPy, use the following command:

```python
!pip install numpy
```

To import NumPy into your Python script or Jupyter notebook, use:

```python
import numpy as np
```

### 2. Creating Arrays

**1D Array:**
You can create a one-dimensional array (1D array) using the `np.array()` function:

```python
arr1 = np.array([1, 2, 3, 4, 5])
print(arr1)  # Output: [1 2 3 4 5]
print(type(arr1))  # Output: <class 'numpy.ndarray'>
print(arr1.shape)  # Output: (5,)
```

**Reshaping an Array:**
Reshape a 1D array to a different shape:

```python
arr2 = np.array([1, 2, 3, 4, 5])
arr2_reshaped = arr2.reshape(1, 5)
print(arr2_reshaped)  # Output: [[1 2 3 4 5]]
```

**2D Array:**
Create a two-dimensional array:

```python
arr2 = np.array([[1, 2, 3, 4, 5], [2, 3, 4, 5, 6]])
print(arr2)
print(arr2.shape)  # Output: (2, 5)
```

### 3. Special Arrays

- **Range of Numbers:** Use `np.arange()` to create a range of numbers:

  ```python
  print(np.arange(0, 10, 2).reshape(5, 1))
  # Output:
  # [[0]
  #  [2]
  #  [4]
  #  [6]
  #  [8]]
  ```

- **Array of Ones:** Create an array filled with ones:

  ```python
  print(np.ones((3, 4)))
  # Output:
  # [[1. 1. 1. 1.]
  #  [1. 1. 1. 1.]
  #  [1. 1. 1. 1.]]
  ```

- **Identity Matrix:** Create an identity matrix:

  ```python
  print(np.eye(3))
  # Output:
  # [[1. 0. 0.]
  #  [0. 1. 0.]
  #  [0. 0. 1.]]
  ```

### 4. Attributes of NumPy Arrays

Attributes like shape, dimensions, size, and data type of the arrays can be accessed using:

```python
arr = np.array([[1, 2, 3], [4, 5, 6]])
print("Shape:", arr.shape)  # (2, 3)
print("Number of dimensions:", arr.ndim)  # 2
print("Size (number of elements):", arr.size)  # 6
print("Data type:", arr.dtype)  # int32
print("Item size (in bytes):", arr.itemsize)  # Platform dependent
```

### 5. Vectorized Operations

NumPy allows performing element-wise operations on arrays:

```python
arr1 = np.array([1, 2, 3, 4, 5])
arr2 = np.array([10, 20, 30, 40, 50])

print("Addition:", arr1 + arr2)  # [11 22 33 44 55]
print("Subtraction:", arr1 - arr2)  # [-9 -18 -27 -36 -45]
print("Multiplication:", arr1 * arr2)  # [10 40 90 160 250]
print("Division:", arr1 / arr2)  # [0.1 0.1 0.1 0.1 0.1]
```

### 6. Universal Functions (ufuncs)

NumPy provides a wide range of universal functions that operate element-wise on arrays:

```python
arr = np.array([2, 3, 4, 5, 6])

print(np.sqrt(arr))  # Square root
print(np.exp(arr))   # Exponential
print(np.sin(arr))   # Sine
print(np.log(arr))   # Natural log
```

### 7. Array Slicing and Indexing

Slicing is used to access subarrays:

```python
arr = np.array([[1, 2, 3, 4], [5, 6, 7, 8], [9, 10, 11, 12]])
print(arr[1:, 1:3])  # Output: [[6 7], [10 11]]
print(arr[0][0])     # Output: 1
print(arr[0:2, 2:])  # Output: [[3 4], [7 8]]
```

### 8. Modifying Array Elements

Elements of an array can be modified using indexing:

```python
arr[0, 0] = 100
print(arr)  # First element set to 100

arr[1:] = 100
print(arr)  # All elements of rows 2 and 3 set to 100
```

### 9. Statistical Functions

- **Normalization**: Adjust data to have a mean of 0 and standard deviation of 1.

  ```python
  data = np.array([1, 2, 3, 4, 5])
  mean = np.mean(data)
  std_dev = np.std(data)
  normalized_data = (data - mean) / std_dev
  print("Normalized data:", normalized_data)
  ```

- **Mean, Median, Standard Deviation, Variance**:

  ```python
  data = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10])
  print("Mean:", np.mean(data))  # Output: 5.5
  print("Median:", np.median(data))  # Output: 5.5
  print("Standard Deviation:", np.std(data))  # Output: 2.87
  print("Variance:", np.var(data))  # Output: 8.25
  ```

### 10. Logical Operations

Logical operations can be used to filter arrays based on conditions:

```python
data = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10])
filtered_data = data[(data >= 5) & (data <= 8)]
print(filtered_data)  # Output: [5 6 7 8]
```

These examples provide a solid foundation for working with NumPy, a crucial library for data analysis in Python. Understanding these concepts will help you perform efficient data manipulation and mathematical computations.

No, NumPy arrays in Python are not exactly the same as arrays in Java or C++. While they share some similarities in how they store data and allow indexing, there are key differences in how they are implemented, their capabilities, and how they are used. Here’s a breakdown of the similarities and differences:

### ARRAY IN JAVA VS NUMPY

### 1. **Memory Management**
   - **NumPy (Python)**: NumPy arrays are implemented in C, which means they are highly optimized for numerical computations. They are stored in a contiguous block of memory, making them faster and more efficient for mathematical operations compared to regular Python lists.
   - **Java and C++**: Arrays in Java and C++ are also stored in contiguous blocks of memory, which allows for efficient memory access and manipulation. However, these arrays are often of a fixed size once created, and resizing them requires creating a new array and copying elements over.

### 2. **Dynamic vs. Static Typing**
   - **NumPy (Python)**: NumPy arrays are homogenous, meaning all elements in an array must be of the same type (e.g., all integers or all floats). You can specify the data type (dtype) when you create a NumPy array. This homogeneity makes NumPy arrays more efficient for mathematical operations.
   - **Java**: Java arrays are strongly typed and also homogenous. The type of the array (e.g., `int[]`, `double[]`) is specified at creation, and all elements must match that type.
   - **C++**: In C++, arrays are also homogenous and typed (e.g., `int[]`, `double[]`). They use static typing like Java.

### 3. **Array Slicing and Indexing**
   - **NumPy (Python)**: NumPy supports advanced slicing and indexing, allowing for selecting subarrays, modifying parts of the array, and even conditional filtering (e.g., selecting elements based on a condition). You can use negative indices to access elements from the end of the array, and NumPy supports multi-dimensional arrays (e.g., 2D, 3D arrays).
   - **Java**: Java supports simple indexing with fixed-size arrays but does not natively support slicing in the same way NumPy does. You would need to manually loop through and copy elements to achieve similar functionality.
   - **C++**: Similar to Java, C++ supports basic indexing but does not have native slicing capabilities like NumPy. You can achieve similar results with loops or the use of vector objects from the Standard Template Library (STL).

### 4. **Vectorized Operations**
   - **NumPy (Python)**: One of the key strengths of NumPy is its ability to perform vectorized operations. This means you can perform element-wise operations on entire arrays without writing explicit loops. For example, adding two arrays or multiplying an array by a scalar is done with simple syntax (`arr1 + arr2`), and it operates much faster due to NumPy's underlying C implementation.
   - **Java**: Arrays in Java do not support vectorized operations out of the box. You would typically use loops to perform element-wise operations.
   - **C++**: Similarly, C++ arrays require explicit loops for element-wise operations unless you use specialized libraries (like the Eigen library) that provide vectorized operations.

### 5. **Built-in Functions and Methods**
   - **NumPy (Python)**: NumPy comes with a wide range of built-in functions for mathematical operations, statistical analysis, linear algebra, random number generation, etc., which are optimized for performance.
   - **Java**: Java’s standard library provides some mathematical functions, but it's not as extensive as NumPy for scientific computing. For more complex operations, you often need to rely on third-party libraries.
   - **C++**: C++ provides a standard library for mathematical functions, but more advanced operations require additional libraries like Eigen for linear algebra, or boost for more complex operations.

### 6. **Memory Safety**
   - **NumPy (Python)**: Python, and by extension NumPy, handles memory management automatically, reducing the likelihood of memory leaks or buffer overflows.
   - **Java**: Java also provides automatic memory management through garbage collection, which helps manage memory safety.
   - **C++**: In C++, the programmer has manual control over memory management, which provides flexibility but also introduces risks of memory leaks and buffer overflows if not handled carefully.

### Summary

- **NumPy arrays** are more flexible and powerful for scientific computing, offering advanced functionalities like slicing, vectorized operations, and a wide range of mathematical functions.
- **Java and C++ arrays** are simpler, strongly typed, and efficient for basic data storage and manipulation, but they require additional effort to perform complex numerical computations and often need third-party libraries for advanced features.

NumPy is often preferred in data analysis and scientific computing environments because of its extensive capabilities, performance optimizations, and ease of use.

Let's go through these two statements one by one, using an example array to understand what each line does.

Suppose we have the following 2D NumPy array:

```python
import numpy as np

arr = np.array([
    [1, 2, 3, 4],
    [5, 6, 7, 8],
    [9, 10, 11, 12]
])
```

### 1. `print(arr[0][0])`

- **What it does**: This line accesses and prints the element in the first row and first column of the array.
- **Explanation**: 
  - `arr[0]` selects the first row of the array (`[1, 2, 3, 4]`).
  - `arr[0][0]` then selects the first element of that row, which is `1`.

- **Example Output**:

  ```python
  print(arr[0][0])
  ```

  **Output**:
  ```
  1
  ```

### 2. `print(arr[0:2, 2:])`

- **What it does**: This line slices the array to select a subarray and prints it. Specifically, it selects:
  - Rows from index `0` to `1` (up to, but not including, index `2`).
  - Columns from index `2` to the end.

- **Explanation**:
  - `arr[0:2]`: This selects the first two rows (`0` and `1`). So, it includes:
    - Row 0: `[1, 2, 3, 4]`
    - Row 1: `[5, 6, 7, 8]`
  - `arr[:, 2:]`: This selects columns starting from index `2` to the end.
    - Columns `2` and `3` are selected:
      - For Row 0: Elements `[3, 4]`
      - For Row 1: Elements `[7, 8]`

- **Example Output**:

  ```python
  print(arr[0:2, 2:])
  ```

  **Output**:
  ```
  [[3 4]
   [7 8]]
  ```

### Summary of Each Statement:

1. `print(arr[0][0])`: Prints the first element (top-left corner) of the 2D array, which is `1` in this example.
2. `print(arr[0:2, 2:])`: Slices the array to get the first two rows and the last two columns, resulting in a subarray:
   ```
   [[3 4]
    [7 8]]
   ```

These slicing techniques are extremely useful when working with multi-dimensional arrays, as they allow you to extract specific parts of the array for further analysis or manipulation.
Absolutely! Let's go through the concepts of **standard deviation** and **normalization** in simple terms.

### 1. **Standard Deviation**

**What is Standard Deviation?**

- **Standard deviation** is a measure of how spread out the numbers in a dataset are. It tells us how much the values in the dataset deviate from the mean (average) of the data.
- In simple terms, it shows how much the numbers in the dataset are different from the average value.

**Example:**

Let's consider a small set of numbers to understand standard deviation:

Suppose we have the numbers: `[2, 4, 4, 4, 5, 5, 7, 9]`

1. **Find the Mean (Average)**:  
   - Mean = (2 + 4 + 4 + 4 + 5 + 5 + 7 + 9) / 8  
   - Mean = 40 / 8 = 5

2. **Calculate Each Number's Distance from the Mean and Square It**:
   - (2 - 5)² = 9  
   - (4 - 5)² = 1  
   - (4 - 5)² = 1  
   - (4 - 5)² = 1  
   - (5 - 5)² = 0  
   - (5 - 5)² = 0  
   - (7 - 5)² = 4  
   - (9 - 5)² = 16

3. **Find the Mean of These Squared Differences**:
   - Sum of squared differences = 9 + 1 + 1 + 1 + 0 + 0 + 4 + 16 = 32  
   - Mean of squared differences = 32 / 8 = 4

4. **Take the Square Root of This Mean**:
   - Standard deviation = √4 = 2

**Interpretation**:  
- The standard deviation of this dataset is 2. This means, on average, the numbers are 2 units away from the mean (5). If the standard deviation is small, the numbers are close to the mean. If it is large, the numbers are spread out more.

### 2. **Normalization**

**What is Normalization?**

- **Normalization** is the process of scaling data so that it has a mean (average) of 0 and a standard deviation of 1. This process is commonly used in data analysis and machine learning to bring different datasets to a common scale without distorting differences in the ranges of values.
- It makes it easier to compare data that may be on different scales.

**How to Normalize Data:**

1. **Calculate the Mean and Standard Deviation of the Data**.
2. **Subtract the Mean from Each Data Point**: This shifts the data so that the mean is now 0.
3. **Divide Each Data Point by the Standard Deviation**: This scales the data so that the standard deviation is now 1.

**Example**:

Suppose we have a dataset: `[2, 4, 4, 4, 5, 5, 7, 9]`

1. **Find the Mean**:  
   - Mean = 5 (as calculated earlier).

2. **Find the Standard Deviation**:  
   - Standard deviation = 2 (as calculated earlier).

3. **Normalize Each Data Point**:  
   - Normalized value = (Original value - Mean) / Standard deviation

   Let's normalize the first three values:
   - For `2`: (2 - 5) / 2 = -1.5  
   - For `4`: (4 - 5) / 2 = -0.5  
   - For another `4`: (4 - 5) / 2 = -0.5  

   Normalized dataset: `[-1.5, -0.5, -0.5, -0.5, 0, 0, 1, 2]`

**Interpretation**:  
- Now, the data has a mean of 0 and a standard deviation of 1.
- A value of -1.5 means it is 1.5 standard deviations below the mean. A value of 2 means it is 2 standard deviations above the mean.

### Summary

- **Standard Deviation** measures the spread of data around the mean. A higher standard deviation means data is more spread out.
- **Normalization** transforms data to have a mean of 0 and a standard deviation of 1, making it easier to compare data and use in machine learning models.


### **1. Introduction to Pandas Data Structures: DataFrame and Series**

**Explanation:**  
Pandas is a Python library used for data manipulation and analysis. It provides two main data structures:
- **Series**: A one-dimensional array-like structure capable of holding any data type (integer, string, float, etc.). Think of it as a single column from a spreadsheet or SQL table.
- **DataFrame**: A two-dimensional, size-mutable, and potentially heterogeneous data structure with labeled axes (rows and columns). It's similar to a table in a database or a data frame in R.

### **2. Importing Pandas Library**

```python
import pandas as pd
```

**Explanation:**  
Here, we import the pandas library and give it the alias `pd`. This is a common practice to make the code more concise when using pandas functions.

### **3. Creating a Pandas Series**

```python
data = [1, 2, 3, 4, 5]
series = pd.Series(data)
print("Series \n", series)
print(type(series))
```

**Explanation:**  
- A list `data` containing numbers 1 through 5 is created.
- `pd.Series(data)` creates a Pandas Series from the list. Each element of the list becomes an element of the Series, with an automatically generated index starting from 0.
- `print(type(series))` confirms that the variable `series` is indeed a Pandas Series.

**Output:**
```
Series
 0    1
1    2
2    3
3    4
4    5
dtype: int64
<class 'pandas.core.series.Series'>
```
Yes, the distinction between `int64` and `int32` in a Pandas Series can depend on the system architecture and the specific context of how the data is handled within Pandas. Here's a deeper explanation:

### 1. **System Architecture: 32-bit vs. 64-bit Systems**
   - **64-bit Systems**: If you are running Python on a 64-bit system, Pandas typically defaults to `int64` for integer types. This is because a 64-bit system can handle larger integers more efficiently, providing more precision and range.
   - **32-bit Systems**: On a 32-bit system, Pandas might use `int32` as the default for integer types. This is due to the system's constraints, as handling 64-bit integers might be less efficient or supported.

### 2. **Data Type Specification in Pandas**
   - When you create a Series, Pandas infers the data type based on the data provided. If you explicitly specify the dtype, Pandas will follow your instruction.
   - Example: Specifying `dtype=int32`:
     ```python
     import pandas as pd

     data = [1, 2, 3, 4, 5]
     series = pd.Series(data, dtype='int32')
     print(series)
     print(series.dtype)  # Output will be int32
     ```
   - Here, you explicitly tell Pandas to use `int32` as the data type.

### 3. **Default Behavior on 64-bit Systems**
   - On a 64-bit system, even if the numbers fit into `int32`, Pandas often uses `int64` to maximize precision and take advantage of the system’s capabilities.
   - The choice of `int64` by default ensures more significant integer range, which is particularly beneficial when dealing with large datasets or big numbers.

### 4. **Data Input and Compatibility**
   - When reading data from external sources (like CSV files or databases), the data type might be determined by the source. If the data source specifies `int32` and it fits into the system memory model, Pandas will use `int32`.
   - For example, reading a CSV file with an explicit data type specified:
     ```python
     df = pd.read_csv('data.csv', dtype={'column_name': 'int32'})
     ```

### 5. **Memory Efficiency**
   - Using `int32` instead of `int64` reduces memory usage. If you're dealing with a large dataset where the integer range is well within `int32`, you might opt for `int32` to save memory.
   - This choice is particularly important when scaling data operations on limited memory resources.

### Summary

- **System Architecture**: On a 64-bit system, Pandas defaults to `int64`. On a 32-bit system, it may use `int32`.
- **Explicit Specification**: You can specify the data type (`int32` or `int64`) when creating a Series or DataFrame.
- **Default Behavior**: On 64-bit systems, Pandas defaults to `int64` for broader range and precision unless explicitly set otherwise.
- **Memory Efficiency**: Choose `int32` for memory efficiency when large ranges aren't necessary.

These details can be crucial when optimizing performance or ensuring compatibility across different platforms and data processing environments. If you need more information on how to handle specific scenarios, feel free to ask!

### **4. Creating a Series from a Dictionary**

```python
data = {'a': 1, 'b': 2, 'c': 3}
series_dict = pd.Series(data)
print(series_dict)
```

**Explanation:**  
- A dictionary `data` is created with keys as labels ('a', 'b', 'c') and values (1, 2, 3).
- `pd.Series(data)` creates a Pandas Series where the keys of the dictionary become the index of the Series, and the values become the Series' values.

**Output:**
```
a    1
b    2
c    3
dtype: int64
```

### **5. Creating a Custom Indexed Series**

```python
data = [10, 20, 30]
index = ['a', 'b', 'c']
pd.Series(data, index=index)
```

**Explanation:**  
- Here, a list `data` and a list `index` are defined.
- `pd.Series(data, index=index)` creates a Series with the specified `index` for each element, which provides more meaningful labels instead of the default numeric index.

**Output:**
```
a    10
b    20
c    30
dtype: int64
```

### **6. Creating a DataFrame from a Dictionary of Lists**

```python
data = {
    'Name': ['Krish', 'John', 'Jack'],
    'Age': [25, 30, 45],
    'City': ['Bangalore', 'New York', 'Florida']
}
df = pd.DataFrame(data)
print(df)
print(type(df))
```

**Explanation:**  
- A dictionary `data` is created where each key corresponds to a column name, and its value is a list representing the column's data.
- `pd.DataFrame(data)` creates a DataFrame from this dictionary.
- `print(type(df))` confirms that `df` is indeed a Pandas DataFrame.

**Output:**
```
    Name  Age       City
0  Krish   25  Bangalore
1   John   30   New York
2   Jack   45    Florida
<class 'pandas.core.frame.DataFrame'>
```
A **DataFrame** is like a table or a spreadsheet in Python. It's a way to organize and work with data in rows and columns. 

### Key Points:

1. **Rows and Columns**: Think of a DataFrame as a table with rows and columns, similar to an Excel sheet. Each column can have a different type of data (like numbers, text, dates).

2. **Labeled**: Each row and column has labels (names), making it easy to access specific parts of the data. The columns have names (like "Name," "Age," "City"), and rows are usually labeled with numbers (0, 1, 2, etc.).

3. **Versatile**: A DataFrame can hold different types of data in each column, such as integers, floats, strings, or even more complex types like dates.

### Example:

Imagine a DataFrame that looks like this:

| Name  | Age | City      |
|-------|-----|-----------|
| Alice | 25  | New York  |
| Bob   | 30  | London    |
| Charlie | 22 | Paris     |

- **Columns**: "Name," "Age," "City" are the columns.
- **Rows**: Each person's information is a row (Alice's details are in one row, Bob's in another).

### How It Helps:

- **Easy Data Handling**: DataFrames make it simple to read, write, filter, and analyze data.
- **Quick Analysis**: You can perform operations like finding the average age or counting how many people live in each city.
- **Data Organization**: They help keep data organized and structured, which is crucial for analysis, reporting, and visualization.

In summary, a DataFrame is a powerful tool in Python for organizing, viewing, and analyzing data in a structured way, just like a table in a spreadsheet!
### **7. Creating a DataFrame from a List of Dictionaries**

```python
data = [
    {'Name': 'Krish', 'Age': 32, 'City': 'Bangalore'},
    {'Name': 'John', 'Age': 34, 'City': 'Bangalore'},
    {'Name': 'Bappy', 'Age': 32, 'City': 'Bangalore'},
    {'Name': 'Jack', 'Age': 32, 'City': 'Bangalore'}
]
df = pd.DataFrame(data)
print(df)
print(type(df))
```

**Explanation:**  
- Here, a list `data` is defined where each item is a dictionary representing a row in the DataFrame.
- `pd.DataFrame(data)` creates a DataFrame with each dictionary in the list forming a row, and the keys of the dictionary forming the column names.

**Output:**
```
    Name  Age       City
0  Krish   32  Bangalore
1   John   34  Bangalore
2  Bappy   32  Bangalore
3   Jack   32  Bangalore
<class 'pandas.core.frame.DataFrame'>
```

### **8. Reading Data from a CSV File into a DataFrame**

```python
df = pd.read_csv('sales_data.csv')
df.head(5)
df.tail(5)
```

**Explanation:**  
- `pd.read_csv('sales_data.csv')` reads a CSV file named `sales_data.csv` into a DataFrame.
- `df.head(5)` displays the first five rows of the DataFrame, which helps in quickly understanding the structure and data contained within it.
- `df.tail(5)` displays the last five rows of the DataFrame.

### **9. Accessing Data from a DataFrame**

```python
df['Name']
df.loc[0]
df.iloc[0]
```

**Explanation:**  
- `df['Name']` accesses the 'Name' column of the DataFrame, returning a Series containing all the names.
- `df.loc[0]` accesses the first row of the DataFrame using the label-based index.
- `df.iloc[0]` accesses the first row of the DataFrame using the integer-based position index.

### **10. Accessing Specific Elements in a DataFrame**

```python
df.at[2, 'Age']
df.at[2, 'Name']
```

**Explanation:**  
- `df.at[2, 'Age']` accesses the element in the 3rd row (index 2) and the 'Age' column.
- `df.at[2, 'Name']` accesses the element in the 3rd row (index 2) and the 'Name' column.

```python
df.iat[2, 2]
```

**Explanation:**  
- `df.iat[2, 2]` accesses the element at the 3rd row and 3rd column (both indices are zero-based).

### **11. Data Manipulation with DataFrame**

**Adding a Column:**

```python
df['Salary'] = [50000, 60000, 70000]
```

**Explanation:**  
- A new column 'Salary' is added to the DataFrame with the specified values `[50000, 60000, 70000]`.

**Removing a Column:**

```python
df.drop('Salary', axis=1, inplace=True)
```

**Explanation:**  
- `df.drop('Salary', axis=1)` drops the 'Salary' column from the DataFrame. `axis=1` indicates columns (use `axis=0` for rows).
- `inplace=True` means the changes are made directly in the original DataFrame.

**Modifying Data:**

```python
df['Age'] = df['Age'] + 1
```

**Explanation:**  
- This increases the value in the 'Age' column by 1 for every row, demonstrating how to update data within a DataFrame.

**Dropping Rows:**

```python
df.drop(0, inplace=True)
```

**Explanation:**  
- This drops the row with index 0 from the DataFrame, permanently modifying the original DataFrame.

### **12. Descriptive Statistics and Data Types**

```python
df = pd.read_csv('sales_data.csv')
print("Data types:\n", df.dtypes)
print("Statistical summary:\n", df.describe())
```

**Explanation:**  
- The DataFrame `df` is loaded again from `sales_data.csv`.
- `df.dtypes` displays the data type of each column in the DataFrame, helping understand what type of data is being handled.
- `df.describe()` provides a statistical summary of the DataFrame, including count, mean, standard deviation, min, and max values for each numerical column.


