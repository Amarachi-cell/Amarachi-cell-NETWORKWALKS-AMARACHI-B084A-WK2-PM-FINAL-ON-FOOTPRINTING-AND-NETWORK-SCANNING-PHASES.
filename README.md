# 🛡️ Penetration Testing Report: Footprinting & Network Scanning

A structured penetration testing and security assessment report covering **Phase 1 (Reconnaissance & Footprinting)** and **Phase 2 (Scanning & Network Discovery)**, completed as part of the Networkwalks Cybersecurity Internship Program (Week 2)[span_0](start_span)[span_0](end_span).

---

## ⚠️ Legal & Ethical Disclaimer
> **For Educational & Authorized Research Purposes Only.**  
> All reconnaissance and scanning activities documented in this repository were conducted strictly within authorized boundaries—either against targets with explicit written permission (`networkwalks.com`) or on an isolated, self-owned local area network (LAN)[span_1](start_span)[span_1](end_span). Unauthorized scanning or exploitation of systems without prior consent is illegal[span_2](start_span)[span_2](end_span).

---

## 📋 Project Overview
This project demonstrates the foundational stages of an ethical hacking engagement: moving from passive/active public information gathering to internal live-host discovery and network topology mapping[span_3](start_span)[span_3](end_span). Each phase includes exact command execution, terminal/GUI evidence, risk impact ratings, and actionable remediation steps[span_4](start_span)[span_4](end_span).

### Scope & Phases Covered
* **Phase 1: Reconnaissance & Footprinting** (`W2-PM1`) — External domain enumeration against `networkwalks.com` using Kali Linux[span_5](start_span)[span_5](end_span).
* **Phase 2: Scanning & Network Discovery** (`W2-PM5`) — Internal subnet discovery, MAC/IP mapping, and network topology generation using Zenmap on Windows[span_6](start_span)[span_6](end_span).

---

## 🛠️ Tools & Technologies Used

| Category | Tool | Purpose |
| :--- | :--- | :--- |
| **OS Environment** | Kali Linux & Windows | Operating systems used for external recon and internal scanning[span_7](start_span)[span_7](end_span). |
| **Domain & DNS Recon** | `whois` | Queried domain registration records, registrar details, and name servers[span_8](start_span)[span_8](end_span). |
| **Domain & DNS Recon** | `nslookup` | Resolved target domain to its hosting IPv4 address[span_9](start_span)[span_9](end_span). |
| **Domain & DNS Recon** | `dnsrecon` | Enumerated DNS records (A, NS, MX, SOA, SRV) and checked DNSSEC status[span_10](start_span)[span_10](end_span). |
| **Web Fingerprinting** | `whatweb` | Identified CMS versions (WordPress), plugins, and server technologies[span_11](start_span)[span_11](end_span). |
| **Web Fingerprinting** | `curl -I` | Inspected HTTP response headers, caching rules, and security policies[span_12](start_span)[span_12](end_span). |
| **WAF Detection** | `wafw00f` | Fingerprinted Web Application Firewall protection (ModSecurity)[span_13](start_span)[span_13](end_span). |
| **Network Discovery** | `Zenmap` (Nmap GUI) | Conducted ping sweeps (`nmap -sn`), identified live hosts, and exported network topology[span_14](start_span)[span_14](end_span). |
| **Host Enumeration** | Windows `ipconfig` | Identified local subnet masks, default gateways, and hardware MAC addresses[span_15](start_span)[span_15](end_span). |

---

## 🔍 Key Findings & Risk Summary

The assessment focused strictly on information gathering and host discovery without active exploitation[span_16](start_span)[span_16](end_span):

* **Web Stack & Plugin Exposure (Medium):** Fingerprinting revealed the underlying CMS (WordPress 7.1.4) and active plugins (WP Download Manager 3.3.76), which could aid an attacker in targeting version-specific vulnerabilities[span_17](start_span)[span_17](end_span).
* **DNS & Infrastructure Mapping (Medium):** DNS enumeration mapped the target's public IP (`192.232.216.135`) and noted unsigned DNSSEC / SOA timeout behaviors[span_18](start_span)[span_18](end_span).
* **Internal Network Visibility (Medium):** Ping sweeps across the local `/28` subnet successfully identified active hosts and hardware MAC addresses, highlighting the need for continuous internal device monitoring[span_19](start_span)[span_19](end_span).
* **Security Controls Identified (Low):** HTTP header inspection and WAF fingerprinting confirmed active defensive layers, including HTTPS redirection, HTTP/2, reCAPTCHA/hCaptcha integration, and a ModSecurity (SpiderLabs) WAF[span_20](start_span)[span_20](end_span).

---

## 🛡️ Remediation Highlights
* **Minimize Banner & Version Leakage:** Suppress verbose CMS/plugin version metadata and unnecessary HTTP response headers[span_21](start_span)[span_21](end_span).
* **Patch Management:** Maintain regular update cycles for core web platforms and third-party plugins[span_22](start_span)[span_22](end_span).
* **DNS Hardening:** Audit public DNS records and configure DNSSEC to prevent spoofing and cache poisoning.
* **Network Segmentation & Monitoring:** Conduct periodic internal asset discovery scans to detect unauthorized or rogue devices on the LAN[span_23](start_span)[span_23](end_span).

---

## 👤 Author
**Amarachi Esther Onwenu**  
*Cybersecurity Professional | Batch B084A — Networkwalks*[span_24](start_span)[span_24](end_span)  
* **LinkedIn:** [Amarachi Onwenu](https://www.linkedin.com/in/amarachi-onwenu-aa8b82423)[span_25](start_span)[span_25](end_span)
