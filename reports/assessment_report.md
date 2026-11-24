\# Project 04: Login Page Penetration Testing Report



\## 1. Executive Summary



This project assessed login security and authentication controls in a locally hosted OWASP Juice Shop training application.



The assessment examined invalid login responses, account enumeration, repeated login attempts, password validation, unauthenticated profile access, successful authentication, and logout/session behavior.



A suspected information disclosure was observed during unauthenticated profile testing.



\## 2. Scope



\- Application: OWASP Juice Shop

\- Target: http://127.0.0.1:3000

\- Environment: Local Windows testing environment

\- Testing type: Authentication and access-control assessment

\- Authorization: Local training application owned or controlled for testing



\## 3. Tools Used



\- OWASP Juice Shop

\- Google Chrome

\- Windows PowerShell

\- Screenshot evidence



\## 4. Findings



\### Finding 1: Generic Login Error Responses



Severity: Informational



The application displayed the same error message for an incorrect password and an unregistered email address:



"Invalid email or password"



This behavior helps reduce account enumeration through login error messages.



Recommendation:

Continue using generic authentication error messages.



\### Finding 2: No Lockout Observed Within Three Attempts



Severity: Needs Review



Three consecutive failed login attempts did not trigger an account lockout or CAPTCHA.



This limited test does not establish that no rate limiting exists.



Recommendation:

Implement appropriate rate limiting, monitoring, and temporary account protection against repeated login attempts.



\### Finding 3: Weak Password Validation



Severity: Needs Review



The registration form displayed a password length requirement of 5–40 characters. The weak password "123456" was not rejected by the observed form validation.



Recommendation:

Reject common and compromised passwords, enforce an appropriate minimum password length, and provide password-strength guidance.



\### Finding 4: Suspected Unauthenticated Profile Information Disclosure



Severity: Potentially High — Requires Confirmation



During testing in a fresh Incognito session without logging in, the test account's email address remained visible on the profile page.



This suggests a possible access-control issue. However, further investigation is required to determine whether the information is public profile data, cached content, or sensitive information returned by an improperly protected API.



Recommendation:

\- Enforce authorization checks on the server for every private profile endpoint.

\- Ensure private account information is returned only to the authenticated account owner.

\- Verify that logout invalidates the active session or token.

\- Avoid exposing sensitive account information through public endpoints.



\## 5. Test Results Summary



\- AUTH-001: Passed

\- AUTH-002: Passed

\- AUTH-003: Needs Review

\- AUTH-004: Needs Review

\- AUTH-005: Passed

\- AUTH-006: Passed

\- AUTH-007: Suspected Vulnerability



\## 6. Limitations



\- Testing was restricted to a local training application.

\- Account lockout testing covered only three failed attempts.

\- No source-code review was performed.

\- The suspected profile disclosure has not yet been confirmed at API level.

\- Burp Suite was not used during the recorded tests.



\## 7. Conclusion



The assessment identified several authentication behaviors that should be reviewed, particularly weak password validation and possible unauthenticated exposure of profile information.



Further testing is recommended to confirm the suspected access-control issue and evaluate the application's server-side authorization controls.



\## 8. Evidence



Screenshots are stored in the evidence directory of this project.



Project directory:

Project\_04\_Login\_Page\_Penetration\_Testing

