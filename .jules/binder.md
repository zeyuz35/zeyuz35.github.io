## 2024-05-24 - Remove unused imports
**Learning:** The markdown generator scripts `pubsFromBib.py` and `PubsFromBib.ipynb` contained unused imports (`import string`) and redundant imports (`import pybtex.database.input.bibtex` since `from pybtex.database.input import bibtex` is already there). Both files need to be synchronized when removing these imports.
**Action:** Always check for and remove unused or redundant imports during code cleanups to keep the dependency footprint lean.
