## 2024-05-10 - Replace DataFrame.iterrows() with DataFrame.itertuples()
**Learning:** Using `iterrows()` in pandas is famously slow because it returns each row as a Series object, adding overhead. For scripts that process multiple files based on pandas DataFrame entries (e.g. `markdown_generator` scripts), using `itertuples()` is significantly faster and drop-in compatible if the fields are valid python identifiers.
**Action:** When working with pandas DataFrames iteration for read-only access where performance is a concern, replace `iterrows()` with `itertuples()` where possible.
