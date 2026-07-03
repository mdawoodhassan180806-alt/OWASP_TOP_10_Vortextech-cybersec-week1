# OWASP Top 10 Research Report – Week 1

**Name:*** Muhammad Dawood Hassan*
**Track:** Cyber Security
**Assignment:** OWASP Top 10 Research

---

# Introduction

The OWASP Top 10 is a globally recognized list of the most critical security risks affecting web applications. It is maintained by the Open Worldwide Application Security Project (OWASP) and helps developers, security professionals, and organizations understand the most common vulnerabilities and how to prevent them. This report explains five important vulnerabilities from the current OWASP Top 10 in simple language.

---

# 1. Broken Access Control

## What is it?

Broken Access Control happens when a web application does not properly restrict what users are allowed to do. A normal user may be able to access data or features that should only be available to administrators or other users.

## How an attacker could exploit it

An attacker might simply change the URL or modify a request to access another user's account or confidential information. For example, changing:

```
/profile?id=101
```

to

```
/profile?id=102
```

could reveal another user's profile if the application does not verify permissions.

## Real-world example

In 2021, the social media platform Facebook experienced vulnerabilities where researchers demonstrated that improper access controls could expose private user information. Similar Broken Access Control issues are frequently found during bug bounty programs and penetration tests.

## Prevention

* Verify user permissions on every request.
* Use role-based access control (RBAC).
* Follow the principle of least privilege.
* Never rely only on hidden buttons or client-side validation.

---

# 2. Cryptographic Failures

## What is it?

Cryptographic Failures occur when sensitive information is not properly protected using encryption. This can expose passwords, payment information, and personal data.

## How an attacker could exploit it

If a website stores passwords as plain text or sends sensitive information without HTTPS, an attacker who intercepts the data can read it easily.

## Real-world example

The Equifax data breach (2017) exposed personal information of approximately 147 million people. While the breach involved multiple security failures, poor protection of sensitive data greatly increased its impact.

## Prevention

* Always use HTTPS/TLS.
* Encrypt sensitive information both during transmission and storage.
* Store passwords using strong hashing algorithms such as bcrypt or Argon2.
* Remove unnecessary sensitive data from databases.

---

# 3. Injection

## What is it?

Injection vulnerabilities happen when an application accepts user input without properly checking it. Attackers can trick the application into executing unintended commands or database queries.

SQL Injection is one of the most common examples.

## How an attacker could exploit it

Suppose a login form asks for a username and password. If the application directly inserts user input into a SQL query, an attacker may enter malicious SQL commands that bypass authentication or retrieve database records.

## Real-world example

The 2017 Equifax breach began with another vulnerability, but many major organizations have suffered SQL Injection attacks over the years. Sony Pictures and Heartland Payment Systems also experienced attacks involving SQL Injection.

## Prevention

* Use parameterized queries (prepared statements).
* Validate and sanitize all user input.
* Avoid building SQL queries using string concatenation.
* Apply the principle of least privilege to database accounts.

---

# 4. Insecure Design

## What is it?

Insecure Design refers to security weaknesses caused by poor planning or architecture rather than programming mistakes. Even perfectly written code can be insecure if the overall design ignores security.

## How an attacker could exploit it

If an online banking system allows unlimited password reset attempts without verification, attackers can repeatedly try to guess reset codes or abuse the recovery process.

## Real-world example

Many online services have experienced account takeover attacks because password reset mechanisms were designed without sufficient security controls.

## Prevention

* Consider security during the design phase.
* Perform threat modeling before development.
* Apply secure design principles.
* Review business logic for possible abuse.

---

# 5. Security Misconfiguration

## What is it?

Security Misconfiguration occurs when applications, servers, or cloud services are set up incorrectly, leaving systems exposed to attackers.

Examples include default passwords, unnecessary services, exposed error messages, or publicly accessible storage.

## How an attacker could exploit it

An attacker scans websites looking for default administrator accounts, exposed configuration files, or cloud storage that has been left public.

## Real-world example

Numerous companies have accidentally exposed millions of customer records because cloud storage buckets were configured for public access instead of private access.

## Prevention

* Remove default usernames and passwords.
* Disable unnecessary features and services.
* Keep software updated.
* Regularly review security settings.
* Perform configuration audits.

---

# Personal Reflection

The vulnerability that surprised me the most was **Insecure Design**. I originally thought most cyberattacks happened because programmers made coding mistakes, but I learned that poor planning can create security problems even when the code itself is correct. This showed me that security should be considered from the beginning of software development instead of being added later. Understanding secure design principles seems just as important as learning secure coding techniques.

---

# References

1. OWASP Foundation. *OWASP Top 10: The Ten Most Critical Web Application Security Risks.*
2. OWASP Cheat Sheet Series.
3. Equifax Data Breach Reports (2017).
4. National Institute of Standards and Technology (NIST) Cybersecurity Resources.
