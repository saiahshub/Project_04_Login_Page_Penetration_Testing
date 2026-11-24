\# Project 04: Login Page Penetration Testing



\## Test Case Matrix



| Test ID | Test Description | Expected Result | Observed Result | Status |

|---|---|---|---|---|

| AUTH-001 | Login with valid email and incorrect password | Login should be rejected with a generic error | Displayed "Invalid email or password" | Passed |

| AUTH-002 | Login using an unregistered email | Login should be rejected without revealing account existence | Same generic error displayed | Passed |

| AUTH-003 | Three consecutive failed login attempts | Security controls should restrict repeated attempts | No lockout or CAPTCHA observed within three attempts | Needs Review |

| AUTH-004 | Test weak password validation | Weak passwords should be rejected | Password 123456 was accepted by the observed form validation | Needs Review |

| AUTH-005 | Access profile without authentication | Private profile information should be inaccessible | Profile access was initially blocked | Passed |

| AUTH-006 | Login with valid credentials | User should successfully authenticate | Login successful | Passed |

| AUTH-007 | Access profile in a fresh logged-out session | Private account information should not be visible | Test account email remained visible in fresh Incognito session | Suspected Vulnerability |



\## Evidence



1\. 01\_Invalid\_Login\_Response.png

2\. 02\_Account\_Enumeration\_Test.png

3\. 03\_Account\_Lockout\_Test.png

4\. 04\_Unauthenticated\_Access\_Test.png

5\. 05\_Valid\_Authentication.png

6\. 06\_Profile\_Visible\_Without\_Login.png

7\. 07\_Unauthenticated\_Profile\_Data\_Exposure.png



\## Important Notes



\- Testing was performed on a local OWASP Juice Shop training application.

\- Account lockout conclusions are limited to three failed attempts.

\- AUTH-007 requires further investigation to establish whether the exposed email is retrieved from a protected API or displayed from publicly accessible data.

\- No real user accounts or external systems were tested.s

