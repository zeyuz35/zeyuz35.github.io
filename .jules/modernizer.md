## 2025-05-25 - Refactor iterrows to itertuples
**Learning:** Pandas `iterrows()` yields a Series for every row, incurring heavy overhead. Switching to `itertuples()` yields NamedTuples, massively improving iteration performance.
**Action:** Always prefer `itertuples()` over `iterrows()` when iterating over a DataFrame where columns are accessed via dot-notation.
