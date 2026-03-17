## 2024-05-24 - Add XSS protection for markdown generators
**Vulnerability:** XSS vulnerability in markdown generators where user input wasn't properly escaped for `<` and `>`.
**Learning:** `html_escape_table` in the markdown generators was missing `<` and `>` entities mapping.
**Prevention:** Make sure to map `<` to `&lt;` and `>` to `&gt;` in addition to handling quotes and ampersands.
