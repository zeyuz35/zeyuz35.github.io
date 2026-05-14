## 2024-05-24 - Pandas iterrows to itertuples
**Learning:** `iterrows()` is often a performance bottleneck in loops. `itertuples()` is a much faster alternative that returns namedtuples where original column names are accessible directly as attributes.
**Action:** Prefer `itertuples()` over `iterrows()` when iterating through rows in a pandas DataFrame for better performance.
