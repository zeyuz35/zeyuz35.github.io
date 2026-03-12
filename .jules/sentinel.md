## 2024-05-24 - Fix XSS via unsafe YAML injection in markdown generators
**Vulnerability:** The `html_escape` function used across `markdown_generator` scripts didn't escape `<` and `>` characters, opening up XSS vulnerabilities if user-controlled metadata (e.g., from TSV or BibTeX like titles, excerpts, etc.) contains malicious HTML/scripts.
**Learning:** Even though Jekyll encodes strings, passing raw `<` and `>` tags in user-provided titles/links via front-matter could lead to raw HTML being embedded in the output.
**Prevention:** Always escape `<` and `>` to `&lt;` and `&gt;` in addition to quotes/ampersands whenever embedding user data into template or markdown generation scripts. Also, handle non-string types cleanly (like `str(text)`) to avoid exceptions.
