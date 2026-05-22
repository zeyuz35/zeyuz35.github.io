## 2025-02-23 - Enforce structured logging instead of raw print statements
**Learning:** Found raw `print()` statements and informal language/spelling ("SUCESSFULLY PARSED") in `markdown_generator/pubsFromBib.py` and its companion notebook `PubsFromBib.ipynb`. This violates professional documentation/style standards.
**Action:** Replaced these informal print statements with structured `logging.info()` and `logging.warning()` utilizing Python's `logging` module to ensure clear messaging. Always make sure to update companion `.ipynb` files in tandem with the `.py` scripts.
