## 2025-01-20 - Use itertuples over iterrows
**Learning:** `iterrows()` in pandas is slow because it creates a Series for each row. `itertuples()` is significantly faster as it returns a namedtuple.
**Action:** Always prefer `itertuples()` over `iterrows()` when iterating through a pandas DataFrame where column values are accessed as attributes.
