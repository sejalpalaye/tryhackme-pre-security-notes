# DNS in Detail

## What is DNS?
DNS (Domain Name System) translates domain names into IP addresses.
Like a phonebook for the internet — you type a name, DNS finds the number.

> `google.com` → `142.250.180.14`

---

## Domain Hierarchy

```
.com                        ← TLD (Top Level Domain)
google.com                  ← SLD (Second Level Domain)
maps.google.com             ← Subdomain
```

| Part | Example | Description |
|------|---------|-------------|
| TLD | .com, .org, .in | Top level, managed by ICANN |
| SLD | google, tryhackme | The actual domain name |
| Subdomain | maps, mail, www | Prefix before the SLD |

---

## DNS Record Types

| Record | Purpose | Example |
|--------|---------|---------|
| A | Maps domain to IPv4 | google.com → 142.250.180.14 |
| AAAA | Maps domain to IPv6 | google.com → 2607:f8b0::200e |
| CNAME | Alias for another domain | www.google.com → google.com |
| MX | Mail server for domain | google.com → smtp.google.com |
| TXT | Stores text info | Used for verification, SPF records |

---

## DNS Resolution Process

```
1. You type google.com in browser
2. Browser checks local cache
3. Asks Recursive DNS Resolver (your ISP)
4. Resolver asks Root DNS Server
5. Root points to TLD server (.com)
6. TLD points to Authoritative DNS server
7. Authoritative returns the IP
8. Browser connects to that IP
```

---

## DNS Commands

```bash
# Basic DNS lookup
nslookup google.com

# Detailed DNS lookup
dig google.com

# Lookup specific record type
dig google.com MX
dig google.com TXT

# Reverse lookup (IP to domain)
dig -x 142.250.180.14
```
