## 2024-05-24 - Unused Imports in pubsFromBib scripts
**Learning:** The `pubsFromBib.py` script and its Jupyter notebook counterpart contain unused imports: `pybtex.database.input.bibtex` and `string`. Removing them reduces dependency bloat.
**Action:** Always check for unused imports using `flake8` when performing package hygiene audits.
