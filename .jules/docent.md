## 2025-05-31 - Safe Dictionary Access During Exception Logging
**Learning:** When adding logging statements inside exception handlers like `except KeyError`, using direct dictionary access (e.g., `b["title"]`) to enrich the log message can trigger a secondary exception if that key is the one missing, crashing the script.
**Action:** Always use safe dictionary access methods like `.get("title", "")` when logging variable contents within exception handlers.

## 2025-05-31 - Respecting File Headers When Prepending Imports
**Learning:** Prepending imports naively to the top of a Python script can break shebangs (`#!/usr/bin/env python`) and encoding declarations (`# coding: utf-8`), causing execution errors or linting failures.
**Action:** When programmatically adding imports, explicitly check for and preserve leading shebangs and encoding comments, inserting the new imports below them.
