## 2025-05-14 - XSS vulnerability in markdown generation
**Vulnerability:** The HTML escape functionality in markdown generation scripts did not escape `<` and `>` characters, and lacked robust non-string handling.
**Learning:** When ingesting external data (CSV/TSV/Bib) to output markdown, relying only on basic escaping (ampersand, quotes) allows potential HTML/script injection if tags are present in the dataset.
**Prevention:** Always escape `<` and `>` when converting data fields to markdown/HTML, and use type checking (e.g., `isinstance(text, str)`) to gracefully handle empty or non-string fields.
