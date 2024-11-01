# Task 1
# PortSwigger XSS Labs Solutions Guide
### Overview

This guide documents solutions for five Cross-Site Scripting (XSS) labs from PortSwigger's Web Security Academy. Each solution includes step-by-step instructions, payloads used, and explanations of the underlying vulnerability.

**Lab 1: Reflected XSS into HTML context with no escaping:**

**Difficulty Level: Apprentice**

**Description:**
This lab contains a simple reflected cross-site scripting vulnerability in the search functionality.
Solution Steps

Navigate to the lab's search functionality
Input a basic XSS payload: <script>alert(1)</script>
Submit the search form
The payload executes, demonstrating the vulnerability   
***Lab is marked as solved***



**Technical Explanation:**

The application reflects user input from the search parameter directly into the response without any sanitization or encoding, allowing arbitrary JavaScript execution.

**Lab 2: Stored XSS into HTML context with nothing encoded**

**Difficulty Level:** Apprentice

**Description:**
This lab contains a stored XSS vulnerability in the comment functionality.
Solution Steps

Navigate to a blog post
Find the comment submission form
Enter the following payload in the comment field:

htmlCopy<script>alert(document.cookie)</script>

Submit the comment
The payload persists and executes whenever the page is visited  
***Lab is marked as solved***

**Technical Explanation:**

The application stores user input from comments without sanitization and reflects it back to all users who view the page, creating a persistent XSS vulnerability.

**Lab 3: DOM XSS in document.write sink using source location.search**

**Difficulty Level: Apprentice**

**Description:**
This lab contains a DOM-based XSS vulnerability in the search functionality.
Solution Steps

Identify the vulnerable JavaScript code using browser developer tools
Notice that the application uses document.write with user input
Craft payload: "><script>alert(document.domain)</script>
Submit via the search functionality
The payload executes through DOM manipulation  
***Lab is marked as solved***

**Technical Explanation:**

The application uses document.write to display search terms, creating a DOM-based XSS vulnerability when user input is not properly encoded.

**Lab 4: Reflected XSS into attribute with angle brackets HTML-encoded**

**Difficulty Level: Practitioner**

Solution Steps

Identify that the input is reflected inside an attribute
Notice angle brackets are encoded but quotes aren't
Craft payload: " onmouseover="alert(1)
Submit the payload
Move mouse over the injected attribute to trigger the XSS   
***Lab is marked as solved***

**Technical Explanation:**

While angle brackets are encoded, the application fails to encode quotes, allowing attackers to break out of the attribute context and inject event handlers.

**Lab 5: Stored XSS into anchor href attribute with double quotes HTML-encoded**

**Difficulty Level: Practitioner**

Solution Steps

Locate the vulnerable input field that creates a link
Notice that double quotes are encoded
Craft payload: javascript:alert(document.domain)
Submit the payload in the website field
Click the created link to trigger the XSS  
***Lab is marked as solved***

**Technical Explanation:**

The application allows javascript: URLs in href attributes, enabling XSS even when other special characters are encoded.

**Security Reminders:**

These exercises should only be performed in PortSwigger's lab environment
Never test XSS vulnerabilities on production websites without explicit permission
Real-world XSS can lead to session hijacking, data theft, and other serious security issues
Always follow responsible disclosure practices when finding vulnerabilities

**Additional Resources:**

PortSwigger XSS Documentation
OWASP XSS Prevention Cheat Sheet
PortSwigger Web Security Academy
