## 2024-05-23 - Modifying Jupyter Notebook files
**Learning:** Jupyter notebooks (`.ipynb`) must be modified programmatically by parsing JSON rather than using `replace_with_git_merge_diff` to ensure correct and valid file formatting.
**Action:** When updating Jupyter Notebook contents, I will create a python script using `json.load()` and `json.dump()` instead of using raw string diff tools.
