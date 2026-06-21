## 2025-02-14 - Replace raw print statements with structured logging
**Learning:** Found raw `print()` statements in `markdown_generator/pubsFromBib.py` used to output status and warning messages, which should be replaced with structured `logging`.
**Action:** Replaced `print()` with `logging.info()` and `logging.warning()` for better message handling and consistency. Applied equivalent updates to corresponding `PubsFromBib.ipynb` using a python helper script to ensure parity.
