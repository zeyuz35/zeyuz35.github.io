## YYYY-MM-DD - Remove unused and redundant imports
**Learning:** The `pubsFromBib.py` and its corresponding Jupyter notebook `PubsFromBib.ipynb` contained an unused `string` module import and a redundant `import pybtex.database.input.bibtex` import (as `from pybtex.database.input import bibtex` was already present). Both files must be updated in tandem to maintain consistency.
**Action:** Audit and remove unused/redundant imports across both Python scripts and their corresponding Jupyter notebooks simultaneously to ensure cleaner dependency footprint without breaking functionality.
