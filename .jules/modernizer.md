## 2024-05-24 - Pandas row iteration optimization
**Learning:** `iterrows()` is significantly slower than `itertuples()` for iterating through Pandas DataFrames because it creates a Series for each row.
**Action:** Replace `for row, item in df.iterrows():` with `for item in df.itertuples():` where possible to improve performance, while maintaining identical property access syntax (`item.column_name`).
