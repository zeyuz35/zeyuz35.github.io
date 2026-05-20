## 2025-05-20 - Remove Unused Imports in pubsFromBib.py
**Learning:** `markdown_generator/pubsFromBib.py` contained redundant and unused imports (`import pybtex.database.input.bibtex` when `from pybtex.database.input import bibtex` was already used, and `import string`).
**Action:** Audit and remove unused imports in scripts and their accompanying Jupyter notebooks to maintain package hygiene.
