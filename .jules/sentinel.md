## 2024-05-23 - Prevent Cross-Site Scripting (XSS) in Markdown Generators
**Vulnerability:** The `html_escape` function in markdown generator scripts failed to escape `<` and `>` characters, leaving the site vulnerable to XSS if malicious TSV/Bib data was provided.
**Learning:** Hardcoded dictionaries for HTML escaping might miss critical tags if not reviewed carefully.
**Prevention:** Standardize `html_escape` across all scripts to include `<` and `>`, and ensure type checking (`isinstance(text, str)`) prevents runtime errors or bypasses from non-string inputs.
