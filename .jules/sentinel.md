## 2025-03-08 - Added rel="noopener noreferrer" to external target="_blank" links
**Vulnerability:** External links generated with `target="_blank"` without `rel="noopener noreferrer"` can expose the site to reverse tabnabbing attacks. The external page can access the original `window.opener` object and redirect the user's original page to a malicious site.
**Learning:** The Python scripts that generated markdown content in `markdown_generator/pubsFromBib.py` and its corresponding Jupyter notebook `PubsFromBib.ipynb` were adding `target="_blank"` directly to markdown syntax without `noopener noreferrer`.
**Prevention:** Always add `rel="noopener noreferrer"` when setting `target="_blank"` on links, including in generators that output HTML or Markdown that supports attributes.
