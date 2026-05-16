## 2024-05-16 - Removed redundant imports in data generators
**Learning:** Found an unused standard library import (`string`) and a duplicate module import (`pybtex.database.input.bibtex`) in `pubsFromBib.py` and its companion notebook.
**Action:** Always check imports for redundancy, and when removing them, ensure to update both the `.py` script and the companion `.ipynb` notebook in tandem.
