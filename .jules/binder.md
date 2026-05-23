## 2024-05-23 - Remove unused imports in Jupyter Notebook and python file
**Learning:** Found unused `string` and redundant `pybtex.database.input.bibtex` imports in `markdown_generator/pubsFromBib.py` and `markdown_generator/PubsFromBib.ipynb`. Notebook edits via JSON serialization work smoothly for simple removals without corrupting JSON logic.
**Action:** Always parse unused imports cautiously inside `.ipynb` by loading as JSON and selectively filtering lines from cell sources.
