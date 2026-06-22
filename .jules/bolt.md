## 2025-02-20 - Use itertuples over iterrows
**Learning:** pandas `iterrows()` is slow because it creates a Series for each row. `itertuples()` is much faster as it returns namedtuples and doesn't do type checking on each row.
**Action:** Always prefer `itertuples()` when iterating over a pandas DataFrame if you don't need the index and the column names are valid Python identifiers.
