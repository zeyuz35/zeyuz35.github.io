## 2025-02-14 - Optimize DataFrame iteration with itertuples()
**Learning:** In pandas, iterating over rows using `df.iterrows()` creates a new pandas Series for every single row, which is exceptionally slow.
**Action:** Replace `iterrows()` with `itertuples()` for a significant performance gain (often 50x-100x), especially in scripts that parse TSVs. Ensure downstream column references (e.g. `item.pub_date`) match the syntax of `namedtuple` attributes.
