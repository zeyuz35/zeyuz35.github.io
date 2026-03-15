## 2026-03-15 - Add missing characters to html_escape_table
**Vulnerability:** The `html_escape_table` in the markdown generator scripts only escaped `&`, `"`, and `'`, but completely ignored `<` and `>`. This could lead to Cross-Site Scripting (XSS) when user input is used to generate HTML/Markdown.
**Learning:** Security controls must be comprehensive. Escaping only some special characters still leaves applications vulnerable to XSS.
**Prevention:** Always use standard library functions or comprehensive mapping tables when escaping user input.
