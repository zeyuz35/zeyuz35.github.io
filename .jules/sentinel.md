## 2024-05-20 - Fix XSS Vulnerability in Markdown Generator
**Vulnerability:** The `html_escape` function used in the `markdown_generator` scripts did not escape `<` and `>`, leaving the generated markdown vulnerable to Cross-Site Scripting (XSS) if malicious data was provided in TSV/BibTeX inputs.
**Learning:** Even static site generators relying on external data inputs (like CSV/TSV) need comprehensive HTML escaping because the output files (Markdown) will eventually be parsed into HTML. Missing just one or two critical characters can lead to a full XSS exploit.
**Prevention:** Always escape `<` and `>` alongside `&`, `'`, and `"` when inserting user-controlled data into HTML or Markdown contexts. Use a comprehensive HTML escape function rather than a partial list.
