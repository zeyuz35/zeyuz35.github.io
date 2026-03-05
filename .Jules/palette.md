## 2024-05-14 - Skip to content missing
**Learning:** The layouts here lack a "skip to content" link which is crucial for screen readers and keyboard users to bypass repetitive navigation. There is an existing `.skip-link` CSS class that isn't being used.
**Action:** Add a "Skip to content" link as the first item in the DOM right after `<body>`, using the existing `.skip-link` and `.screen-reader-text` classes, and pointing it to `#main` which is already defined on major page layouts.
