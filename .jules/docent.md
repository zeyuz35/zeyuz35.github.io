## 2024-05-28 - Preventing Secondary Crashes in Exception Loggers
**Learning:** Raw dictionary accesses (like `b["title"]`) within a `KeyError` exception block can cause secondary, unhandled crashes if the expected key is missing.
**Action:** Always use safe access methods like `.get("key", "default")` when extracting variables to populate log or warning messages inside exception handlers.
