# Information-Disclosure-Labs-PortSwigger-Web-Security-Academy
This repository contains my write-ups for Information Disclosure vulnerabilities from the PortSwigger Web Security Academy. Each lab demonstrates how seemingly harmless information exposed by a web application can provide attackers with valuable insights into the application's internal structure, configuration, or sensitive credentials.
Lab 1 – Information Disclosure in Error Messages
Objective

Identify sensitive information exposed through verbose error messages.

Description

During this lab, the application returned detailed error messages instead of generic responses. The error output exposed internal implementation details that should not have been accessible to end users.

Methodology
Interacted with the application.
Triggered an unexpected error.
Observed the application's error response.
Identified sensitive information disclosed within the error message.
Used the disclosed information to solve the lab.
Security Impact

Verbose error messages may disclose:

Internal file paths
Framework versions
Stack traces
Database information
Source code references

This information can significantly assist attackers during the reconnaissance phase.

Remediation
Return generic error messages to users.
Log detailed errors only on the server.
Disable debugging in production.
Implement centralized exception handling.
Key Learning

Applications should never expose internal implementation details through error messages.

Lab 2 – Information Disclosure on Debug Page
Objective

Discover sensitive information exposed through an accessible debug page.

Description

The application unintentionally exposed a debugging page that contained internal application data. By accessing the debug endpoint, sensitive information became available that should only be accessible to developers.

Methodology
Explored the application.
Located the debug endpoint.
Reviewed the information displayed.
Identified the secret value exposed by the debug page.
Submitted the secret to complete the lab.
Security Impact

Exposed debug pages may reveal:

Environment variables
Secret keys
Internal configuration
Database settings
Application versions
Developer information

These disclosures increase the attack surface and may enable further exploitation.

Remediation
Disable debug mode in production.
Restrict access to development endpoints.
Remove unnecessary debugging interfaces before deployment.
Follow secure deployment practices.
Key Learning

Debug pages should never be publicly accessible in production environments.

Lab 3 – Source Code Disclosure via Backup Files
Objective

Identify sensitive information exposed through publicly accessible backup files.

Description

The application's robots.txt file disclosed the existence of a backup directory. Accessing this directory revealed a backup copy of a Java source code file containing hard-coded database credentials.

Methodology
Checked the robots.txt file.
Identified the hidden /backup directory.
Navigated to the backup location.
Located the .bak source code file.
Reviewed the source code.
Identified hard-coded database credentials.
Submitted the disclosed secret to solve the lab.
Security Impact

Exposed backup files may disclose:

Application source code
Database credentials
API keys
Internal business logic
File structure
Authentication mechanisms

Such disclosures can provide attackers with critical information for further attacks.

Remediation
Remove backup files from production servers.
Prevent public access to backup directories.
Store secrets securely using environment variables or dedicated secret management solutions.
Review deployment processes to prevent accidental exposure of development artifacts.
Key Learning

Backup files should never be publicly accessible, as they often contain highly sensitive information capable of compromising an application.

Skills Demonstrated
Information Disclosure Assessment
Web Application Reconnaissance
Source Code Review
Security Misconfiguration Identification
Sensitive Information Discovery
Debugging Endpoint Analysis
Secure Deployment Awareness
OWASP Top 10 Understanding
PortSwigger Web Security Academy Labs
Burp Suite Assisted Testing
Tools Used
Burp Suite Community Edition
Firefox Developer Tools
Kali Linux
PortSwigger Web Security Academy
References
PortSwigger Web Security Academy
OWASP Top 10
OWASP Secure Coding Practices
Burp Suite
Disclaimer

This repository contains write-ups completed in the PortSwigger Web Security Academy training environment. All activities were performed in an authorized lab created for educational purposes. The techniques documented here are intended solely for learning, ethical hacking, and improving web application security.



Author: Pawan Yadav
