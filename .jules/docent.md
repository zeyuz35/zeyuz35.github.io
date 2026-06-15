## YYYY-MM-DD - [Title]
**Learning:** [Insight]
**Action:** [How to apply next time]
## YYYY-MM-DD - Replace Raw Print Statements With Structured Logging
**Learning:** Found raw `print()` statements and a typo ("SUCESSFULLY") used for diagnostic output in the `pubsFromBib.py` script and the corresponding `PubsFromBib.ipynb` notebook. The code lacked proper structure and formatting. Furthermore, handling `b["title"]` in a `KeyError` exception block caused issues when `title` was the very key that was missing.
**Action:** Always replace raw diagnostic prints with the `logging` module (`logging.info`, `logging.warning`) and configure it properly. Use `.get()` with a default value when formatting logging messages in exception blocks to safely retrieve dictionary values and prevent secondary crashes.
