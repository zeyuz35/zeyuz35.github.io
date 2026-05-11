## 2026-05-11 - Replace raw print statements with proper logging
**Learning:** In Jupyter notebook files, the `source` field in cells is an array of strings, so programmatic updates should carefully modify the exact lines and preserve the exact indentation (`indent=1`) when dumping back to JSON to avoid massive formatting diffs.
**Action:** When updating Jupyter notebooks programmatically, use `json.load` and `json.dump(..., indent=1)` and surgically modify the `source` lists instead of raw regex on the JSON string.
