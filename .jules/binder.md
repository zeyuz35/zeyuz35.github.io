## 2024-05-24 - Unused `string` module import in `markdown_generator/pubsFromBib.py`
**Learning:** `markdown_generator/pubsFromBib.py` imports `string` but never uses it. It's safe to remove.
**Action:** Remove the unused import in both the `.py` script and the corresponding `.ipynb` file to keep the generator lean and consistent.
