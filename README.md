# 🛡️ Penetration Testing Report: Footprinting & Network Scanning

A structured penetration testing and security assessment report covering **Phase 1 (Reconnaissance & Footprinting)** and **Phase 2 (Scanning & Network Discovery)**, completed as part of the Networkwalks Cybersecurity Internship Program (Week 2).

---

## ⚠️ Legal & Ethical Disclaimer
> **For Educational & Authorized Research Purposes Only.**  
> All reconnaissance and scanning activities documented in this repository were conducted strictly within authorized boundaries—either against targets with explicit written permission (`networkwalks.com`) or on an isolated, self-owned local area network (LAN). Unauthorized scanning or exploitation of systems without prior consent is illegal.

---

## 📋 Project Overview
This project demonstrates the foundational stages of an ethical hacking engagement: moving from passive/active public information gathering to internal live-host discovery and network topology mapping Each phase includes exact command execution, terminal/GUI evidence, risk impact ratings, and actionable remediation steps.

### Scope & Phases Covered
* **Phase 1: Reconnaissance & Footprinting** (`W2-PM1`) — External domain enumeration against `networkwalks.com` using Kali Linux.
* **Phase 2: Scanning & Network Discovery** (`W2-PM5`) — Internal subnet discovery, MAC/IP mapping, and network topology generation using Zenmap on Windows.

---

## 🛠️ Tools & Technologies Used

| Category | Tool | Purpose |
| :--- | :--- | :--- |
| **OS Environment** | Kali Linux & Windows | Operating systems used for external recon and internal scanning |
| **Domain & DNS Recon** | `whois` | Queried domain registration records, registrar details, and name servers. |
| **Domain & DNS Recon** | `nslookup` | Resolved target domain to its hosting IPv4 address). |
| **Domain & DNS Recon** | `dnsrecon` | Enumerated DNS records (A, NS, MX, SOA, SRV) and checked DNSSEC status. |
| **Web Fingerprinting** | `whatweb` | Identified CMS versions (WordPress), plugins, and server technologies. |
| **Web Fingerprinting** | `curl -I` | Inspected HTTP response headers, caching rules, and security policies. |
| **WAF Detection** | `wafw00f` | Fingerprinted Web Application Firewall protection (ModSecurity). |
| **Network Discovery** | `Zenmap` (Nmap GUI) | Conducted ping sweeps (`nmap -sn`), identified live hosts, and exported network topology. |
| **Host Enumeration** | Windows `ipconfig` | Identified local subnet masks, default gateways, and hardware MAC addresses. |

---

## 🔍 Key Findings & Risk Summary

The assessment focused strictly on information gathering and host discovery without active exploitation:

* **Web Stack & Plugin Exposure (Medium):** Fingerprinting revealed the underlying CMS (WordPress 7.1.4) and active plugins (WP Download Manager 3.3.76), which could aid an attacker in targeting version-specific vulnerabilities.
* **DNS & Infrastructure Mapping (Medium):** DNS enumeration mapped the target's public IP (`192.232.216.135`) and noted unsigned DNSSEC / SOA timeout behaviors.
* **Internal Network Visibility (Medium):** Ping sweeps across the local `/28` subnet successfully identified active hosts and hardware MAC addresses, highlighting the need for continuous internal device monitoring.
* **Security Controls Identified (Low):** HTTP header inspection and WAF fingerprinting confirmed active defensive layers, including HTTPS redirection, HTTP/2, reCAPTCHA/hCaptcha integration, and a ModSecurity (SpiderLabs) WAF.

---

## 🛡️ Remediation Highlights
* **Minimize Banner & Version Leakage:** Suppress verbose CMS/plugin version metadata and unnecessary HTTP response headers.
* **Patch Management:** Maintain regular update cycles for core web platforms and third-party plugins.
* **DNS Hardening:** Audit public DNS records and configure DNSSEC to prevent spoofing and cache poisoning.
* **Network Segmentation & Monitoring:** Conduct periodic internal asset discovery scans to detect unauthorized or rogue devices on the LAN.

---

## 👤 Author
**Amarachi Esther Onwenu**  
*Cybersecurity Professional | Batch B084A — Networkwalks*  
* **LinkedIn:** [Amarachi Onwenu](https://www.linkedin.com/in/amarachi-onwenu-aa8b82423)
