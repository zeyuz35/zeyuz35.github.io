## YYYY-MM-DD - Fix Reverse Tabnabbing in Markdown Generation
**Vulnerability:** External links generated with `target="_blank"` lack `rel="noopener noreferrer"`.
**Learning:** Kramdown inline attributes `{:target="_blank"}` in markdown files can introduce reverse tabnabbing if not accompanied by `rel="noopener noreferrer"`.
**Prevention:** Always append `rel="noopener noreferrer"` when setting `target="_blank"` for external URLs in generated markdown.
