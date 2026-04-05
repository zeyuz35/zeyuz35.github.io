## 2024-06-05 - Fix Tabnabbing Vulnerability
**Vulnerability:** Markdown generator creates links with `target="_blank"` but does not include `rel="noopener"` or `rel="noopener noreferrer"`.
**Learning:** This is a Tabnabbing vulnerability, where the newly opened page can access the original window's `window.opener` object, potentially navigating the original page to a malicious site. The Kramdown syntax for Jekyll allows setting these attributes, but they are missing.
**Prevention:** Always use `rel="noopener"` or `rel="noopener noreferrer"` when setting `target="_blank"` on links to untrusted/external sites.
