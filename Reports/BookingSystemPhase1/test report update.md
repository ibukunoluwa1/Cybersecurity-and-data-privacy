# Penetration Testing Report

## **1. Overview**
This document details the findings from the latest penetration test conducted on the **Booking System - Phase 1**. It also includes an update on previously identified vulnerabilities to track fixes and improvements.

## **2. Scope**
- **Target:** Booking System (Phase 1)
- **Testing Methods:** Automated and Manual Testing
- **Tools Used:**
  - OWASP ZAP
  - Burp Suite
  - Nmap
  - Checkmarx
  - Nikto
- **Date:** 27/02/2025
- **Tester:** _Ibukun Olomiyesan_

## **3. Summary of Findings**
| Vulnerability | Status | Severity | Description |
|--------------|--------|----------|-------------|
| SQL Injection | Fixed | High | Found in login form, mitigated by parameterized queries |
| Cross-Site Scripting (XSS) | Fixed | High | JavaScript sanitization applied |
| Broken Authentication | Fixed | Critical | Implemented MFA, session timeout enforcement |
| Server Misconfiguration | **Still Present** | Medium | Debug mode is enabled in production |
| Outdated Libraries | **Still Present** | Low | jQuery outdated, potential risk |

## **4. New Penetration Test Results**
- **SQL Injection:** No longer exploitable.
- **XSS:** No vulnerabilities detected.
- **Broken Authentication:** MFA implemented, reducing risk.
- **Server Misconfiguration:** Debug mode still enabled - requires fixing.
- **Outdated Libraries:** jQuery update needed.

## **5. Recommendations**
1. **Disable Debug Mode in Production**
   - Modify `settings.py` or `.env` to set `DEBUG=False`.
2. **Update jQuery Version**
   - Ensure the latest version is used to patch known vulnerabilities.
3. **Continuous Monitoring**
   - Schedule periodic security assessments.



