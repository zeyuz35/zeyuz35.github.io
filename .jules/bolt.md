## 2024-05-24 - Optimizing Citation String Concatenation in Python Scripts

**Learning:** Manual string concatenation within loops (`citation = citation + ...`) in `markdown_generator/pubsFromBib.py` and `markdown_generator/PubsFromBib.ipynb` is inefficient in Python because strings are immutable, leading to repeated memory allocation and copying.
**Action:** Replace `citation = citation + ...` with list appends and `"".join()` for O(N) linear time performance instead of O(N^2) quadratic time.
