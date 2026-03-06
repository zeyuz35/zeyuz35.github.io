## 2024-05-24 - Pandas iterrows bottleneck
**Learning:** Iterating over Pandas DataFrames in `markdown_generator` scripts using `iterrows()` is a performance bottleneck. `itertuples()` is significantly faster because it doesn't incur the overhead of boxing rows into Pandas Series objects, preserving the types and offering much better speed. The TSV column names are already maintained as valid Python identifiers to support attribute access during iteration.
**Action:** Use `itertuples()` over `iterrows()` for iterating Pandas DataFrames in this project to optimize performance.
