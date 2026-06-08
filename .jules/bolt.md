## 2025-06-08 - Optimize Pandas Iteration
**Learning:** Pandas `iterrows()` is notoriously slow compared to `itertuples()` for row iteration. Both `publications.py` and `talks.py` as well as their Jupyter notebook counterparts were using `iterrows()`.
**Action:** Replace `iterrows()` with `itertuples()`, which requires minimal syntax change (just `for item in df.itertuples():`) but yields significantly better performance. Always ensure to update BOTH `.py` and `.ipynb` generator files.
