## 2025-02-27 - Replace iterrows() with itertuples()
**Learning:** In Pandas, `iterrows()` is generally slower because it boxes each row into a Series. `itertuples()` is much faster as it returns a namedtuple for each row, avoiding this overhead while maintaining readability.
**Action:** Always prefer `itertuples()` over `iterrows()` when iterating through Pandas DataFrames in Python scripts and Jupyter notebooks if named attribute access is sufficient.
