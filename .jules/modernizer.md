## 2025-03-01 - Replace iterrows() with itertuples()
**Learning:** pandas `iterrows()` is slow compared to `itertuples()`, which returns namedtuples and provides much better performance for iteration.
**Action:** Always prefer `itertuples()` over `iterrows()` when iterating through pandas DataFrames if row modification is not needed.
