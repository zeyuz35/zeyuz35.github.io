## 2024-05-24 - Missing HTML escape entities for < and > and Missing rel="noopener" for target="_blank"
**Vulnerability:** XSS and Tabnabbing vulnerabilities in markdown generators
**Learning:** The custom HTML escaper `html_escape_table` in python generator scripts only escaped `&`, `"`, and `'`, leaving `<` and `>` unescaped which allows injection of HTML tags when using user-controlled fields. The generated markdown also used `target="_blank"` without `rel="noopener"` leaving generated markdown open to tabnabbing vulnerabilities.
**Prevention:** Use standard HTML escape libraries where possible or ensure all critical HTML entities (`&`, `"`, `'`, `<`, `>`) are covered when rolling a custom solution. Always use `rel="noopener"` or `rel="noopener noreferrer"` with `target="_blank"`.
