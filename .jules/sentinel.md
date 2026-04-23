## YYYY-MM-DD - Fix incomplete HTML escaping

**Vulnerability:** The HTML escape table used in the markdown generator scripts only escaped `&`, `"`, and `'`, failing to escape `<` and `>`, leaving the generated markdown susceptible to XSS.
**Learning:** The failure to escape angle brackets allowed potential HTML injection.
**Prevention:** Ensure all 5 standard HTML entity characters (`&`, `"`, `'`, `<`, `>`) are properly escaped when generating HTML or markdown from untrusted data sources.