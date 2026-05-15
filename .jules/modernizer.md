## 2024-05-18 - Replacing iterrows with itertuples in pandas iterators
**Learning:** Found loops using `iterrows()` across `markdown_generator/` python files and Jupyter notebooks, which is notoriously slow for pandas iterating. Using `itertuples()` instead keeps readability but improves performance significantly since it accesses elements directly as namedtuples rather than creating series objects for each row.
**Action:** Replace `iterrows()` with `itertuples()` to make iterator blocks more performant without changing output formatting.
