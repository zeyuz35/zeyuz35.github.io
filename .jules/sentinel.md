## YYYY-MM-DD - Missing XSS protection in HTML escaping
**Vulnerability:** The custom `html_escape` logic in markdown generation scripts failed to escape `<` and `>` characters, allowing potential Cross-Site Scripting (XSS) if malicious HTML or `<script>` tags were included in the parsed TSV or BibTeX files.
**Learning:** Custom sanitization lists often miss edge cases. Hardcoded entity maps must include all critical HTML special characters (`<`, `>`, `&`, `"`, `'`) when preparing data for markdown/HTML output.
**Prevention:** Use standard libraries for HTML escaping (like `html.escape`) rather than maintaining custom dictionaries, or at minimum ensure all 5 standard entities are covered.
