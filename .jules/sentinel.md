## YYYY-MM-DD - Fix XSS Vulnerability in Markdown Generation
**Vulnerability:** Markdown generation scripts used an incomplete HTML escape table that missed `<` and `>` characters, allowing potential XSS payloads to be rendered in the generated academicpages markdown.
**Learning:** Proper HTML escaping requires handling not just quotes and ampersands, but also angle brackets to prevent script injection. Duplicated logic across multiple script files (both `.py` and `.ipynb`) meant the vulnerability existed in several places.
**Prevention:** Always use comprehensive HTML escaping tables or established libraries (like `html.escape`) rather than partial custom dictionaries when generating markup from user-provided data sources.
