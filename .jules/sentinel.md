## 2026-03-27 - Incomplete HTML Escaping Allows XSS in Markdown Generators
**Vulnerability:** The `html_escape` function in `markdown_generator/publications.py`, `talks.py`, `pubsFromBib.py` (and their respective `.ipynb` files) misses critical character replacements, specifically `<` and `>`.
**Learning:** Incomplete implementations of HTML escaping tables can lead to Cross-Site Scripting (XSS) when generating markdown files from potentially untrusted data sources like TSV or BibTeX.
**Prevention:** Always use standard library functions like `html.escape` or ensure custom escaping tables comprehensively cover `&`, `<`, `>`, `"`, and `'`.
