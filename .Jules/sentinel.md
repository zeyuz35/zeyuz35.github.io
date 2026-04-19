## YYYY-MM-DD - Missing HTML Escaping
**Vulnerability:** The markdown generators (e.g. `talks.py`, `publications.py`) did not escape `<` and `>` characters when converting TSV/BibTeX to Markdown.
**Learning:** User-provided inputs in data files can contain raw HTML/scripts. The existing html_escape_table only escaped `&`, `"`, and `'`.
**Prevention:** Always escape `<` and `>` when rendering raw user text into an environment that interprets HTML.
