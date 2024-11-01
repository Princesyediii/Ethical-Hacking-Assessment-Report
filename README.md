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
                                       
                        
                                                                                  
                                                                                                             
# Task 2
# Vulnerability Assessment Presentation Report
### Introduction

Local File Inclusion Exploitation (LFI) Feature in Netsparker

In this Netsparker web security tutorial we will use a local file inclusion vulnerability which was discovered by Netsparker web application security scanner and exploit it using the Netsparker exploitation engine. As you can see screenshots images it is very easy to use Netsparker and exploit reported web application vulnerabilities.

Netsparker is a false positive free web application security scanner and is used by government agencies, financial institutions, software companies and many other world renowned companies such as Samsung, EA Sports, Skype, ING Bank and Ernst & Young.


## Additional Vulnerabilities 

Even If you are not a seasoned web security expert or penetration tester, it is possible to easily and automatically detect SQL Injection, Cross-site scripting (XSS) and other web application vulnerabilities in your websites and web applications with Netsparker. Since Netsparker automatically exploits detected web vulnerabilities using read only safe methods, there is no need for testers to verify if the reported vulnerabilities are false positives.

An out of the box installation of Netsparker can scan any type of website and web application built in PHP, .NET, Perl, Java and other popular web development frameworks without the need for it to be extensively configured. Netsparker automates most of the tasks for you. For example it can automatically identify custom 404 error pages, URL rewrite rules, anti-CSRF tokens etc, therefore you do not need to spend time configuring the web security scanner. 

Even though Netsparker boasts a very easy to use interface, it presents developers and security auditors with all the needed technical details of the identified web application vulnerabilities. It also suggests practical solutions to help developers remediate the vulnerabilities.


## Report:

### ***NO request has been carried out for the selected resource.***

In the Images you will see how easy it is to launch a vulnerability scan against a website or web application using the false positive free web application security scanner Netsparker.

## Conclusion

Netsparker is not just an automated web application security scanner. It is a featureful web application security tool that can be used and integrated at every stage of the SDLC (software development lifecycle) of any web application. For example it has a scheduler to schedule repetitive automated web vulnerability scans, a reporter to generate professional technical and compliance reports, a command line interface to easily integrate with other tools and much more. 

Netsparker also supports several open source and free web security tools




# Task 3

# Cross-Site Scripting (XSS)

**Description:**

The site is vulnerable to XSS attacks, allowing attackers to inject malicious scripts into web pages viewed by other users.

**Method of Discovery:**

Injected script tags into input fields (e.g., <script>alert(0 / 1)</script>).
Observed that the script executed in the browser, confirming the vulnerability.


**Impact:** 

An attacker could execute scripts in the context of another user's session, leading to data theft or session hijacking.


**Conclusion:** 

The assessment of testasp.vulnweb.com/ revealed several critical vulnerabilities, including SQL Injection, Directory Traversal, and Cross-Site Scripting. These vulnerabilities pose significant risks to the security of the application and its users.

**Recommendations** 

**For SQL Injection:** 
Implement prepared statements and parameterized queries to prevent SQL injection.
**For Directory Traversal:**
Validate and sanitize user inputs to restrict access to sensitive files.
**For XSS:**
Use output encoding and content security policies to mitigate XSS risks.


***This report serves as a documentation of the vulnerabilities found and the methods used to discover them. Further actions should be taken to remediate these vulnerabilities to enhance the security of the application.***

# *** ***Thank You!*** ***
