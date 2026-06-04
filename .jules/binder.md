## 2024-06-04 - Unused `string` module import in generator
**Learning:** The `markdown_generator/pubsFromBib.py` and its corresponding Jupyter notebook `PubsFromBib.ipynb` imported the standard `string` module, but did not use it.
**Action:** When removing unused imports in Python generator scripts, always verify if a counterpart `.ipynb` exists and modify its JSON structure programmatically to keep both environments synchronized.
