## YYYY-MM-DD - Enforce Structured Logging in Data Generators
**Learning:** Raw `print()` statements for warnings and parsing status in scripts like `markdown_generator/pubsFromBib.py` violate professional presentation standards and make output ingestion difficult.
**Action:** Replace `print()` statements with Python's standard `logging` module configured appropriately.