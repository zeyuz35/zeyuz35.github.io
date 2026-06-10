## 2024-05-24 - Removed unused import string from pubsFromBib generator
**Learning:** Found an unused import (`import string`) in `markdown_generator/pubsFromBib.py` which was likely a remnant from an older iteration. It doesn't use `string` module functionalities.
**Action:** Remove the unused import in both the `.py` and `.ipynb` files to improve package hygiene.
