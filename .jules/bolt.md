## 2024-05-23 - Pandas DataFrame iteration optimization
**Learning:** In pandas-based scripts, replacing `iterrows()` with `itertuples()` for DataFrame iteration yields significant performance improvement (~97%). However, it requires updating attribute access to namedtuple dot notation (e.g., `item.date`) instead of dictionary-style or Series index access.
**Action:** Always prefer `itertuples()` over `iterrows()` when iterating through large pandas DataFrames, unless index-based modification is strictly required. Ensure attribute access logic is updated accordingly.
