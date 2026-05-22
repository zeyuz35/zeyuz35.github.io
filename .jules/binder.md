## 2024-05-18 - Audit for Unused Imports in Scripts and Notebooks
**Learning:** Python scripts and their companion Jupyter notebooks can easily accumulate unused standard library or third-party imports over time (like `string` and redundant `pybtex` imports). Both must be updated in tandem.
**Action:** Always search for identical unused imports across both `.py` and `.ipynb` files in the `markdown_generator` directory when performing a package hygiene audit.
