## YYYY-MM-DD - Target Blank Reverse Tabnabbing Vulnerability
**Vulnerability:** Links opening in a new tab (`target="_blank"`) without `rel="noopener noreferrer"` found in `markdown_generator/pubsFromBib.py` and its corresponding Jupyter Notebook.
**Learning:** This exposes the application to reverse tabnabbing, allowing the newly opened page to potentially execute malicious code or redirect the original page. It existed because the generated markdown links appended `{:target="_blank"}` but lacked the necessary `rel="noopener noreferrer"` attributes.
**Prevention:** Always append `rel="noopener noreferrer"` when generating HTML/markdown with `target="_blank"`.
