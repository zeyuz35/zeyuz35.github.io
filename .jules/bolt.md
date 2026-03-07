
## 2024-05-19 - Pandas Iteration Optimization
**Learning:** Using `iterrows()` on Pandas DataFrames is significantly slower than using `itertuples()` due to the overhead of creating Series objects for each row.
**Action:** Replace `iterrows()` with `itertuples()` for iterating over DataFrames when only reading values, which provides a fast and readable O(n) iteration in Python.
