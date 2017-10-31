# A2:2017 Broken Authentication

| Threat agents/Attack vectors | Security Weakness           | Impacts               |
| -- | -- | -- |
| Access Lvl \| Exploitability 3 | Prevalence 2 \| Detectability 2 | Technical 3 \| Business |
| Attackers have access to hundreds of millions of valid username and password combinations for credential stuffing, default administrative account lists, automated brute force and dictionary attack tools, and advanced GPU cracking tools.  | The prevalence of broken authentication is widespread due to the design and implementation of most identity and access management systems. Attackers can detect broken authentication using manual means, but are often attracted by password dumps, or after a social engineering attack such as phishing or similar. | Attackers only have to gain access to a few accounts, or just one admin  account to compromise the system. Depending on the domain of the app, this may allow money laundering social security fraud and identity theft; or disclose legally protected highly sensitive information. |

## Am I Vulnerable to Broken Auth?

Confirmation of the user's identity, authentication, and session management are critical for separating malicious unauthenticated attackers from authorized users.
You may have authentication weaknesses if your application:

* Permits [credential stuffing](https://www.owasp.org/index.php/Credential_stuffing), which is where the attacker has a list of valid usernames and passwords.
* Permits brute force or other automated attacks.
* Permits default, weak or well-known passwords, such as "Password1" or "admin/admin“.
* Uses weak or ineffectual credential recovery and forgot password processes, such as "knowledge-based answers", which cannot be made safe.
* Uses plain text, encrypted, or weakly hashed passwords permit the rapid recovery of passwords using GPU crackers or brute force tools.
* Has missing or ineffective multi-factor authentication.

## How Do I Prevent This?

* Do not ship or deploy with any default credentials, particularly for admin users
* [Store passwords using a modern one way hash function](https://www.owasp.org/index.php/Password_Storage_Cheat_Sheet#Leverage_an_adaptive_one-way_function), such as Argon2 or PBKDF2, with sufficient work factor to prevent realistic GPU cracking attacks.
* Implement weak password checks, such as testing new or changed passwords against a list of the [top 10000 worst passwords](https://github.com/danielmiessler/SecLists/tree/master/Passwords).
* Align password length, complexity and rotation policies with [NIST 800-63 B's guidelines in section 5.1.1 for Memorized Secrets](https://pages.nist.gov/800-63-3/sp800-63b.html#memsecret) or other modern, evidence based password policies
* Ensure registration, credential recovery, and API pathways are hardened against account enumeration attacks by using the same messages for all outcomes
* Where possible, implement multi-factor authentication to prevent credential stuffing, brute force, automated, and stolen credential attacks
* Log authentication failures and alert administrators when credential stuffing, brute force, other attacks are detected.

## Example Attack Scenarios

**Scenario #1**: [credential stuffing](https://www.owasp.org/index.php/Credential_stuffing), the use of [lists of known passwords](https://github.com/danielmiessler/SecLists), is a common attack. If an application does not rate limit authentication attempts, the application can be used as a password oracle to determine if the credentials are valid.

**Scenario #2**: Most authentication attacks occur due to the continued use of passwords as a sole factor. Once considered best practices, password rotation and complexity requirements are viewed as encouraging users to use, and reuse, weak passwords. Organizations are recommended to stop these practices per NIST 800-63 and use multi-factor authentication.

**Scenario #3**: Insecure password storage (including plain text, reversibly encrypted passwords, and weakly hashed passwords (such as using MD5/SHA1 with or without a salt) can lead to breaches. A recent effort by a small group of researchers cracked [320 million passwords in less than three weeks](https://cynosureprime.blogspot.com.au/2017/08/320-million-hashes-exposed.html), including long passwords. Instead use modern hashing algorithms such as Argon2, with salting and sufficient work factor to prevent the use of rainbow tables, word lists, etc.

## References

### OWASP

* [OWASP Proactive Controls - Implement Identity and Authentication Controls]((https://www.owasp.org/index.php/OWASP_Proactive_Controls#5:_Implement_Identity_and_Authentication_Controls))
* [OWASP Application Security Verification Standard V2 Authentication](https://www.owasp.org/index.php/Category:OWASP_Application_Security_Verification_Standard_Project#tab=Home)
* [OWASP Application Security Verification Standard V3 Session Management](https://www.owasp.org/index.php/Category:OWASP_Application_Security_Verification_Standard_Project#tab=Home)
* [OWASP Testing Guide: Identity](https://www.owasp.org/index.php/Testing_Identity_Management)
 and [Authentication](https://www.owasp.org/index.php/Testing_for_authentication)
* [OWASP Authentication Cheat Sheet](https://www.owasp.org/index.php/Authentication_Cheat_Sheet)
* [OWASP Credential Stuffing Cheat Sheet](https://www.owasp.org/index.php/Credential_Stuffing_Prevention_Cheat_Sheet)
* [OWASP Forgot Password Cheat Sheet](https://www.owasp.org/index.php/Forgot_Password_Cheat_Sheet)
* [OWASP Password Storage Cheat Sheet](https://www.owasp.org/index.php/Password_Storage_Cheat_Sheet)
* [OWASP Session Management Cheat Sheet](https://www.owasp.org/index.php/Session_Management_Cheat_Sheet)

### External

* [NIST 800-63b 5.1.1 Memorized Secrets – for thorough, modern, evidence based advice on authentication.](https://pages.nist.gov/800-63-3/sp800-63b.html#memsecret)
* [CWE-287 Improper Authentication](https://cwe.mitre.org/data/definitions/287.html)
* [CWE-384 Session Fixation](https://cwe.mitre.org/data/definitions/384.html)
