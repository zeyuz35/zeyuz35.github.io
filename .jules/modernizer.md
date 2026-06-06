## 2024-06-06 - Replacing iterrows() with itertuples() in pandas
**Learning:** `iterrows()` is notoriously slow in pandas because it creates a Series object for every row. `itertuples()` returns namedtuples and is significantly faster while maintaining readability.
**Action:** Replace `iterrows()` with `itertuples()` when iterating through pandas DataFrames, documenting the performance rationale.
