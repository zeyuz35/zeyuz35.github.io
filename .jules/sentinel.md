## YYYY-MM-DD - Reverse Tabnabbing Vulnerability in Markdown Links
**Vulnerability:** Found `{:target="_blank"}` attributes in `markdown_generator/pubsFromBib.py` and `markdown_generator/PubsFromBib.ipynb` used for external links without `rel="noopener noreferrer"`.
**Learning:** Using `target="_blank"` without `rel="noopener noreferrer"` on external links allows the newly opened tab to retain a reference to the `window.opener` object, creating a Reverse Tabnabbing vulnerability. A malicious site could use this reference to redirect the original page to a phishing site.
**Prevention:** Always include `rel="noopener noreferrer"` when generating external links with `target="_blank"` using Kramdown inline attributes or direct HTML.
