# 📌 Booking System - Phase 1 Security Test Report

## **1️⃣ Overview**
- **Application:** Booking System Ver1
- **Testing Date:** February 19, 2025
- **Tested By:** Ibukunoluwa Olomiyesan 
- **Testing Tools:** OWASP ZAP, Gobuster, SQL Injection, XSS payloads.

## **2️⃣ Functionality Testing Results**
| Test | Expected Outcome | Result |
|------|-----------------|--------|
| Weak Password (`12345`) | Should be rejected | ❌ (Accepted) |
| SQL Injection (`' OR '1'='1' --`) | Should be rejected | ❌ (Login Bypassed) |
| XSS (`<script>alert('XSS')</script>`) | Should be escaped | ❌ (Alert Shown) |
| Missing CSRF Token | Should have protection | ❌ (No CSRF Token) |

## **3️⃣ Security Vulnerabilities**
### 🔹 **SQL Injection**
- **Vulnerable Fields:** Username, Password
- **Payload Used:** `' OR '1'='1' --`
- **Impact:** **Login bypass possible**.

### 🔹 **Cross-Site Scripting (XSS)**
- **Vulnerable Fields:** Username, Email
- **Payload Used:** `<script>alert('XSS')</script>`
- **Impact:** **User session hijacking risk**.

### 🔹 **Missing CSRF Protection**
- **Observation:** No CSRF tokens in form requests.
- **Impact:** **Account takeover possible via forged requests**.

## **4️⃣ OWASP ZAP Report**
The full ZAP scan report is included in this repository.

## **5️⃣ Recommendations**
✅ **Fix SQL Injection** → Use **prepared statements**.  
✅ **Prevent XSS** → Sanitize inputs using **HTML encoding**.  
✅ **Implement CSRF Protection** → Add **CSRF tokens** in all forms.  
✅ **Enforce Strong Passwords** → Require **8+ characters, symbols, and numbers**.  

---














