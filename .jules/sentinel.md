## YYYY-MM-DD - Fix target="_blank" vulnerability
**Vulnerability:** Reverse tabnabbing vulnerability due to `target="_blank"` without `rel="noopener noreferrer"`.
**Learning:** When generating Markdown or HTML files with external links, adding `target="_blank"` allows the new page to access the original window object via `window.opener`. This is a security risk.
**Prevention:** Always append `rel="noopener noreferrer"` when setting `target="_blank"` to protect the host page.
