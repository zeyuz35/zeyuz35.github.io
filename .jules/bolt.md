## 2024-05-16 - Replace iterrows with itertuples
**Learning:** Using `itertuples()` is significantly faster than `iterrows()` for iterating through pandas DataFrames in Python, and returns namedtuples where original column names are accessible directly as attributes.
**Action:** Default to `itertuples()` over `iterrows()` when row iteration is necessary in pandas to improve script execution times.