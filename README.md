# Pentesting-Report
### Footprinting & Network Scanning Phases

**W2-PM-FINAL  |  CYBERSECURITY  |  NETWORKWALKS**

| Field | Detail |
|---|---|
| **Pentester Name (Cybersecurity Professional)** | **Sandy** |
| **Program/Batch** | B083-Networkwalks |
| **Date** | 18 September 2026 |
| **Modules completed** | W2-PM1 (Multiple Kali Tools)<br>W2-PM4 (theHARVESTER)<br>W2-PM5 (Zenmap Scanning) |
| **Client/Target** | 1. Networkwalks (secured written permission already)<br>2. Microsoft (public source)<br>3. My own local LAN Network |
| **Permission secured from client?** | Yes |
| **Phases covered** | **Phase 1 & 2:** Reconnaissance & Footprinting<br>**Phase 3:** Scanning & Network Discovery |

# 1. Liability Disclaimer

I have performed these activities only on the systems & devices where I had secured written permission or the devices/systems that I own myself. All these materials are for education and research purpose only. Do not use anything from here to break the law. The instructor, the authors and Networkwalks are not responsible for what you do with this knowledge. Every action you take is your own responsibility. Misuse can lead to criminal charges, heavy fines, loss of your job and a permanent record. In most countries unauthorised access is a crime even when nothing is damaged.

# 2. Introduction

This report covers the cybersecurity activities completed during Week 2 of my ongoing internship program at NetworkWalks, including W2-PM1 (Footprinting), W2-PM4 (Footprinting & Reconnaissance with theHarvester), and W2-PM5 (Network Scanning with Zenmap).

The activities involve finding out what information about a target is publicly available, and finding out if there are live machines on my local network. The footprinting and reconnaissance has been done from Kali Linux environment, and the network scanning has been done from my Windows Desktop using Zenmap. Every step has the command used with the result observed and provides a screenshot showing the result and gives a short explanation of why it is relevant from a cybersecurity perspective. All commands were run in Kali Linux (footprinting) and on a Windows PC with Zenmap installed (scanning). Every step below includes the exact command used, the result I observed, a screenshot as evidence, and a short note on why the finding matters from an attacker's point of view.

# 3. Tools Used

The table below lists each tool used in this report and its purpose.

| Tool | Purpose |
|---|---|
| Kali Linux & Windows | Operating systems used for reconnaissance activities.                                        |
| WHOIS                | Domain registration and name server information (owner, dates, name servers).               |
| whatweb              | Identifies technologies and software used by a website (servers, CMS, plugins, IP).        |
| nslookup             | Resolves domain names into IP addresses using DNS.                                           |
| curl -I              | Display HTTP response headers to observe information.                                        |
| wafw00f              | Detects whether a website is protected by a Web Application Firewall.               |
| dnsrecon             | Enumerate all DNS records (NS, MX, SPF, TXT, SRV).                                           |
| theHarvester - baidu | Public information gathering using Baidu.                                                    |
| theHarvester - all   | Public information gathering from multiple sources.                                          |
| Zenmap (Nmap GUI)    | Scan the local subnet to find live hosts, IPs, and MAC addresses.                          |
| Windows CMD          | Local IP and MAC address identification.                                                     |

# 4. Activities Performed

## 4.1 Footprinting & Reconnaissance

I performed reconnaissance on the 'networkwalks.com' domain using six Kali Linux tools: WHOIS, WhatWeb, Nslookup, Curl, Wafw00f, and DNSRecon. Each tool provided different information about the target.
With WHOIS, I observed publicly available domain registration details and the domain’s name servers. Using WhatWeb, I observed that the website was running WordPress 7.0.4 and WP Download Manager 3.3.58, along with other exposed technologies.
With Nslookup, I observed that networkwalks.com resolved to the IP address 192.232.216.135. Using Curl with the -I option, I observed HTTP response headers and the exposed /wp-json/ WordPress REST API endpoint.
With Wafw00f, I observed that the website was protected by ModSecurity (SpiderLabs). Finally, DNSRecon showed DNS information including name servers, mail servers, SPF/TXT records, service records, and DNS software information.

## 4.2 Footprinting & Reconnaissance with theHARVESTER

I used theHarvester in Kali Linux to perform footprinting and reconnaissance on the microsoft.com domain. I first used the following command to search for information from the Baidu search engine:
theHarvester -d microsoft.com -l 1000 -b baidu, I then performed a broader search using multiple available sources with:
theHarvester -d microsoft.com -l 50 -b all, From the results, I observed publicly available information related to the target domain, such as email addresses, subdomains, hosts, and other discovered details. This activity demonstrated how theHarvester can be used to collect information from public sources during the reconnaissance phase.

## 4.3 Network Scanning with Zenmap

I used Zenmap to perform network discovery on my local network. First, I used the Windows ipconfig command to identify my local IP address and subnet. I then entered the subnet into Zenmap and performed a Ping Scan to identify live hosts.
From the scan, I observed the active devices on my local network along with their IP and MAC addresses. I also used Zenmap’s Topology section to visualize the discovered devices and their network relationships. The topology was then saved as a PDF as required by the practical task.
The IP addresses, MAC addresses, and number of live hosts shown in this report are based on the results observed from my own local network.


