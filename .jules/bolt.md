## 2024-05-19 - Pandas Iteration Performance
**Learning:** `iterrows()` is known to be significantly slower in pandas than `itertuples()` for iterating over DataFrames because it yields Series objects and involves more type checking overhead. `itertuples()` yields namedtuples which is much faster.
**Action:** Replace `iterrows()` with `itertuples()` in `markdown_generator/publications.py` and `markdown_generator/talks.py` and their corresponding notebooks.
