## 2024-05-13 - Replace iterrows() with itertuples() in pandas DataFrames
**Learning:** In the `markdown_generator` scripts, iterating over pandas DataFrames was done using `iterrows()`. This method is noticeably slow as it boxes each row into a Series object.
**Action:** Used `itertuples()` instead, which returns a namedtuple and is often over an order of magnitude faster when iterating through pandas DataFrames.
