## 2024-05-18 - Safe Logging within Exception Handlers
**Learning:** Raw print statements in exception handlers that directly access dictionary keys (e.g. `b["title"]`) can cause secondary KeyError crashes if the key doesn't exist, obscuring the original issue.
**Action:** Replace raw print statements with proper logging and always use safe dictionary access methods like `.get()` instead of direct key access when logging variables within exception handlers to prevent secondary crashes.
