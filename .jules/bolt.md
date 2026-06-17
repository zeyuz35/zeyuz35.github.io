## 2024-05-24 - Pandas Performance Optimization
**Learning:** In Pandas, iterating over DataFrame rows with `iterrows()` is extremely slow compared to `itertuples()` because `iterrows()` yields a Series for each row, incurring massive overhead, while `itertuples()` yields namedtuples, which is significantly faster and often a drop-in replacement if the row index is unused.
**Action:** Replace `iterrows()` with `itertuples()` whenever row iteration is required and the index is not needed. Ensure corresponding `.ipynb` notebooks are updated to match the Python script changes.
