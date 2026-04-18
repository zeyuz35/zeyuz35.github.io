## YYYY-MM-DD - [HIGH] Fix XSS vulnerability in markdown generation
**Vulnerability:** Missing HTML escaping for `<` and `>` in `html_escape_table` allows Cross-Site Scripting (XSS) when parsing external data sources to Markdown.
**Learning:** Even when converting to Markdown, HTML tags can pass through unescaped. It is critical to sanitize all special HTML characters (`<`, `>`, `&`, `"`, `'`) when building strings dynamically from untrusted inputs like TSVs or BibTeX files.
**Prevention:** Always use comprehensive HTML escaping utilities instead of custom, partial escape tables. Ensure both scripts and interactive notebooks share the secure logic.
