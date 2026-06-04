## 2025-02-27 - Geopy Nominatim API Terms of Service Violation
**Vulnerability:** The codebase was initializing the Geopy Nominatim geocoder without specifying a custom `user_agent` in `talkmap.py` and `talkmap.ipynb`.
**Learning:** Using the default or a generic user agent string violates Nominatim's Terms of Service and leads to requests being rejected or blocked with 403 HTTP errors, essentially rendering the script useless. This represents a lack of compliance with third-party service policies.
**Prevention:** Always initialize `Nominatim` with a descriptive, application-specific `user_agent` parameter (e.g., `Nominatim(user_agent="academicpages")`) to ensure reliable and compliant API communication.
