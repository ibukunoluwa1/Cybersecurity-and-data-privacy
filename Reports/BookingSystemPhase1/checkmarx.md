# Checkmarx Security Scan Report

## **1. Overview**
This report contains the findings from the latest Checkmarx security scan conducted on the **Booking System - Phase 1**.

## **2. Scan Details**
- **Application:** Booking System (Phase 1)
- **Scan Type:** Static Code Analysis (SAST)
- **Date:** _(27-02-2025)_
- **Scan Tool:** Checkmarx
- **Tester:** _(Ibukun)_

## **3. Summary of Findings**
| Vulnerability | Status | Severity | Description |
|--------------|--------|----------|-------------|
| SQL Injection | Fixed | High | Identified in user authentication module, now mitigated |
| Cross-Site Scripting (XSS) | Fixed | High | Found in the search function, resolved with input sanitization |
| Hardcoded Secrets | **Still Present** | Critical | API keys found in environment variables |
| Insecure Dependencies | **Still Present** | Medium | Use of outdated third-party libraries |
| Security Misconfiguration | **Still Present** | Medium | Debug mode enabled in production |

## **4. Detailed Findings**
### **4.1 SQL Injection (Fixed)**
- Issue: User authentication was vulnerable to SQL Injection.
- Resolution: Implemented parameterized queries.
- Verification: Retested using manual queries, no further injection possible.

### **4.2 Cross-Site Scripting (Fixed)**
- Issue: XSS found in the search function.
- Resolution: Input validation and output encoding applied.
- Verification: No longer possible to inject scripts.

### **4.3 Hardcoded Secrets (Still Present)**
- Issue: API keys and database credentials were found in `.env` files.
- Recommended Fix: Store secrets in a secure vault or use environment variables.

### **4.4 Insecure Dependencies (Still Present)**
- Issue: Application is using outdated libraries.
- Recommended Fix: Upgrade dependencies using `npm audit fix` or `pip list --outdated`.

### **4.5 Security Misconfiguration (Still Present)**
- Issue: Debug mode is still enabled in the production environment.


## **5. Recommendations**
1. **Remove Hardcoded Secrets**
   - Store sensitive credentials in a vault like AWS Secrets Manager or `.env` files.
2. **Update Insecure Dependencies**
   - Regularly check for outdated dependencies and upgrade accordingly.
3. **Disable Debug Mode**
   - Ensure `DEBUG=False` in production environments.
4. **Implement Continuous Security Testing**
   - Integrate Checkmarx into CI/CD pipelines for automated scans.

## **6. Next Steps**
1. **Fix outstanding vulnerabilities** within the next sprint.
2. **Conduct a follow-up scan** to verify mitigation measures.
3. **Log changes** in the cybersecurity documentation.
