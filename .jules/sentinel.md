## 2025-05-27 - Reverse Tabnabbing Vulnerability in Social Links
**Vulnerability:** External social and profile links in `_includes/social-share.html` and `_includes/author-profile.html` were missing `rel="noopener noreferrer"` attributes while using `target="_blank"`.
**Learning:** This exposes the application to reverse tabnabbing, where a maliciously crafted linked page can access the `window.opener` object and redirect the original application page to a phishing site.
**Prevention:** Always include `rel="noopener noreferrer"` whenever `target="_blank"` is used for external links to ensure the new tab runs in a separate process without access to the referencing window.
