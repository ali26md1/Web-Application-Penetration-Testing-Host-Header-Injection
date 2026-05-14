# Host Header Injection Testing using BurpSuite

## Overview

This project demonstrates practical Host Header Injection testing using BurpSuite and intentionally vulnerable web application environments provided by PortSwigger Web Security Academy.

The project focuses on identifying security weaknesses related to improper handling of HTTP Host headers and forwarded headers during password reset functionality testing.

---

# Objectives

* Understand Host Header Injection vulnerabilities
* Perform HTTP request interception using BurpSuite
* Analyze password reset request behavior
* Manipulate Host-related headers
* Test X-Forwarded-Host handling
* Test duplicate Host header behavior
* Document security findings and mitigation strategies

---

# Tools Used

* BurpSuite Community Edition
* BurpSuite Proxy
* BurpSuite Repeater
* PortSwigger Web Security Academy
* Exploit Server

---

# Testing Performed

## 1. HTTP Traffic Interception

Captured HTTP requests and responses using BurpSuite Proxy.

## 2. Password Reset Request Analysis

Analyzed password reset functionality for Host header manipulation opportunities.

## 3. Host Header Manipulation

Modified HTTP Host headers using BurpSuite Repeater.

Example Payload:

```http
Host: attacker.com
```

## 4. X-Forwarded-Host Testing

Tested application behavior using forwarded Host-related headers.

Example Payload:

```http
X-Forwarded-Host: attacker.com
```

## 5. Duplicate Host Header Testing

Tested application response behavior using multiple Host headers.

Example Payload:

```http
Host: original-domain.com
Host: attacker.com
```

---

# Key Findings

* Application accepted manipulated Host headers
* Password reset functionality continued processing after header modification
* X-Forwarded-Host values were not strictly validated
* Duplicate Host headers produced abnormal behavior
* Manipulated Host values caused inconsistent responses

---

# Potential Risks

* Password reset poisoning
* Credential theft
* Phishing attacks
* Reverse proxy confusion
* Cache poisoning
* Authentication manipulation

---

# Mitigation Strategies

* Enforce strict Host header validation
* Reject duplicate Host headers
* Sanitize X-Forwarded-* headers
* Harden reverse proxy configurations
* Conduct regular security assessments

---

# Project Structure

```text
Host_Header_Injection_Project/
│
├── Screenshots/
├── Payloads/
├── Notes/
└── Reports/
```

---

# References

1. PortSwigger Web Security Academy
   https://portswigger.net/web-security/host-header

2. OWASP Web Security Testing Guide
   https://owasp.org/www-project-web-security-testing-guide/

3. BurpSuite Documentation
   https://portswigger.net/burp/documentation

---

# Disclaimer

This project was performed in controlled and intentionally vulnerable lab environments strictly for educational and cybersecurity learning purposes.
