## 2025-02-14 - Missing XSS Prevention in Custom HTML Escaper
**Vulnerability:** XSS vulnerability due to the `html_escape_table` custom escaper missing `<` and `>` escaping.
**Learning:** Custom implementations of HTML escaping are risky because it's easy to forget characters like `<` and `>`. Relying on custom tables instead of standard libraries like `html.escape` caused this XSS gap.
**Prevention:** Use established standard library functions for escaping, or thoroughly test custom implementations to ensure they cover critical XSS characters like `<` and `>`.
