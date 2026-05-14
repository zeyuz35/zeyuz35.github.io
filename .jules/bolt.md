## 2024-05-14 - Replace pandas iterrows() with itertuples()
**Learning:** `iterrows()` in pandas is slow because it yields Series objects. `itertuples()` yields namedtuples and is much faster for iterating over DataFrames, preserving row values as attributes.
**Action:** Use `itertuples()` instead of `iterrows()` for iteration in pandas scripts to improve performance.
