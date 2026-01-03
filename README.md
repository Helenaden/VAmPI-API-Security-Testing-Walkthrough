# VAmPI-API-Security-Testing-Walkthrough

This repository is a practical, hands-on walkthrough of **VAmPI (Vulnerable API)**. Here's the [Step-by-step walkthrough on Medium](https://medium.com/@peacedennis/vampi-api-security-testing-walkthrough-ee9811f9494b).
It shows how common API security issues actually look in the real world, and how they can be chained together to fully compromise an application.

I walked through the API starting with no access, gathering information, and gradually escalating privileges.

If you’re interested in API security, penetration testing, or the OWASP API Top 10, this repo is for you. Don't forget to use the Medium link above to see the step by step guide.


## What You’ll Find

Each section explains **what the issue is**, **how it’s exploited**, and **why it matters**.

### Unauthenticated Issues
 
- Broken authentication logic
- Username and password enumeration     
- Excessive data exposure via debug endpoints
- Mass Assignment
- SQL injection leading to full database disclosure
- Lack of Resource Limits & Rate Limiting  

### Authenticated Issues

- Broken Object Level Authorization (BOLA)
- Unauthorized Password Change  
- JWT Authentication Bypass via Weak Signing Key 
- ReDoS (Regular Expression Denial of Service)

All of these are mapped back to real-world API security failures.

---

## How the Lab Is Set Up

The environment uses **Docker Compose** to run two versions of the API:

- **Secure API** → `http://127.0.0.1:5001`  
- **Vulnerable API** → `http://127.0.0.1:5002`  

All testing is done against the vulnerable instance.

### Tools Used

- **Postman** – for exploring and testing endpoints  
- **Burp Suite** – for intercepting, modifying, and brute-forcing requests  
- **sqlmap** – for automated SQL injection exploitation  
- **jwttool** – for cracking and forging JWTs  

---

## Getting Started

Here is how to run this locally:

```bash
git clone https://github.com/erev0s/VAmPI
cd VAmPI
docker-compose up -d
```

## Once it’s running:

- Use http://127.0.0.1:5002 as the base URL
- Import the Postman collection or OpenAPI spec from the openapi_specs folder
- Start testing and following along with the walkthrough on my Medium page. [Step-by-step walkthrough on Medium](https://medium.com/@peacedennis/vampi-api-security-testing-walkthrough-ee9811f9494b)

## Why This Project Exists

APIs are everywhere, and they’re often over-trusted.

This project shows how:

- Authentication doesn’t mean authorization
- Tokens don’t protect data if ownership isn’t enforced
- Debug endpoints can destroy security
- Weak crypto breaks everything built on top of it

More than anything, this repo focuses on attacker thinking: how small issues combine into serious compromises.

## Who This Is For

- Anyone learning API security
- Pentesters and bug bounty beginners
- Developers who want to understand how APIs fail

## Disclaimer

This project is for educational purposes only.  
VAmPI is intentionally vulnerable and designed for learning.  
Do not use these techniques on systems you don’t own or have permission to test.

## Final Thoughts

If you’re serious about API security, the best way to learn is to break things, and understand why they broke. That’s what this project is about.

Thanks for checking out the repo.  
If you have questions, feedback, or want to talk API security, feel free to reach out.

