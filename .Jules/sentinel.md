## YYYY-MM-DD - Fix Missing HTML Escaping
**Vulnerability:** XSS vulnerability in HTML escaping
**Learning:** The `html_escape` functions across multiple Python scripts and Jupyter Notebooks failed to escape `<` and `>` characters, opening up possible XSS vectors.
**Prevention:** Always verify that character escaping dictionaries handle common HTML characters.