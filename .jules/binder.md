## 2025-05-11 - Removed unused imports from pubsFromBib generator
**Learning:** The codebase includes Jupyter notebooks and companion Python scripts that must be kept synchronized. When removing unused Python imports (like pybtex and string), they must be removed from both the `.py` script and the `.ipynb` JSON source.
**Action:** Always check for matching `.ipynb` counterparts when modifying `markdown_generator` Python scripts, and use standard newline `\n` matching when replacing strings programmatically in Jupyter notebooks.
