## YYYY-MM-DD - Replaced pandas iterrows() with itertuples()
**Learning:** In pandas-based scripts, using `iterrows()` is slow because it creates a Series for each row. Using `itertuples()` is much faster since it returns namedtuples and avoids the overhead of converting rows to Series objects. This is a common pattern in the data generation scripts here.
**Action:** Always prefer `itertuples()` over `iterrows()` in data generation scripts. Existing Series dot notation (e.g., `item.date`) is perfectly compatible without changes.
