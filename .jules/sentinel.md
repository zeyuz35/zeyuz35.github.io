## 2025-03-23 - Prevent Cross-Site Scripting (XSS) in Markdown Generators
**Vulnerability:** The HTML escape utility `html_escape_table` in the Markdown generator scripts and notebooks only escaped ampersands, double quotes, and single quotes. This meant that less-than `<` and greater-than `>` characters could be injected from user-controlled metadata fields, potentially allowing Cross-Site Scripting (XSS) attacks in the generated Markdown.
**Learning:** The previous escaping mechanism missed essential character substitutions required to safely render input fields as text, leading to XSS vulnerabilities.
**Prevention:** Always escape `<` to `&lt;` and `>` to `&gt;` alongside `&`, `"`, and `'` when handling user input that will be inserted into Markdown or HTML to effectively prevent XSS.
