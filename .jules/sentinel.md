## YYYY-MM-DD - Missing HTML Escaping for XSS Prevention
**Vulnerability:** The HTML escape logic for TSV and BibTeX processing only escaped quotes and ampersands, missing `<` and `>` characters, allowing potential XSS payloads when generating markdown.
**Learning:** Basic string replacements in legacy scripts often miss standard XSS vectors if they do not use standard, comprehensive encoding libraries.
**Prevention:** Use established HTML encoding libraries or include comprehensive manual lists of XSS-prone characters (`<`, `>`, `&`, `"`, `'`).
