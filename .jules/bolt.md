## 2024-05-19 - Fast string concatenation in pubsFromBib.py
**Learning:** Python string concatenation inside a loop (e.g. `s = s + new_string`) is a common performance anti-pattern. This codebase used this in `markdown_generator/pubsFromBib.py` for generating citations.
**Action:** Replaced loop string concatenation with `citation_parts = []`, `.append(...)`, and `"".join(citation_parts)` at the end. Applied this optimization to the source code and the corresponding Jupyter notebook json.
