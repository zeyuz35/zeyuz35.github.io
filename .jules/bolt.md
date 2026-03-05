## 2024-03-05 - Optimize DataFrame iteration with itertuples
**Learning:** When iterating over Pandas DataFrames to generate markdown files, using `iterrows()` constructs a new Series object for each row, leading to a performance bottleneck. Using `itertuples()` returns a namedtuple and is significantly faster, especially since TSV column names are already valid Python identifiers.
**Action:** Always use `itertuples()` instead of `iterrows()` when iterating over Pandas DataFrames, especially when the iteration logic relies on attribute access.
