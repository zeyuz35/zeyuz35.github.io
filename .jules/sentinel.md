## 2025-05-24 - Prevent Reverse Tabnabbing Vulnerability
**Vulnerability:** Reverse tabnabbing vulnerability via `target="_blank"` missing `rel="noopener noreferrer"`.
**Learning:** External links generated with Kramdown inline attributes `{:target="_blank"}` allow newly opened pages to gain access to the original page's `window.opener` object, which can be maliciously manipulated for phishing or redirect attacks.
**Prevention:** Always append `rel="noopener noreferrer"` when setting `target="_blank"` on links to untrusted or external domains to ensure the opener context is nullified.