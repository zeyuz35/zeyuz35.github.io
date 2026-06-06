## 2024-06-07 - Removing unused imports
**Learning:** Flake8 caught unused imports in `markdown_generator/pubsFromBib.py`: `import string` and `import pybtex.database.input.bibtex` (since `from pybtex.database.input import bibtex` is used).
**Action:** Always run a linter like Flake8 on python files to catch unused imports. Also remember to check `.ipynb` files and use python to read/write JSON carefully to maintain parity with the generator python scripts.
