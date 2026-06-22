## 2024-06-22 - Replacing raw output with structured logging
**Learning:** Generic programming best practices like safe variable access with `.get()` shouldn't be journaled as docent tips, but properly replacing raw console outputs with standard, structured application logging using the `logging` module is an important clarity and structural improvement.
**Action:** When finding raw `print()` statements representing state like warnings or successful processing, prefer migrating them to python's standard structured logging.
