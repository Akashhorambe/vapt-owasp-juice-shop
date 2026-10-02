# Web Application VAPT & Risk Assessment (OWASP Juice Shop)

A comprehensive Vulnerability Assessment and Penetration Testing (VAPT) portfolio project demonstrating manual exploitation, business risk analysis, and secure code remediation based on the **OWASP Top 10 (2021)** framework.


## 🎯 Project Overview
The objective of this engagement was to evaluate the security posture of OWASP Juice Shop (v20.2.0), a modern Node.js/Angular e-commerce application. The assessment simulated an unauthenticated, external threat actor to identify logical flaws, injection vectors, and access control bypasses.

**Tools Utilized:**
*   **Burp Suite Community Edition** (Traffic interception, parameter tampering)
*   **Browser Developer Tools** (Client-side logic analysis, route discovery)
*   **Gobuster / FFuF** (Directory enumeration)
*   **OSINT** (Background profiling for authentication bypass)

## 🛑 Key Findings Summary
The assessment uncovered 9 distinct vulnerabilities spanning Critical to Low severity. Business impact was calculated using **CVSS v3.1** metrics.

*   **Critical:** Authentication Bypass via SQL Injection (CVSS 9.8)
*   **High:** Insecure Direct Object References / IDOR (CVSS 7.5)
*   **High:** Unrestricted File Upload (CVSS 7.5)
*   **High:** Broken Access Control to Administration Panel (CVSS 7.5)
*   **High:** DOM-Based Cross-Site Scripting / XSS (CVSS 7.1)
*   **Medium:** Business Logic Flaw / Negative Basket Pricing (CVSS 6.5)
*   **Medium:** Weak Authentication / Predictable Security Questions (CVSS 5.3)
*   **Medium:** Directory Listing & Sensitive File Exposure (CVSS 5.3)
*   **Low:** Missing HTTP Security Headers (CVSS 3.7)

## 💡 Remediation Strategy
The accompanying PDF report does not just list exploits; it provides actionable, code-level recommendations for engineering teams. Key remediation strategies proposed include:
*   Implementation of **Parameterized Queries (Prepared Statements)** in the backend ORM.
*   Enforcement of **Server-Side Role-Based Access Control (RBAC)** relying on secure JWT claims rather than client-side route hiding.
*   Strict backend validation of transactional integers (e.g., rejecting negative basket quantities).
*   Deprecation of Knowledge-Based Authentication in favor of out-of-band email reset flows.

---
*Disclaimer: This repository is for educational and portfolio purposes only. All testing was conducted in a local, authorized, deliberately vulnerable lab environment.*
