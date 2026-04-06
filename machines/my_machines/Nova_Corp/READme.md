# NovaCorp Vulnerable Lab

A realistic intentionally vulnerable web application
environment for penetration testing practice and
security education.

> Built by Laziz Ilyosov — cybersecurity student from
> Tashkent, Uzbekistan. Student at HAAD TC.

---

## What is this?

NovaCorp Technologies is a fictional corporate web
environment designed for learning web application
security through hands-on practice.

This is NOT a CTF machine. There are no flags to
capture. Every vulnerability is embedded naturally
into the application logic — exactly as it would
appear in a real corporate penetration test.

The goal is to teach beginners what real web
vulnerabilities look like and how to find them.

---

## Lab specs

| Detail | Value |
|--------|-------|
| OS | Ubuntu 24.04 LTS |
| Web server | Nginx 1.24 |
| Backend | PHP 8.3 + Python Flask |
| Database | MySQL 8.0 + SQLite3 |
| Format | OVA (VirtualBox / VMware) |
| IP address | 192.168.56.103 |
| Total subdomains | 11 (main + 10) |
| Total vulnerabilities | 15 |

---

## The 11 subdomains

| # | Subdomain | Purpose |
|---|-----------|---------|
| 0 | novacorp.local | Corporate homepage |
| 1 | shop.novacorp.local | E-commerce store |
| 2 | blog.novacorp.local | Corporate blog |
| 3 | mail.novacorp.local | Webmail client |
| 4 | dev.novacorp.local | Developer portal |
| 5 | api.novacorp.local | Internal REST API |
| 6 | admin.novacorp.local | Admin control panel |
| 7 | portal.novacorp.local | Customer portal |
| 8 | support.novacorp.local | Support tickets |
| 9 | files.novacorp.local | File sharing |
| 10 | status.novacorp.local | System status |

---

## Vulnerability overview

| # | Vulnerability | Subdomain | Severity |
|---|--------------|-----------|----------|
| 1 | Reflected XSS | novacorp.local | Medium |
| 2 | SQL Injection | shop.novacorp.local | Critical |
| 3 | No Rate Limiting | shop.novacorp.local | Low |
| 4 | IDOR | blog.novacorp.local | Medium |
| 5 | Stored XSS | mail.novacorp.local | High |
| 6 | LFI | dev.novacorp.local | Critical |
| 7 | Sensitive Data Exposure | dev.novacorp.local | High |
| 8 | BOLA | api.novacorp.local | High |
| 9 | Command Injection | api.novacorp.local | Critical |
| 10 | Default Credentials | admin.novacorp.local | High |
| 11 | Broken Auth (Session) | portal.novacorp.local | High |
| 12 | CSRF | portal.novacorp.local | High |
| 13 | Open Redirect | novacorp.local | Medium |
| 14 | XXE Injection | api.novacorp.local | High |
| 15 | File Upload → RCE | files.novacorp.local | Critical |

**Severity breakdown: 4 Critical — 6 High — 4 Medium — 1 Low**

---

## Setup instructions

### Step 1 — Import OVA
Download the OVA file from Releases.
Import into VirtualBox: File → Import Appliance.
Set network adapter to Host-Only (vboxnet0).
Start the VM.

### Step 2 — Add to your hosts file
On your Kali Linux or attacking machine:

```bash
sudo nano /etc/hosts
```

Add these lines:
```
192.168.56.103  novacorp.local
192.168.56.103  shop.novacorp.local
192.168.56.103  blog.novacorp.local
192.168.56.103  mail.novacorp.local
192.168.56.103  dev.novacorp.local
192.168.56.103  api.novacorp.local
192.168.56.103  admin.novacorp.local
192.168.56.103  portal.novacorp.local
192.168.56.103  support.novacorp.local
192.168.56.103  files.novacorp.local
192.168.56.103  status.novacorp.local
```

### Step 3 — Start hacking
Open your browser and navigate to:
http://novacorp.local

Enumerate the subdomains, find the vulnerabilities,
and document your findings like a real pentest report.

---

## Recommended tools

- Reconnaissance: nmap, gobuster, ffuf
- Web testing: Burp Suite, OWASP ZAP
- Exploitation: sqlmap, curl, Python scripts
- Documentation: your own pentest report template

---

## Blog series

I am documenting each vulnerability with a full
explanation post on my blog. New posts published weekly.

Read the full series: 

---

## Disclaimer

This lab is for educational purposes only.
All vulnerabilities are intentional and contained
within an isolated virtual machine environment.
Never test these techniques on systems you do not
own or have explicit written permission to test.

---

## About the author

Laziz Ilyosov
Cybersecurity student — HAAD TC, Tashkent, Uzbekistan
CJCA certified (100/100) | Web RTA | Red-0

Blog: https://hashnode.com/@lazicoxy
LinkedIn: linkedin.com/in/lazizbek-i-9bb54939a
HackTheBox: https://profile.hackthebox.com/profile/019c38bd-9b69-7364-86f1-eb0beb7d48ff
