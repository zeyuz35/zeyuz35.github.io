## 2024-05-18 - Replacing Raw Prints with Logging
**Learning:** The Python scripts (like `pubsFromBib.py`) for the Jekyll academic pages use raw `print()` statements for reporting parsing successes and warnings. Often inside a `try/except KeyError` block. If `b["title"]` throws a `KeyError` within the `except` block print itself, it leads to a secondary crash.
**Action:** When replacing raw `print()` with `logging`, make sure to use `dict.get("title", "Fallback")` to prevent secondary `KeyError` crashes in the logging statement itself.
