## YYYY-MM-DD - Missing rel="noopener noreferrer" for target="_blank" Links
**Vulnerability:** External markdown links using `target="_blank"` lack `rel="noopener noreferrer"`, which opens up a reverse tabnabbing vulnerability.
**Learning:** These types of inline markdown tags are manually generated strings in the python scripts and notebook, so they must explicitly contain `rel="noopener noreferrer"`.
**Prevention:** Always add `rel="noopener noreferrer"` when programmatically generating `target="_blank"` anchor tags or inline markdown attributes.