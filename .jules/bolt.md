## 2024-06-02 - Pandas Iteration Performance
**Learning:** Pandas `iterrows()` is extremely slow for iterating over DataFrames compared to `itertuples()`, especially in scripts used to generate static files like `talks.py` and `publications.py`.
**Action:** Replace `iterrows()` with `itertuples()` for significantly better performance when iterating over DataFrames.
