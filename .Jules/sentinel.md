## YYYY-MM-DD - Missing HTML Escaping for XSS Prevention
**Vulnerability:** The HTML escape function used during markdown generation from TSV and BibTeX data omitted escaping for `<` and `>` characters, opening up Cross-Site Scripting (XSS) risks.
**Learning:** Even custom markdown generator scripts need to thoroughly escape all XSS-sensitive HTML characters, not just quotes and ampersands, as the resulting markdown is rendered to HTML on the static site.
**Prevention:** Use standard libraries for HTML escaping where possible, or ensure custom escaping functions cover the complete set of standard HTML entities (`&`, `"`, `'`, `<`, `>`).
