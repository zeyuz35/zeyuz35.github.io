## 2024-06-09 - Safe Dictionary Access in Exception Logging
**Learning:** When logging variables that caused exceptions (like `KeyError`), using direct key access (e.g., `b["title"]`) can trigger a secondary crash if the key is missing.
**Action:** Always use safe dictionary access methods like `.get()` (e.g., `b.get("title", "")`) when logging within exception handlers to prevent secondary crashes.
