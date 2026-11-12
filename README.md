
# Website Information Gathering & Reconnaissance

## Objective
To perform passive and basic active reconnaissance on a target domain using Kali Linux tools. The objective is to gather domain information, identify DNS records, analyze web technologies, inspect HTTP headers, and detect Web Application Firewall (WAF) protection.

**Target Domain:** `networkwalks.com`

---

## Step 1: WHOIS Lookup

**Tool:** WHOIS

**Command:**
```bash
whois networkwalks.com
```

**Description:**

Performed a WHOIS lookup to collect domain registration information, registrar details, domain creation and expiry dates, name servers, and domain status.

**Key Information Collected:**
- Domain registrar: GoDaddy
- Domain creation and expiry dates
- Name servers
- Domain status
- DNSSEC information

**Screenshot:**

![WHOIS Lookup](images/01-whois.png)

---

## Step 2: DNS Lookup

**Tool:** NSLookup

**Command:**
```bash
nslookup networkwalks.com
```

**Description:**

Used NSLookup to resolve the target domain name into its corresponding IP address through the configured DNS server.

**Key Findings:**
- DNS Server: `192.168.13.2`
- Resolved IP Address: `192.232.216.135`
- Successfully retrieved the DNS resolution response.

**Screenshot:**

![DNS Lookup](images/02-nslookup.png)

---

## Step 3: Website Technology Identification

**Tool:** WhatWeb

**Command:**
```bash
whatweb networkwalks.com
```

**Description:**

Used WhatWeb to identify the technologies and frameworks running on the target website.

**Key Findings:**
- Web Server: Apache
- CMS: WordPress
- WordPress Version: 7.1.4 (as reported by the tool)
- JavaScript Library: jQuery 3.7.1
- Framework: Bootstrap 7.1.4 (as reported by the tool)
- Website Title: NetworkWalks Academy

**Screenshot:**

![WhatWeb Scan](images/03-whatweb.png)

---

## Step 4: HTTP Header Analysis

**Tool:** cURL

**Command:**
```bash
curl -I https://networkwalks.com
```

**Description:**

Used cURL to send an HTTP HEAD request and inspect the server response headers.

**Key Findings:**
- HTTP Status: `200 OK`
- Web Server: Apache
- Content-Type: text/html
- Security-related headers and cookie attributes were observed.
- WordPress-related HTTP response headers were identified.

**Screenshot:**

![HTTP Header Analysis](images/04-curl.png)

---

## Step 5: Web Application Firewall Detection

**Tool:** WAFW00F

**Command:**
```bash
wafw00f networkwalks.com
```

**Description:**

Used WAFW00F to identify whether the target website is protected by a Web Application Firewall (WAF).

**Key Findings:**
- WAF Detection: Positive
- Identified WAF: ModSecurity (SpiderLabs)
- Number of Requests: 2

**Screenshot:**

![WAF Detection](images/05-wafw00f.png)

---

## Step 6: DNS Enumeration

**Tool:** DNSRecon

**Command:**
```bash
dnsrecon -d networkwalks.com
```

**Description:**

Performed DNS enumeration to identify publicly available DNS records associated with the target domain.

**Key Findings:**
- Identified SOA records.
- Retrieved NS (Name Server) records.
- Identified A records.
- Retrieved MX (Mail Exchange) records.
- Identified TXT records.
- Enumerated SRV records.
- Total records reported: 8.

**Screenshot:**

![DNS Enumeration](images/06-dnsrecon.png)

---

## Conclusion

Successfully completed the website reconnaissance process using Kali Linux.

The practical exercise covered:

1. Domain registration information gathering using WHOIS.
2. DNS resolution using NSLookup.
3. Website technology identification using WhatWeb.
4. HTTP response header analysis using cURL.
5. Web Application Firewall detection using WAFW00F.
6. DNS record enumeration using DNSRecon.

These reconnaissance techniques help security professionals understand a website's publicly exposed infrastructure and identify information that may be useful during an authorized security assessment.

---

**Environment:** Kali Linux  
**Tools Used:** WHOIS, NSLookup, WhatWeb, cURL, WAFW00F, DNSRecon  
**Category:** Cybersecurity | Information Gathering | Reconnaissance
