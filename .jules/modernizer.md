## 2024-06-14 - Replace iterrows() with itertuples()
**Learning:** Found uses of pandas `iterrows()` in scripts like `markdown_generator/publications.py` and `markdown_generator/talks.py` where the index variable is unused and the item works perfectly well with namedtuple property access.
**Action:** Replace `iterrows()` with `itertuples()` to improve performance while maintaining readability.
