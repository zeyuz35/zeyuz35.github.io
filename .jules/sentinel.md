## YYYY-MM-DD - [XSS vulnerability in HTML escaping logic]
**Vulnerability:** HTML escaping logic `html_escape_table` was missing escaping for `<` and `>`, leading to potential Cross-Site Scripting (XSS) via injected HTML elements.
**Learning:** Basic replacement of quotes and ampersands is insufficient for XSS prevention when user input is rendered as markdown/HTML.
**Prevention:** Always escape `<` and `>` to `&lt;` and `&gt;` when manually implementing HTML sanitization to prevent unescaped HTML tag injection.