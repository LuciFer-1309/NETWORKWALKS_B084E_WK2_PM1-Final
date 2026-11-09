# Penetration Testing Report

## Footprinting and Network Scanning Phases

### Project Information

| Field            | Details                                                                           |
| ---------------- | --------------------------------------------------------------------------------- |
| Name             | Atharv Shinde                                                                     |
| Organization     | Networkwalks                                                                      |
| Date             | 6 November 2026                                                                   |
| Modules          | Multiple Kali Tools (W2-PM1), Zenmap Scanning (W2-PM5)                            |
| Target           | Networkwalks.com and Own Local Network                                            |
| Permission       | Authorized                                                                        |
| Completed Phases | Phase 1: Reconnaissance and Footprinting; Phase 2: Scanning and Network Discovery |
| Remaining Phases | Phase 3–5: In Progress                                                            |

---

## 1. Introduction

This report documents the practical activities performed during Week 2 of the Networkwalks Cybersecurity and Penetration Testing Program.

The activities focused on two major areas:

- **Footprinting and Information Gathering (W2-PM1):** Used multiple Kali Linux tools to collect publicly available information about Networkwalks.com, including domain registration details, web technologies, DNS information, HTTP response headers, and possible web application firewall details.
- **Network Scanning and Discovery (W2-PM5):** Used Zenmap, the graphical interface of Nmap, to perform a ping scan on the local network and observe active hosts and available network information.

The purpose of these activities was to understand how reconnaissance and network discovery are performed during the initial stages of a penetration testing assessment.

## 2. Liability Disclaimer

All activities documented in this report were performed for educational and cybersecurity research purposes.

Testing was limited to the authorized domain and the user's own local network. No unauthorized systems or devices were intentionally targeted.

The information collected represents observations from the tools used during the practical exercises. These observations should not be considered confirmed security vulnerabilities unless further validation is performed.

## 3. Tools and Technologies Used

The following tools and technologies were used during the practical exercises:

| Tool / Technology      | Purpose                                                           |
| ---------------------- | ----------------------------------------------------------------- |
| Kali Linux             | Operating system used for reconnaissance and security tools       |
| Windows                | Operating system used for local network configuration and testing |
| WHOIS                  | Collecting domain registration and ownership-related information  |
| WhatWeb                | Identifying website technologies and web application details      |
| nslookup               | Resolving domain names into IP addresses                          |
| curl -I                | Retrieving HTTP response headers                                  |
| WAFW00F                | Checking for possible Web Application Firewall presence           |
| DNSRecon               | Collecting publicly available DNS information                     |
| Zenmap                 | Performing network scans through a graphical interface            |
| Windows Command Prompt | Checking local network configuration using ipconfig commands      |

## 4. Activities Performed

### 4.1 Footprinting and Information Gathering (W2-PM1)

The first activity involved collecting publicly available information about Networkwalks.com using different Kali Linux tools.

#### 4.1.1 WHOIS Lookup

**Objective:** To collect domain registration information and identify available domain-related details.

**Activity Performed:**

- Executed a WHOIS lookup for Networkwalks.com.
- Examined the available domain registration information.
- Observed domain-related details, including name server information.

**Observation:**

The WHOIS lookup provided publicly available domain registration information and name server details. This information can help understand the domain's registration and DNS infrastructure.

#### 4.1.2 WhatWeb Scan

**Objective:** To identify the technologies and content management system used by the target website.

**Activity Performed:**

- Executed WhatWeb against Networkwalks.com.
- Examined the technologies identified by the tool.
- Reviewed the detected content management system and plugin information.

**Observation:**

The scan identified the following technologies:

- WordPress 7.0.4
- WP Download Manager 3.3.58

This information demonstrates how website technology fingerprinting can reveal publicly detectable software and component versions.

#### 4.1.3 DNS Lookup Using nslookup

**Objective:** To identify the IP address associated with the target domain.

**Activity Performed:**

- Executed the nslookup command for Networkwalks.com.
- Observed the DNS resolution response.
- Recorded the resolved IP address.

**Observation:**

The domain resolved to the following IP address:

`192.232.216.135`

This demonstrates how DNS lookup tools can be used to identify the IP address associated with a domain name.

#### 4.1.4 HTTP Header Analysis Using curl

**Objective:** To inspect the HTTP response headers returned by the target website.

**Activity Performed:**

- Used the `curl -I` command against Networkwalks.com.
- Retrieved the HTTP response headers.
- Examined the available server and web application information.

**Observation:**

The HTTP response headers exposed technical information about the web server and website. The response also included information related to WordPress and the `/wp-json/` endpoint.

Such information can help identify the technologies and services used by a website.

#### 4.1.5 Web Application Firewall Detection Using WAFW00F

**Objective:** To check whether the target website uses a Web Application Firewall (WAF).

**Activity Performed:**

- Executed WAFW00F against Networkwalks.com.
- Attempted to identify the presence and type of WAF.
- Observed the tool's response during the detection process.

**Observation:**

The WAFW00F scan encountered an SSL connection error (`SSLEOFError`) while attempting to communicate with the target website.

Due to this connection issue, the WAF detection result was inconclusive. The presence or type of a Web Application Firewall could not be confirmed through this scan.

#### 4.1.6 DNS Enumeration Using DNSRecon

**Objective:** To collect available DNS records and understand the publicly exposed DNS infrastructure.

**Activity Performed:**

- Executed DNSRecon against Networkwalks.com.
- Examined the DNS information returned by the tool.
- Reviewed the available name server, mail server, and other DNS-related information.

**Observation:**

DNSRecon collected available DNS information associated with the target domain. This information can help understand the domain's DNS infrastructure and identify publicly exposed records.

### 4.2 Network Scanning Using Zenmap (W2-PM5)

The second activity focused on identifying active hosts within the local network using Zenmap.

#### 4.2.1 Identifying Local Network Configuration

**Objective:** To identify the local system's network configuration before performing a network scan.

**Activity Performed:**

- Opened Windows Command Prompt.
- Executed the `ipconfig` command.
- Used `ipconfig /all` to view additional network configuration details.
- Examined the IPv4 address, subnet mask, default gateway, and physical (MAC) address.

**Observation:**

The commands provided the local system's network configuration details, which helped identify the network range for the scanning activity.

#### 4.2.2 Performing a Ping Scan Using Zenmap

**Objective:** To discover active hosts within the local network.

**Activity Performed:**

- Opened Zenmap on the system.
- Selected the Ping Scan option.
- Entered the local network range for scanning.
- Executed the scan and observed the results.
- Reviewed the discovered IP addresses and available MAC address information.

**Observation:**

Zenmap reported that 256 hosts were up out of 256 IP addresses scanned.

This result represents the scan output and does not independently confirm that all 256 addresses correspond to separate physical devices. The results may require additional verification.

#### 4.2.3 Network Topology Visualization

**Objective:** To understand the network discovery results through a visual representation.

**Activity Performed:**

- Opened the Topology tab in Zenmap.
- Examined the visual representation of the discovered network.
- Adjusted the zoom level and spacing to improve visibility.
- Saved the network topology output as a PDF file.

**Observation:**

The topology view provided a graphical representation of the network scan results and helped visualize the discovered network information.

## 5. Findings and Risk Analysis

The following table summarizes the observations collected during the practical activities.

| No. | Finding                    | Observation                                                                                  | Potential Impact                                                                          | Assessment            |
| --- | -------------------------- | -------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- | --------------------- |
| 1   | Web Technology Information | WordPress 7.0.4 and WP Download Manager 3.3.58 were identified.                              | Publicly visible technology and version information may assist technology fingerprinting. | Medium                |
| 2   | Server IP Identification   | The domain resolved to `192.232.216.135`.                                                    | Reveals the IP address associated with the domain.                                        | Low                   |
| 3   | HTTP Technical Information | HTTP headers and the `/wp-json/` endpoint exposed technical information.                     | May help identify website technologies and services.                                      | Low                   |
| 4   | WAF Detection              | WAFW00F encountered an SSL connection error.                                                 | The presence and type of WAF could not be confirmed.                                      | Inconclusive          |
| 5   | DNS Information            | DNSRecon collected available DNS records, including name server and mail server information. | Public DNS information may assist infrastructure profiling.                               | Medium                |
| 6   | Network Discovery          | Zenmap reported 256 hosts up out of 256 IP addresses scanned.                                | Unexpected or unidentified hosts may require further verification.                        | Requires Verification |

**Note:** The findings listed above are observations and potential security considerations. They do not represent confirmed vulnerabilities. No exploitation or vulnerability validation was performed as part of these activities.

## 6. Recommendations

Based on the observations collected during the practical exercises, the following security improvements are recommended:

1. **Review Publicly Exposed Technology Information**

   Organizations should regularly review the information publicly visible about their web technologies, content management systems, plugins, and software versions.

2. **Keep Software Updated**

   CMS platforms, plugins, and other web technologies should be regularly updated to reduce exposure to known security issues.

3. **Review HTTP Response Headers**

   Organizations should review HTTP response headers and avoid unnecessarily exposing technical information that could assist technology fingerprinting.

4. **Review DNS Records**

   Public DNS records should be reviewed periodically to ensure that only required and intended information is exposed.

5. **Configure and Monitor Web Application Firewalls**

   Organizations should ensure that their WAF solutions, if deployed, are properly configured and monitored. The WAF presence on the tested domain was not confirmed during this activity.

6. **Perform Regular Network Discovery**

   Network administrators should conduct periodic network discovery to maintain visibility into active hosts and network-connected devices.

7. **Investigate Unknown Devices**

   Unrecognized or unexpected devices identified during network scans should be investigated to verify whether they are authorized.

8. **Maintain Network Documentation**

   Organizations should maintain updated documentation of their IP address ranges, network devices, and network infrastructure.

9. **Follow Authorized Testing Practices**

   Reconnaissance and scanning activities should always be performed within the approved scope and with proper authorization.

## 7. Conclusion

During Week 2 of the Networkwalks Cybersecurity and Penetration Testing Program, practical activities were performed on footprinting, information gathering, and network scanning.

In the first activity, multiple Kali Linux tools, including WHOIS, WhatWeb, nslookup, curl, WAFW00F, and DNSRecon, were used to collect publicly available information about Networkwalks.com.

In the second activity, Windows network configuration commands and Zenmap were used to examine the local network and identify active hosts. The scan reported 256 hosts up out of 256 IP addresses scanned. The results were also examined through Zenmap's network topology visualization feature.

These exercises provided practical understanding of how reconnaissance and network discovery contribute to the initial stages of penetration testing. They also highlighted the importance of interpreting tool output carefully, verifying findings, documenting observations, and following authorized testing practices.

## 8. Evidence and Screenshots
<img width="1917" height="288" alt="curl -I" src="https://github.com/user-attachments/assets/5e029030-54ca-4e09-ade2-01a4ee646213" />
<img width="1214" height="503" alt="dnsrecon" src="https://github.com/user-attachments/assets/c4f67ba9-3845-4bd7-affc-f4b97482e685" />
<img width="716" height="690" alt="Harvester1" src="https://github.com/user-attachments/assets/012d7a72-ebf0-4f3b-b8bc-4518192dbff5" />
<img width="1919" height="900" alt="Maltego" src="https://github.com/user-attachments/assets/a716f2db-842b-4358-848e-76ff7fa53210" />
<img width="290" height="177" alt="nslookup" src="https://github.com/user-attachments/assets/85a09729-3399-4835-b644-86f9a0a97a20" />
<img width="1639" height="803" alt="wafw00f" src="https://github.com/user-attachments/assets/363b1b23-b243-4220-b33d-a5d364356924" />
<img width="1910" height="783" alt="whatweb1" src="https://github.com/user-attachments/assets/bb138278-c138-4af4-8a4f-759dc12c5930" />
<img width="1056" height="857" alt="whois1" src="https://github.com/user-attachments/assets/813c090d-4309-4874-9752-8b42cfae2d40" />
<img width="1920" height="911" alt="Zenmap1" src="https://github.com/user-attachments/assets/ee361a4b-17b6-4974-82cb-7a8a89288ce6" />

## 9. Project Information

**Program:** Networkwalks Cybersecurity and Penetration Testing Program

**Week:** Week 2

**Focus Areas:**

- Reconnaissance and Footprinting
- Information Gathering
- DNS Enumeration
- Web Technology Fingerprinting
- HTTP Header Analysis
- Network Scanning
- Host Discovery
- Network Topology Visualization

**Prepared By:** Atharv Shinde

**Organization:** Networkwalks
