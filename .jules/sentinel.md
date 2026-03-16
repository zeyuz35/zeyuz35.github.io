## 2024-03-16 - Prevent XSS in Markdown Generation scripts
**Vulnerability:** The HTML escape function in the `markdown_generator` scripts didn't escape `<` and `>` characters, opening up a potential Cross-Site Scripting (XSS) vulnerability.
**Learning:** The Python scripts that generated the Jekyll content correctly escaped `&`, `"`, and `'`, but did not handle `<` and `>`. If the source TSV or BibTeX content was user-provided and contained `<script>...</script>`, those tags would be evaluated on the resulting website.
**Prevention:** The `html_escape_table` mapping function should always escape `<`, `>`, `&`, `'` and `"` when converting strings that will be written into a markdown/HTML context.
