## 2025-02-18 - [XSS vulnerability in Markdown generation]
**Vulnerability:** The HTML escape function used in markdown generators omitted '<' and '>' which can lead to XSS.
**Learning:** Incomplete HTML escaping tables provide a false sense of security while leaving injection vectors open.
**Prevention:** Always escape '<' and '>' along with quotes and ampersands when sanitizing input for HTML output.
