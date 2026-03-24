## 2025-03-24 - HTML escaping for XSS prevention
**Vulnerability:** The HTML escape function in `markdown_generator` scripts only escaped `&`, `"`, and `'`, but missed `<` and `>`. This allowed potential Cross-Site Scripting (XSS) attacks when malicious HTML payloads were present in TSV or BibTeX files.
**Learning:** `html_escape_table` in custom sanitization functions must explicitly map all high-risk HTML characters, including `<` and `>`, to properly mitigate XSS risks, especially when parsing untrusted or user-controlled input files.
**Prevention:** Always use established libraries (like Python's built-in `html.escape`) or ensure custom encoding dictionaries cover all five critical HTML characters (`&`, `<`, `>`, `"`, `'`).
