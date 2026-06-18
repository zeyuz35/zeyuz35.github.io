## 2025-02-23 - Replaced pandas iterrows with itertuples in markdown generators
**Learning:** Replaced `iterrows()` with `itertuples()` to improve performance as `itertuples()` yields a namedtuple and avoids the overhead of constructing a Series object for each row. The existing attribute access syntax remained compatible.
**Action:** When iterating over pandas DataFrames where row index is unused and attributes are accessed via dot notation, always prefer `itertuples()` for performance and cleaner code.
