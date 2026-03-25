# Day 3 — Internet Addressing & Domain Name System

📖 **Type:** Theory Session
🕐 **Duration:** 2 Hours
📚 **Unit:** 1 — Internet Technology

---

## Learning Objectives

By the end of this session, students will be able to:
- Explain IPv4 and IPv6 addressing schemes
- Classify IP addresses into different classes
- Understand subnet masks and their purpose
- Describe how the Domain Name System (DNS) works
- Differentiate between different types of domain names

---

## 1. IP Addresses

### What is an IP Address?

> **Real-World Analogy:** Just as every house has a unique postal address so the postman knows where to deliver mail, every device on the internet has a unique **IP address** so data packets know where to go.

An **IP Address** (Internet Protocol Address) is a unique numerical label assigned to every device connected to a network that uses the Internet Protocol for communication.

### IPv4 Addresses

**Format:** Four numbers separated by dots, each ranging from 0 to 255.

```
Example: 192.168.1.100

  192    .   168    .    1     .   100
  └─┘        └─┘        └─┘       └─┘
 8 bits    8 bits     8 bits    8 bits
           
           Total = 32 bits
```

**Total IPv4 addresses:** 2³² = **4,294,967,296** (about 4.3 billion)

### IPv4 Address Classes

| Class | Range | Default Subnet Mask | Networks | Hosts per Network | Purpose |
|-------|-------|--------------------|---------|--------------------|---------|
| **A** | 1.0.0.0 – 126.255.255.255 | 255.0.0.0 | 126 | ~16 million | Very large organizations |
| **B** | 128.0.0.0 – 191.255.255.255 | 255.255.0.0 | 16,384 | ~65,000 | Medium organizations |
| **C** | 192.0.0.0 – 223.255.255.255 | 255.255.255.0 | ~2 million | 254 | Small networks |
| **D** | 224.0.0.0 – 239.255.255.255 | — | — | — | Multicasting |
| **E** | 240.0.0.0 – 255.255.255.255 | — | — | — | Experimental/Research |

### Special IP Addresses

| Address | Purpose |
|---------|---------|
| `127.0.0.1` | Loopback (localhost) — your own computer |
| `192.168.x.x` | Private network (home/office Wi-Fi) |
| `10.x.x.x` | Private network (large organizations) |
| `172.16.x.x – 172.31.x.x` | Private network (medium organizations) |
| `0.0.0.0` | Default route / "any address" |
| `255.255.255.255` | Broadcast to all devices on network |

### IPv6 Addresses

> IPv4 only has ~4.3 billion addresses. With billions of phones, laptops, smart TVs, IoT devices — we ran out! IPv6 solves this.

**Format:** Eight groups of four hexadecimal digits, separated by colons.

```
Example: 2001:0db8:85a3:0000:0000:8a2e:0370:7334

Simplified: 2001:db8:85a3::8a2e:370:7334
(Leading zeros dropped, consecutive zero groups replaced with ::)
```

**Total IPv6 addresses:** 2¹²⁸ = approximately 340 undecillion (340 × 10³⁶)

| Feature | IPv4 | IPv6 |
|---------|------|------|
| **Bits** | 32 | 128 |
| **Format** | Decimal (192.168.1.1) | Hexadecimal (2001:db8::1) |
| **Total addresses** | ~4.3 billion | ~340 undecillion |
| **Example** | 192.168.1.1 | 2001:0db8:85a3::7334 |

---

## 2. Subnet Masks

### What is a Subnet Mask?

> **Analogy:** Think of a city with sectors. The city name tells you the general area (network), and the sector number tells you the exact location (host). A **subnet mask** defines where the "city" part ends and the "sector" part begins.

A subnet mask separates an IP address into two parts:
- **Network portion** — identifies which network the device belongs to
- **Host portion** — identifies the specific device on that network

```
IP Address:    192.168.1.100
Subnet Mask:   255.255.255.0
               └────────┘ └─┘
               Network    Host
               
Network ID:    192.168.1.0   (the "street")
Host ID:       100            (the "house number")
```

### Common Subnet Masks

| CIDR Notation | Subnet Mask | Hosts Available |
|--------------|-------------|-----------------|
| /8 | 255.0.0.0 | 16,777,214 |
| /16 | 255.255.0.0 | 65,534 |
| /24 | 255.255.255.0 | 254 |
| /28 | 255.255.255.240 | 14 |

---

## 3. Domain Name System (DNS)

### The Problem

Humans are good at remembering names, computers are good at remembering numbers:
- Human-friendly: `www.google.com`
- Computer-friendly: `142.250.195.68`

### What is DNS?

> **Analogy:** DNS is like a **phone book** for the internet. You know a person's name (domain), and the phone book gives you their number (IP address).

**DNS** (Domain Name System) translates human-readable domain names into IP addresses that computers can understand.

### How DNS Works — Step by Step

```
You type: www.mandsauruniversity.com

Step 1: Browser checks its cache → "Do I already know this?"
            │ No
            ▼
Step 2: OS checks its cache → "Has the computer looked this up before?"
            │ No
            ▼
Step 3: Query goes to Recursive DNS Resolver (your ISP's DNS)
            │ "I don't know, let me ask..."
            ▼
Step 4: Asks Root DNS Server → "Who handles .com?"
            │ "Try the .com TLD server"
            ▼
Step 5: Asks .com TLD Server → "Who handles mandsauruniversity.com?"
            │ "Try ns1.hosting-provider.com"
            ▼
Step 6: Asks Authoritative DNS Server for mandsauruniversity.com
            │ "The IP is 103.45.67.89"
            ▼
Step 7: IP address returned to your browser
            │
            ▼
Step 8: Browser connects to 103.45.67.89 and loads the website!
```

### DNS Record Types

| Record Type | Purpose | Example |
|-------------|---------|---------|
| **A** | Maps domain to IPv4 address | `google.com → 142.250.195.68` |
| **AAAA** | Maps domain to IPv6 address | `google.com → 2404:6800:4009:...` |
| **CNAME** | Alias for another domain | `www.example.com → example.com` |
| **MX** | Mail server for the domain | `example.com → mail.example.com` |
| **NS** | Nameserver for the domain | `example.com → ns1.provider.com` |
| **TXT** | Text records (verification, etc.) | SPF, DKIM records for email |

---

## 4. Domain Names

### Structure of a Domain Name

```
    https://www.mandsauruniversity.edu.in/admissions
    └─┬──┘ └┬┘ └───────┬──────────┘└┬─┘└┬┘ └────┬───┘
   Scheme  Sub  Second-Level Domain TLD ccTLD  Path
          domain                          
```

| Part | Example | Purpose |
|------|---------|---------|
| **Scheme/Protocol** | `https://` | How to communicate |
| **Subdomain** | `www` | Specific service of the domain |
| **Second-Level Domain** | `mandsauruniversity` | The actual name you registered |
| **TLD** (Top-Level Domain) | `.edu` | Category of the website |
| **ccTLD** (Country Code) | `.in` | Country (India) |

### Types of Top-Level Domains (TLDs)

| Type | Examples | Purpose |
|------|----------|---------|
| **gTLD** (Generic) | .com, .org, .net | General purpose |
| **ccTLD** (Country Code) | .in (India), .uk (UK), .jp (Japan) | Country-specific |
| **sTLD** (Sponsored) | .edu (education), .gov (government) | Specific communities |
| **New gTLDs** | .tech, .xyz, .ai, .io | Modern/niche purposes |

### Domain Registration

Domains are registered through **domain registrars** like:
- GoDaddy
- Namecheap
- Google Domains
- Hostinger

**ICANN** (Internet Corporation for Assigned Names and Numbers) manages the global DNS system.

---

## 5. Public vs Private IP Addresses

| Feature | Public IP | Private IP |
|---------|-----------|------------|
| **Scope** | Globally unique, accessible from anywhere | Unique within local network only |
| **Assigned by** | ISP | Router (via DHCP) |
| **Example** | 203.110.245.34 | 192.168.1.100 |
| **Analogy** | Your building's street address | Your apartment number inside the building |

### NAT (Network Address Translation)

> **Analogy:** A company has one phone number (public IP), but many extensions inside (private IPs). When someone calls, the receptionist (NAT) routes the call to the right extension.

NAT allows multiple devices on a private network to share a single public IP address.

---

## Summary

| Concept | Key Takeaway |
|---------|-------------|
| IPv4 | 32-bit address, ~4.3 billion addresses |
| IPv6 | 128-bit address, virtually unlimited |
| Subnet Mask | Divides IP into network and host parts |
| DNS | Translates domain names to IP addresses |
| Domain Names | Structured hierarchy: subdomain.domain.TLD |
| Public vs Private IP | Public = globally unique; Private = local network |

---

## Self-Assessment Questions

1. Convert the class of these IP addresses: 10.0.0.1, 172.16.5.3, 192.168.1.1
2. What is the purpose of a subnet mask? Explain with an example.
3. Trace the DNS resolution process when you type `www.facebook.com` in your browser.
4. What is the difference between IPv4 and IPv6?
5. Explain the difference between gTLD and ccTLD with examples.
6. Why do we need NAT?

---

## Reading for Next Session

Tomorrow we study the **World Wide Web** — the system built ON TOP of the internet that lets us browse websites, access content, and interact with web applications.

---

*Day 3 of 55 | Unit 1 — Internet Technology | Web Technology (25BCA060)*
