## 2024-06-13 - Replace iterrows() with itertuples() in pandas scripts
**Learning:** `iterrows()` is known to be slow in pandas, while `itertuples()` is much faster for iterating over rows. Several Python scripts (`markdown_generator/publications.py`, `markdown_generator/talks.py`, and their corresponding Jupyter Notebooks) in this repository iterate over DataFrame rows using `iterrows()`.
**Action:** Replace `for row, item in dataframe.iterrows():` with `for item in dataframe.itertuples():` in these scripts to improve performance. Ensure comments are added per Bolt's guidelines.
