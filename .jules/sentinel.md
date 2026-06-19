## 2024-05-15 - Reverse Tabnabbing Risk in Generated Markdown Links
**Vulnerability:** External links generated with target="_blank" without rel="noopener noreferrer".
**Learning:** In Kramdown Jekyll setups, markdown links generated via python script can introduce reverse tabnabbing if rel="noopener noreferrer" isn't explicitly added.
**Prevention:** Ensure any generated markdown files append rel="noopener noreferrer" when setting target="_blank".
