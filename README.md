# VulnBank Security Assessment — TL;DR

> **Security assessment report by Komal Sai Raj Atmakuri**  
> Report ID: `VULN-2026-0001` · Assessment period: `23 Sep 2026 – 30 Sep 2026`

## Overview

A security assessment of the **VulnBank web application** identified **12 vulnerabilities** across authentication, authorization, input validation, session management, file handling, and cryptographic controls.

The assessment identified issues ranging from **Medium to Critical severity**, including broken access control, authentication bypass, injection vulnerabilities, sensitive information exposure, privilege escalation, weak password hashing, and insecure session configuration.

The complete technical report contains reproduction steps, evidence, impact analysis, CVSS details, and remediation recommendations.

## Findings at a Glance

| # | Vulnerability | CWE | CVSS | Severity |
|---|---|---|---:|---|
| 1 | Insecure Direct Object Reference (IDOR) | CWE-639 | 6.5 | Medium |
| 2 | Improper Password Reset Token Invalidation | CWE-640 | 6.5 | Medium |
| 3 | Stored Cross-Site Scripting (XSS) | CWE-79 | 6.5 | Medium |
| 4 | SQL Injection — Authentication Bypass | CWE-89 | 6.5 | Medium |
| 5 | Reflected Cross-Site Scripting (XSS) | CWE-79 | 6.5 | Medium |
| 6 | Sensitive Information Disclosure / Unauthenticated Access | CWE-200 | 7.5 | High |
| 7 | Path Traversal / Directory Traversal | CWE-22 | 7.5 | High |
| 8 | OS Command Injection | CWE-78 | 8.2 | High |
| 9 | Broken Access Control / Privilege Escalation | CWE-284 | 9.8 | **Critical** |
| 10 | Weak Password Hashing — MD5 | CWE-328 | 8.2 | High |
| 11 | Missing Brute-Force Protection | CWE-307 | 6.5 | Medium |
| 12 | Insecure Cookie Configuration / Missing Security Flags | CWE-614 | 7.5 | High |

## Key Security Themes

### 🔐 Authentication & Account Security
- SQL injection enabling authentication bypass
- Password-reset token reuse
- Missing brute-force protection
- Weak MD5 password hashing

### 🛡️ Authorization & Access Control
- IDOR allowing access to other users' profiles
- Client-controlled authorization leading to privilege escalation
- Unauthenticated access to sensitive backup data

### 💉 Injection Vulnerabilities
- SQL Injection
- Stored XSS
- Reflected XSS
- OS Command Injection

### 📁 File & Data Exposure
- Path Traversal
- Unauthenticated database backup exposure
- Exposure of password hashes and account information

### 🍪 Session Security
- Missing `HttpOnly`, `Secure`, and `SameSite` cookie attributes
- Client-controlled role information

## Overall Impact

The identified vulnerabilities could allow an attacker to:

- Access information belonging to other users
- Bypass authentication controls
- Escalate privileges to administrative functionality
- Execute client-side or operating-system commands
- Access sensitive application and account data
- Increase the likelihood of account compromise through weak authentication controls

## Assessment Approach

The assessment used a combination of:

- Manual web application security testing
- HTTP request/response analysis
- Burp Suite
- Authentication and authorization testing
- Input validation and injection testing
- Session and cookie security analysis
- Evidence collection and reproducible test cases

All testing was conducted within the authorized scope of the VulnBank assessment environment.

## Severity Distribution

- 🔴 **Critical:** 1
- 🟠 **High:** 5
- 🟡 **Medium:** 6
- 🟢 **Low:** 0

## Detailed Report

📄 **Full Vulnerability Submission Report:**  
**[View the Complete Report on Google Drive](https://drive.google.com/file/d/1Hg0kwlmZf3YcA2FnrdpSgNBebF0UrTw1/view?usp=sharing)**

The full report contains detailed reproduction procedures, proof-of-concept evidence, CVSS vectors, impact analysis, and remediation recommendations for all 12 findings.

## Disclaimer

This repository documents security research performed within an authorized assessment scope. The information is provided for cybersecurity learning, assessment documentation, and responsible security research purposes. Do not reproduce these techniques against systems without explicit authorization.

---

**Researcher:** Komal Sai Raj Atmakuri  
**Report ID:** VULN-2026-0001  
**Assessment:** VulnBank Security Assessment
