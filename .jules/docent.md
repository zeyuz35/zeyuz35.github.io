## 2024-06-11 - Replace raw prints with structured logging
**Learning:** Using raw print statements in production or documentation generator code can lead to unstructured and unmanageable output. When replacing them with structured logging inside exception handlers (e.g., KeyError), variables should be accessed safely using methods like `.get()` to prevent secondary crashes if the key is missing.
**Action:** Always prefer `logging` module over raw `print` statements, and safely access dictionary keys when logging inside exception handlers.
