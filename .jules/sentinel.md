## 2024-06-16 - Prevent Reverse Tabnabbing (Security Enhancement)
**Vulnerability:** External links generated with `target="_blank"` are vulnerable to reverse tabnabbing attacks, allowing the opened page to potentially execute malicious JavaScript in the context of the opening page.
**Learning:** `markdown_generator/pubsFromBib.py` and `markdown_generator/PubsFromBib.ipynb` hardcode external links that open in a new tab but omit the required `rel="noopener noreferrer"` attributes.
**Prevention:** Always append `rel="noopener noreferrer"` to any `target="_blank"` link to instruct the browser not to pass the `window.opener` context.
