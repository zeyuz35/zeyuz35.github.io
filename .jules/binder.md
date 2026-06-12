## 2025-02-26 - Remove Unused Imports in markdown_generator
**Learning:** The bibliography generator `pubsFromBib.py` imported `string` and a redundant `pybtex.database.input.bibtex` without using them.
**Action:** Use `pyflakes` to identify unused imports and remove them from both the python script and the corresponding `.ipynb` notebook programmatically.
