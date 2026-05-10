## YYYY-MM-DD - Iterrows to Itertuples Refactor
**Learning:** Using `itertuples()` instead of `iterrows()` on Pandas DataFrames avoids expensive Series instantiation per row, significantly improving iteration performance while preserving named attribute access to row elements.
**Action:** Default to `itertuples()` when iterating over Pandas DataFrames unless row modification (which `iterrows` also advises against) or explicit Series properties are strictly required.
