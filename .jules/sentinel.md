## 2024-05-18 - XSS vulnerability in markdown generation

**Vulnerability:** The HTML escape utility `html_escape` in `markdown_generator` scripts (`publications.py`, `talks.py`, `pubsFromBib.py`, and their corresponding Jupyter notebooks) only escapes `&`, `"`, and `'`. It fails to escape `<` and `>`, which are critical for preventing Cross-Site Scripting (XSS). If untrusted data containing `<script>...` is fed through `html_escape` during markdown generation, it will be injected as raw HTML.

**Learning:** When writing custom HTML escaping utilities for statically generating markdown, one must always ensure `<` and `>` are explicitly mapped to `&lt;` and `&gt;`.

**Prevention:** Always use standard HTML escape functions (like `html.escape` in Python) if possible, or ensure custom maps include all core HTML control characters.
