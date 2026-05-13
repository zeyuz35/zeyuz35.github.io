## 2025-03-05 - Optimize Pandas Row Iteration
**Learning:** Using `iterrows()` in pandas DataFrames is computationally expensive because it creates a Series for each row.
**Action:** Replace `iterrows()` with `itertuples()` for significantly faster row iteration when simple attribute access is sufficient.