## 2025-05-17 - Missing HTML Tag Escaping in Custom Sanitizer
**Vulnerability:** The custom `html_escape_table` used across markdown generators failed to escape `<` and `>` characters, exposing an XSS vector if untrusted content is included.
**Learning:** Rolling a custom sanitization dictionary often results in omissions of critical HTML characters compared to built-in libraries like `html.escape`.
**Prevention:** Use standard library functions for escaping, or ensure all critical characters (`&`, `<`, `>`, `"`, `'"'`) are explicitly covered, and strictly validate/type-check inputs.