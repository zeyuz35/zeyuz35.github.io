## 2024-05-24 - HTML Escape Omission Vulnerability
**Vulnerability:** The custom `html_escape` function used in `markdown_generator/*.py` and `*.ipynb` files did not escape the `<` and `>` characters, only `&`, `"`, and `'`. This could potentially allow Cross-Site Scripting (XSS) if user-controlled input containing `<script>` or other HTML tags was passed through these functions when generating the markdown files.
**Learning:** Even custom HTML escape functions must include the `<` and `>` characters to properly mitigate XSS risks in markdown and HTML output.
**Prevention:** Always verify that custom encoding/escaping functions cover the full set of potentially dangerous characters, or rely on built-in libraries like `html.escape` in Python.
