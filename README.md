\# Project 04: Login Page Penetration Testing



\## Overview



A beginner-friendly authentication security assessment using the OWASP Juice Shop training application.



\## Objectives



\- Test invalid login responses.

\- Check for account enumeration.

\- Examine account lockout behavior.

\- Evaluate password validation.

\- Test unauthenticated profile access.

\- Verify successful authentication.

\- Examine logout and session behavior.



\## Environment



\- Windows 11

\- OWASP Juice Shop

\- Google Chrome

\- PowerShell



\## Target



`http://127.0.0.1:3000`



\## Project Structure



```text

Project\_04\_Login\_Page\_Penetration\_Testing/

│

├── README.md

├── test\_cases/

│   └── test\_case\_matrix.md

│

├── evidence/

│   ├── 01\_Invalid\_Login\_Response.png

│   ├── 02\_Account\_Enumeration\_Test.png

│   ├── 03\_Account\_Lockout\_Test.png

│   ├── 04\_Unauthenticated\_Access\_Test.png

│   ├── 05\_Valid\_Authentication.png

│   ├── 06\_Profile\_Visible\_Without\_Login.png

│   └── 07\_Unauthenticated\_Profile\_Data\_Exposure.png

│

└── reports/

&#x20;   └── assessment\_report.md

```



\## Key Observations



\- Generic login errors were observed.

\- No lockout was observed within three failed attempts.

\- Weak password validation needs improvement.

\- A possible unauthenticated profile information disclosure requires further investigation.



\## Deliverables



\- Authentication test case matrix

\- Assessment report

\- Screenshot evidence

\- Security recommendations



\## Disclaimer



This project was conducted on a locally hosted OWASP Juice Shop training application for educational purposes.

