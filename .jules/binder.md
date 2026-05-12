## 2024-05-13 - Remove Unused Imports in markdown_generator
**Learning:** The `markdown_generator/` directory contains companion Python scripts and Jupyter notebooks (e.g., `pubsFromBib.py` and `PubsFromBib.ipynb`). Unused imports like `string` and redundant module imports (e.g., `import pybtex.database.input.bibtex` alongside `from pybtex.database.input import bibtex`) can accumulate here.
**Action:** Always check both the `.py` script and the corresponding `.ipynb` notebook when removing unused imports to keep them synchronized and maintain a lean dependency footprint.
