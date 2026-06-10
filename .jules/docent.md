## 2024-06-11 - Replace raw print statements with structured logging
**Learning:** When replacing print statements with logging inside exception blocks like `KeyError` on dictionary elements, direct accesses (e.g., `b["title"]`) can cause secondary crashes if the key doesn't exist.
**Action:** Always use safe dictionary access methods like `.get("key", "default")` within exception handlers when logging missing data.
