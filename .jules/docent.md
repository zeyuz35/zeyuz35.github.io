## 2024-05-18 - Improve python stdout usage
**Learning:** Found several python print outputs used for logging that had misspelled outputs (`SUCESSFULLY`) and hardcoded key accesses that would cause KeyError cascades if fields were missing in the bibtex.
**Action:** Replace `print` with standard python `logging` module and use `dict.get` for safer formatting.