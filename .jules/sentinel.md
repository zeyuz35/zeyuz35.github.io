## 2024-05-18 - Reverse Tabnabbing Vulnerability
**Vulnerability:** Markdown links generated with `target="_blank"` attribute in Kramdown/Jekyll configurations lacked `rel="noopener"`.
**Learning:** Reverse Tabnabbing can allow newly opened tabs to hijack the `window.opener` object and maliciously modify the original page.
**Prevention:** Always append `rel="noopener"` to external links that open in a new tab.