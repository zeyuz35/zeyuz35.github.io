## 2024-06-12 - Synchronizing Generator Scripts and Notebooks
**Learning:** Generator scripts (`.py`) in this codebase often have a corresponding interactive Jupyter notebook (`.ipynb`). Modifications to imports or code in the script must be mirrored in the notebook to maintain consistency.
**Action:** Before removing unused imports or dependencies in python scripts, use `grep` to check if a corresponding `.ipynb` exists. Programmatically modify the JSON structure to apply the same cleanup to keep them synchronized.
