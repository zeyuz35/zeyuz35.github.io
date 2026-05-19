## 2025-05-19 - Replace Raw Prints with Proper Logging
**Learning:** The `pubsFromBib.py` data generation scripts were using raw `print()` statements for messaging (success and warnings), which clutters stdout and is non-standard for script execution tracking.
**Action:** Enforce clear messaging by utilizing Python's built-in `logging` module to standardize script output, replacing `print()` with `logging.info()` and `logging.warning()`.
