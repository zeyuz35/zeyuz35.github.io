## 2024-05-17 - Iterators optimization
**Learning:** pandas `iterrows()` is slow and an antipattern for iteration. It yields Series objects, which carry significant overhead. `itertuples()` yields namedtuples and is significantly faster, or simply using vectorized operations where applicable. For file generation scripts, `itertuples()` is a direct, much faster replacement.
**Action:** Replace `iterrows()` with `itertuples()` in `markdown_generator` scripts.
