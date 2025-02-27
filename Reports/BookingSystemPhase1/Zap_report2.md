# **ZAP2 Penetration Testing Report**

## **1. Overview**
This document details the findings from the second ZAP penetration test conducted on the **Booking System - Phase 1**. The report highlights any new vulnerabilities discovered and updates on previously identified security issues.

## **2. Scope**
- **Target:** Booking System (Phase 1)
- **Testing Methods:** Automated Testing (OWASP ZAP)
- **Tools Used:**
  - OWASP ZAP
  - Checkmarx
- **Date:** _27-02-2025
- **Tester:** _Ibukun Olomiyesan_

## **3. Summary of Findings**

| Vulnerability | Status | Severity | Description |
|--------------|--------|----------|-------------|
| SQL Injection | Fixed | High | Found in login form, mitigated by parameterized queries |
| Cross-Site Scripting (XSS) | Fixed | High | JavaScript sanitization applied |
| Broken Authentication | Fixed | Critical | Implemented MFA, session timeout enforcement |
| Server Misconfiguration | **Still Present** | Medium | Debug mode is enabled in production |
| Outdated Libraries | **Still Present** | Low | jQuery outdated, potential risk |

## **4. Detailed Findings**
### **4.1 SQL Injection (Fixed)**
- Previously detected SQL Injection vulnerability was tested again, and the application now properly handles input sanitization.
- Query parameters are correctly implemented, preventing SQL injection attacks.

### **4.2 Cross-Site Scripting (XSS) (Fixed)**
- The security issue that allowed JavaScript injection has been resolved.
- All input fields properly sanitize user input to prevent XSS attacks.

### **4.3 Broken Authentication (Fixed)**
- Multi-Factor Authentication (MFA) is now enforced for all users.
- Session timeout is implemented, reducing the risk of unauthorized access.

### **4.4 Server Misconfiguration (Still Present)**
- Debug mode is still enabled in the production environment.
- Attackers could potentially exploit this to gain insight into system structure.
