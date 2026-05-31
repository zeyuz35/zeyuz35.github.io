## 2024-05-31 - Safe Logging in Exception Handlers
**Learning:** The Python scripts in the `markdown_generator` directory lacked proper logging and used direct dictionary accesses within exception blocks, leading to potential secondary `KeyError` crashes.
**Action:** Enforce the use of the `logging` module over raw print statements for professional presentation, and always use safe `.get()` dictionary methods when logging variables involved in exceptions to prevent cascading failures.
