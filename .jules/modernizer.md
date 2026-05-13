## 2026-05-13 - Replace iterrows() with itertuples()
**Learning:** `iterrows()` is slow because it iterates over the rows as (index, Series) pairs, while `itertuples()` is much faster as it returns namedtuples where original column names are accessible directly as attributes.
**Action:** Always prefer `itertuples()` over `iterrows()` in pandas DataFrame iterations for better performance and maintainability.
